# Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::EnableCancellation

- ea: `0x155d0`
- end: `0x15603`
- name: `Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::EnableCancellation`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x150e0`

## callees

- `0x155d0`
- `0x15610`
- `0x15620`

## string_xrefs

- `0x155f1`: `Operations need not be thread safe and so can only be cancelled from a single source`

## pseudocode

```c

```

## disassembly

```asm
0x155d0  ldarg.0
0x155d1  call     instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::get_CancellationToken()
0x155d6  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x155db  call     bool [mscorlib]System.Threading.CancellationToken::op_Equality(valuetype [mscorlib]System.Threading.CancellationToken, valuetype [mscorlib]System.Threading.CancellationToken)
0x155e0  brtrue.s loc_155F0
0x155e2  ldarg.0
0x155e3  call     instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::get_CancellationToken()
0x155e8  ldarg.1
0x155e9  call     bool [mscorlib]System.Threading.CancellationToken::op_Equality(valuetype [mscorlib]System.Threading.CancellationToken, valuetype [mscorlib]System.Threading.CancellationToken)
0x155ee  br.s     loc_155F1
0x155f0  ldc.i4.1
0x155f1  ldstr    aOperationsNeed// "Operations need not be thread safe and "...
0x155f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x155fb  ldarg.0
0x155fc  ldarg.1
0x155fd  call     instance void Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::set_CancellationToken(valuetype [mscorlib]System.Threading.CancellationToken value)
0x15602  ret
```
