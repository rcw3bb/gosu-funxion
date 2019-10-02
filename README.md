## Funxion - Gosu Utility

Funxion is a utility class of executing functional interface for Gosu that at least running together with Java 8.

### Interface and Method Mapping

| Interface | Method |
|-------|--------|
| java.util.function.Consumer | Funxion.buildExecutor |
| java.util.function.Supplier | Funxion.buildGenerator |
| java.util.function.Function | Funxion.buildProcessor |

##### Example usage of Funxion.buildExecutor

Implement a Consumer like the following:

```gosu
var consumer : java.util.function.Consumer<String> = \ ___param -> {
  print("Hello ${___param}")
}
```

Execute it with parameter like the following:

```gosu
Funxion.buildExecutor(consumer).execute("World")
```

Execute it without parameter *(i.e. parameter will be null)* like the following:
```gosu
Funxion.buildExecutor(consumer).execute()
```

##### Example usage of Funxion.buildGenerator

Implement a Supplier like the following:

```gosu
var generate : java.util.function.Supplier<String> = \ -> {
  return "Generated"
}
```

Execute it like the following:

```gosu
print(Funxion.buildGenerator(consumer).generate())
```

##### Example usage of Funxion.buildProcessor

Implement the Function like the following:

```gosu
var toUpperCase : java.util.function.Function<String, String> = \ ___text -> ___text.toUpperCase()
```

Execute it like the following:

```gosu
print(Funxion.buildProcessor(toUpperCase).process("test"))
```