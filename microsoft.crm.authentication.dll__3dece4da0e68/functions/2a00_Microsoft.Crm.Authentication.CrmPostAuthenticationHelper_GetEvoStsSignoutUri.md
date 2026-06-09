# Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::GetEvoStsSignoutUri

- ea: `0x2a00`
- end: `0x2a5e`
- name: `Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::GetEvoStsSignoutUri`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2820`

## callees

- `0x2a00`

## string_xrefs

- `0x2a44`: `common`

## pseudocode

```c

```

## disassembly

```asm
0x2a00  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0x2a05  ldstr    aPassiveendpoin// "PassiveEndpoint"
0x2a0a  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0x2a0f  castclass [mscorlib]System.String
0x2a14  stloc.0
0x2a15  ldloc.0
0x2a16  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a1b  brfalse.s loc_2A1F
0x2a1d  ldnull
0x2a1e  ret
0x2a1f  ldarg.0
0x2a20  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a25  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a2a  brfalse.s loc_2A2E
0x2a2c  ldloc.0
0x2a2d  ret
0x2a2e  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0x2a33  ldarg.0
0x2a34  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0x2a39  stloc.1
0x2a3a  ldloca.s 1
0x2a3c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2a41  brfalse.s loc_2A5C
0x2a43  ldloc.0
0x2a44  ldstr    aCommon// "common"
0x2a49  ldloca.s 1
0x2a4b  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x2a51  callvirt instance string [mscorlib]System.Object::ToString()
0x2a56  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2a5b  stloc.0
0x2a5c  ldloc.0
0x2a5d  ret
```
