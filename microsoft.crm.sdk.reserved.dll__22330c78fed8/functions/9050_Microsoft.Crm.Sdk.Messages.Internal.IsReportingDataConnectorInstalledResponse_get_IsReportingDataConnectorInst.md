# Microsoft.Crm.Sdk.Messages.Internal.IsReportingDataConnectorInstalledResponse::get_IsReportingDataConnectorInstalled

- ea: `0x9050`
- end: `0x907a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.IsReportingDataConnectorInstalledResponse::get_IsReportingDataConnectorInstalled`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9050`

## string_xrefs

- `0x9056`: `IsReportingDataConnectorInstalled`
- `0x9068`: `IsReportingDataConnectorInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x9050  ldarg.0
0x9051  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x9056  ldstr    aIsreportingdat// "IsReportingDataConnectorInstalled"
0x905b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x9060  brfalse.s loc_9078
0x9062  ldarg.0
0x9063  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x9068  ldstr    aIsreportingdat// "IsReportingDataConnectorInstalled"
0x906d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x9072  unbox.any [mscorlib]System.Boolean
0x9077  ret
0x9078  ldc.i4.0
0x9079  ret
```
