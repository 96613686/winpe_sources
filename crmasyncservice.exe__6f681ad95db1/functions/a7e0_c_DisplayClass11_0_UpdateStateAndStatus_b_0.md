# <>c__DisplayClass11_0::<UpdateStateAndStatus>b__0

- ea: `0xa7e0`
- end: `0xa825`
- name: `<>c__DisplayClass11_0::<UpdateStateAndStatus>b__0`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c

```

## disassembly

```asm
0xa7e0  ldarg.0
0xa7e1  ldarg.1
0xa7e2  ldc.i4.0
0xa7e3  ldelem.ref
0xa7e4  unbox.any [mscorlib]System.Guid
0xa7e9  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::organizationId
0xa7ee  ldarg.0
0xa7ef  ldarg.1
0xa7f0  ldc.i4.1
0xa7f1  ldelem.ref
0xa7f2  unbox.any [mscorlib]System.Int32
0xa7f7  stfld    int32 <>c__DisplayClass11_0::operationType
0xa7fc  ldarg.0
0xa7fd  ldarg.0
0xa7fe  ldfld    class Microsoft.Crm.Asynchronous.JobDataAccess <>c__DisplayClass11_0::<>4__this
0xa803  ldarg.1
0xa804  ldc.i4.2
0xa805  ldelem.ref
0xa806  call     T0x2B00001D
0xa80b  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass11_0::operationStartTime
0xa810  ldarg.0
0xa811  ldarg.0
0xa812  ldfld    class Microsoft.Crm.Asynchronous.JobDataAccess <>c__DisplayClass11_0::<>4__this
0xa817  ldarg.1
0xa818  ldc.i4.3
0xa819  ldelem.ref
0xa81a  call     T0x2B00001D
0xa81f  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass11_0::operationEndTime
0xa824  ret
```
