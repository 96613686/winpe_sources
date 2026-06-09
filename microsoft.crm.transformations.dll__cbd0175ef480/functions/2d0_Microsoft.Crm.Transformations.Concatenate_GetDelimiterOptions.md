# Microsoft.Crm.Transformations.Concatenate::GetDelimiterOptions

- ea: `0x2d0`
- end: `0x3bb`
- name: `Microsoft.Crm.Transformations.Concatenate::GetDelimiterOptions`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x280`

## callees

- `0x2740`

## string_xrefs

- `0x31a`: `Microsoft.Crm.Transformations.Concatenate.InputParameter.Delimiter.Option.CommaSpace.Name`
- `0x32c`: `Microsoft.Crm.Transformations.Concatenate.InputParameter.Delimiter.Option.CommaSpace.Description`

## pseudocode

```c

```

## disassembly

```asm
0x2d0  ldc.i4.4
0x2d1  newarr   [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption
0x2d6  dup
0x2d7  ldc.i4.0
0x2d8  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x2dd  stelem.ref
0x2de  dup
0x2df  ldc.i4.0
0x2e0  ldelem.ref
0x2e1  ldstr    aMicrosoftCrmTr_9// "Microsoft.Crm.Transformations.Concatena"...
0x2e6  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2eb  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x2f0  dup
0x2f1  ldc.i4.0
0x2f2  ldelem.ref
0x2f3  ldstr    aMicrosoftCrmTr_10// "Microsoft.Crm.Transformations.Concatena"...
0x2f8  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2fd  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x302  dup
0x303  ldc.i4.0
0x304  ldelem.ref
0x305  ldstr    asc_3704// " "
0x30a  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x30f  dup
0x310  ldc.i4.1
0x311  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x316  stelem.ref
0x317  dup
0x318  ldc.i4.1
0x319  ldelem.ref
0x31a  ldstr    aMicrosoftCrmTr_11// "Microsoft.Crm.Transformations.Concatena"...
0x31f  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x324  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x329  dup
0x32a  ldc.i4.1
0x32b  ldelem.ref
0x32c  ldstr    aMicrosoftCrmTr_12// "Microsoft.Crm.Transformations.Concatena"...
0x331  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x336  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x33b  dup
0x33c  ldc.i4.1
0x33d  ldelem.ref
0x33e  ldstr    asc_387E// ", "
0x343  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x348  dup
0x349  ldc.i4.2
0x34a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x34f  stelem.ref
0x350  dup
0x351  ldc.i4.2
0x352  ldelem.ref
0x353  ldstr    aMicrosoftCrmTr_13// "Microsoft.Crm.Transformations.Concatena"...
0x358  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x35d  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x362  dup
0x363  ldc.i4.2
0x364  ldelem.ref
0x365  ldstr    aMicrosoftCrmTr_14// "Microsoft.Crm.Transformations.Concatena"...
0x36a  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x36f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x374  dup
0x375  ldc.i4.2
0x376  ldelem.ref
0x377  ldstr    asc_3A0A// "; "
0x37c  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x381  dup
0x382  ldc.i4.3
0x383  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x388  stelem.ref
0x389  dup
0x38a  ldc.i4.3
0x38b  ldelem.ref
0x38c  ldstr    aMicrosoftCrmTr_15// "Microsoft.Crm.Transformations.Concatena"...
0x391  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x396  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x39b  dup
0x39c  ldc.i4.3
0x39d  ldelem.ref
0x39e  ldstr    aMicrosoftCrmTr_16// "Microsoft.Crm.Transformations.Concatena"...
0x3a3  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x3a8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x3ad  dup
0x3ae  ldc.i4.3
0x3af  ldelem.ref
0x3b0  ldstr    asc_3B86// ": "
0x3b5  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x3ba  ret
```
