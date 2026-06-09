# Microsoft.Crm.Asynchronous.Operations.CompositeOperation::MarkAsIncomplete

- ea: `0x150a0`
- end: `0x150b5`
- name: `Microsoft.Crm.Asynchronous.Operations.CompositeOperation::MarkAsIncomplete`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x150a0`

## string_xrefs

- `0x150a9`: `Composite operations expect the inner steps to handle failure`

## pseudocode

```c

```

## disassembly

```asm
0x150a0  ldarg.1
0x150a1  isinst   [mscorlib]System.OperationCanceledException
0x150a6  brfalse.s loc_150A9
0x150a8  ret
0x150a9  ldstr    aCompositeOpera_1// "Composite operations expect the inner s"...
0x150ae  ldarg.1
0x150af  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0x150b4  throw
```
