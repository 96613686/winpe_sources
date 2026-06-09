# Microsoft.Crm.Sdk.Messages.Internal.RetrieveEntitiesToSyncRequest::get_ColumnSetXml

- ea: `0xe200`
- end: `0xe22a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveEntitiesToSyncRequest::get_ColumnSetXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe200`

## string_xrefs

- `0xe206`: `ColumnSetXml`
- `0xe218`: `ColumnSetXml`

## pseudocode

```c

```

## disassembly

```asm
0xe200  ldarg.0
0xe201  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xe206  ldstr    aColumnsetxml// "ColumnSetXml"
0xe20b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xe210  brfalse.s loc_E228
0xe212  ldarg.0
0xe213  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xe218  ldstr    aColumnsetxml// "ColumnSetXml"
0xe21d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xe222  castclass [mscorlib]System.String
0xe227  ret
0xe228  ldnull
0xe229  ret
```
