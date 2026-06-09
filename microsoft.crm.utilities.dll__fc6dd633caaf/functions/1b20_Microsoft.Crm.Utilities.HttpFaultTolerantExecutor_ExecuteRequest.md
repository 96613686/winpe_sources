# Microsoft.Crm.Utilities.HttpFaultTolerantExecutor::ExecuteRequest

- ea: `0x1b20`
- end: `0x1b51`
- name: `Microsoft.Crm.Utilities.HttpFaultTolerantExecutor::ExecuteRequest`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b00`
- `0x1b10`

## callees

- `0x1f10`

## pseudocode

```c

```

## disassembly

```asm
0x1b20  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x1b25  stloc.0
0x1b26  ldloc.0
0x1b27  ldarg.0
0x1b28  stfld    class [mscorlib]System.Func`1<string> <>c__DisplayClass8_0::action
0x1b2d  ldloc.0
0x1b2e  ldsfld   string [mscorlib]System.String::Empty
0x1b33  stfld    string <>c__DisplayClass8_0::result
0x1b38  ldarg.1
0x1b39  ldloc.0
0x1b3a  ldftn    instance void <>c__DisplayClass8_0::<ExecuteRequest>b__0()
0x1b40  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1b45  callvirt instance void [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.RetryPolicy::ExecuteAction(class [mscorlib]System.Action)
0x1b4a  ldloc.0
0x1b4b  ldfld    string <>c__DisplayClass8_0::result
0x1b50  ret
```
