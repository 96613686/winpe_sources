# Microsoft.Crm.Sdk.Messages.Internal.ImportLinearMappingsImportMapRequest::get_ReplaceIds

- ea: `0x65e0`
- end: `0x660a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ImportLinearMappingsImportMapRequest::get_ReplaceIds`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x65e0`

## string_xrefs

- `0x65e6`: `ReplaceIds`
- `0x65f8`: `ReplaceIds`

## pseudocode

```c

```

## disassembly

```asm
0x65e0  ldarg.0
0x65e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x65e6  ldstr    aReplaceids// "ReplaceIds"
0x65eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x65f0  brfalse.s loc_6608
0x65f2  ldarg.0
0x65f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x65f8  ldstr    aReplaceids// "ReplaceIds"
0x65fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6602  unbox.any [mscorlib]System.Boolean
0x6607  ret
0x6608  ldc.i4.0
0x6609  ret
```
