# Microsoft.Crm.Sdk.Messages.Internal.IsPartnerSolutionInstalledResponse::get_IsPartnerSolutionInstalled

- ea: `0x13310`
- end: `0x1333a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.IsPartnerSolutionInstalledResponse::get_IsPartnerSolutionInstalled`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13310`

## string_xrefs

- `0x13316`: `IsPartnerSolutionInstalled`
- `0x13328`: `IsPartnerSolutionInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x13310  ldarg.0
0x13311  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x13316  ldstr    aIspartnersolut// "IsPartnerSolutionInstalled"
0x1331b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13320  brfalse.s loc_13338
0x13322  ldarg.0
0x13323  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x13328  ldstr    aIspartnersolut// "IsPartnerSolutionInstalled"
0x1332d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13332  unbox.any [mscorlib]System.Boolean
0x13337  ret
0x13338  ldc.i4.0
0x13339  ret
```
