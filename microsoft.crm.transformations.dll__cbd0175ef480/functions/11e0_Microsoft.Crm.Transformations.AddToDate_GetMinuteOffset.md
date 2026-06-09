# Microsoft.Crm.Transformations.AddToDate::GetMinuteOffset

- ea: `0x11e0`
- end: `0x121c`
- name: `Microsoft.Crm.Transformations.AddToDate::GetMinuteOffset`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd10`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x11e0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x11e5  dup
0x11e6  ldstr    aMicrosoftCrmTr_67// "Microsoft.Crm.Transformations.AddToDate"...
0x11eb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x11f0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x11f5  dup
0x11f6  ldstr    aMicrosoftCrmTr_68// "Microsoft.Crm.Transformations.AddToDate"...
0x11fb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1200  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1205  dup
0x1206  ldc.i4.s 9
0x1208  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x120d  dup
0x120e  ldc.i4.0
0x120f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1214  dup
0x1215  ldc.i4.0
0x1216  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x121b  ret
```
