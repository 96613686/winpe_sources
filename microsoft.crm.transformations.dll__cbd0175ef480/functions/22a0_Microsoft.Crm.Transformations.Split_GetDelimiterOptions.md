# Microsoft.Crm.Transformations.Split::GetDelimiterOptions

- ea: `0x22a0`
- end: `0x22e1`
- name: `Microsoft.Crm.Transformations.Split::GetDelimiterOptions`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2250`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x22a0  ldc.i4.1
0x22a1  newarr   [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption
0x22a6  dup
0x22a7  ldc.i4.0
0x22a8  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x22ad  stelem.ref
0x22ae  dup
0x22af  ldc.i4.0
0x22b0  ldelem.ref
0x22b1  ldstr    aMicrosoftCrmTr_116// "Microsoft.Crm.Transformations.Split.Inp"...
0x22b6  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x22bb  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x22c0  dup
0x22c1  ldc.i4.0
0x22c2  ldelem.ref
0x22c3  ldstr    aMicrosoftCrmTr_117// "Microsoft.Crm.Transformations.Split.Inp"...
0x22c8  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x22cd  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x22d2  dup
0x22d3  ldc.i4.0
0x22d4  ldelem.ref
0x22d5  ldc.i4.1
0x22d6  box      [mscorlib]System.Int32
0x22db  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x22e0  ret
```
