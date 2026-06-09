# Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup

- ea: `0x910`
- end: `0x93f`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x860`

## callees

- `0x940`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldstr    aMicrosoftCrmAs// "Microsoft.Crm.Asynchronous."
0x915  ldarg.0
0x916  call     string [mscorlib]System.String::Concat(string, string)
0x91b  ldstr    aMicrosoftCrmAs_0// "Microsoft.Crm.Asynchronous.{0}HandlerGr"...
0x920  ldc.i4.1
0x921  newarr   [mscorlib]System.Object
0x926  dup
0x927  ldc.i4.0
0x928  ldarg.0
0x929  stelem.ref
0x92a  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string, string, object[])
0x92f  call     class [mscorlib]System.Type Microsoft.Crm.Asynchronous.AsyncHandlerFactory::LoadType(string qualifiedTypeName)
0x934  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x939  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup
0x93e  ret
```
