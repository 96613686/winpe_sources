# Microsoft.Xrm.Sdk.Messages.UpsertResponse::get_RecordCreated

- ea: `0x12eb0`
- end: `0x12eda`
- name: `Microsoft.Xrm.Sdk.Messages.UpsertResponse::get_RecordCreated`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x3790`
- `0x12eb0`

## string_xrefs

- `0x12eb6`: `RecordCreated`
- `0x12ec8`: `RecordCreated`

## pseudocode

```c

```

## disassembly

```asm
0x12eb0  ldarg.0
0x12eb1  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12eb6  ldstr    aRecordcreated// "RecordCreated"
0x12ebb  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12ec0  brfalse.s loc_12ED8
0x12ec2  ldarg.0
0x12ec3  call     instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12ec8  ldstr    aRecordcreated// "RecordCreated"
0x12ecd  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12ed2  unbox.any [mscorlib]System.Boolean
0x12ed7  ret
0x12ed8  ldc.i4.0
0x12ed9  ret
```
