# Microsoft.Crm.Sdk.Messages.Internal.GetWopiExcelClientInfoRequest::get_FileExtension

- ea: `0x141e0`
- end: `0x1420a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetWopiExcelClientInfoRequest::get_FileExtension`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x141e0`

## string_xrefs

- `0x141e6`: `FileExtension`
- `0x141f8`: `FileExtension`

## pseudocode

```c

```

## disassembly

```asm
0x141e0  ldarg.0
0x141e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x141e6  ldstr    aFileextension// "FileExtension"
0x141eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x141f0  brfalse.s loc_14208
0x141f2  ldarg.0
0x141f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x141f8  ldstr    aFileextension// "FileExtension"
0x141fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14202  castclass [mscorlib]System.String
0x14207  ret
0x14208  ldnull
0x14209  ret
```
