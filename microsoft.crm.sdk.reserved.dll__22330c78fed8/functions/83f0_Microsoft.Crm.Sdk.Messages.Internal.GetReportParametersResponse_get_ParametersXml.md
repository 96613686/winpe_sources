# Microsoft.Crm.Sdk.Messages.Internal.GetReportParametersResponse::get_ParametersXml

- ea: `0x83f0`
- end: `0x841a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetReportParametersResponse::get_ParametersXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x83f0`

## string_xrefs

- `0x83f6`: `ParametersXml`
- `0x8408`: `ParametersXml`

## pseudocode

```c

```

## disassembly

```asm
0x83f0  ldarg.0
0x83f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x83f6  ldstr    aParametersxml// "ParametersXml"
0x83fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8400  brfalse.s loc_8418
0x8402  ldarg.0
0x8403  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x8408  ldstr    aParametersxml// "ParametersXml"
0x840d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8412  castclass [mscorlib]System.String
0x8417  ret
0x8418  ldnull
0x8419  ret
```
