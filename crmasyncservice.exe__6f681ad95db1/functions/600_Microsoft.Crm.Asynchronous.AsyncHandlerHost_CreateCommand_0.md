# Microsoft.Crm.Asynchronous.AsyncHandlerHost::CreateCommand_0

- ea: `0x600`
- end: `0x61f`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerHost::CreateCommand_0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x600  ldarg.1
0x601  ldc.i4.2
0x602  newarr   [mscorlib]System.Object
0x607  dup
0x608  ldc.i4.0
0x609  ldarg.0
0x60a  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncHandlerHost::asyncService
0x60f  stelem.ref
0x610  dup
0x611  ldc.i4.1
0x612  ldarg.2
0x613  stelem.ref
0x614  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x619  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand
0x61e  ret
```
