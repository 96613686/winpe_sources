# Microsoft.Crm.Tools.Admin.ClaimsConfiguration::CreateIfProviderDoesNotExist

- ea: `0x2e50`
- end: `0x2ea8`
- name: `Microsoft.Crm.Tools.Admin.ClaimsConfiguration::CreateIfProviderDoesNotExist`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2eb0`

## callees

- `0x2e50`
- `0x3340`

## string_xrefs

- `0x2e51`: `claimsInfo`

## pseudocode

```c

```

## disassembly

```asm
0x2e50  ldarg.0
0x2e51  ldstr    aClaimsinfo// "claimsInfo"
0x2e56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e5b  ldc.i4.0
0x2e5c  stloc.0
0x2e5d  ldarg.0
0x2e5e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2e63  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0x2e68  stloc.1
0x2e69  ldloc.1
0x2e6a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::GetFederationProviderData()
0x2e6f  stloc.2
0x2e70  ldloc.2
0x2e71  brfalse.s loc_2E80
0x2e73  ldloc.2
0x2e74  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_MetadataUrl()
0x2e79  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2e7e  br.s     loc_2E81
0x2e80  ldc.i4.1
0x2e81  stloc.0
0x2e82  leave.s  loc_2E9A
0x2e84  stloc.3
0x2e85  ldc.i4   0x8004D230
0x2e8a  ldloc.3
0x2e8b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x2e90  bne.un.s loc_2E96
0x2e92  ldc.i4.1
0x2e93  stloc.0
0x2e94  br.s     loc_2E98
0x2e96  rethrow
0x2e98  leave.s  loc_2E9A
0x2e9a  ldloc.0
0x2e9b  brfalse.s loc_2EA6
0x2e9d  ldloc.1
0x2e9e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::TryCreate()
0x2ea3  pop
0x2ea4  ldc.i4.1
0x2ea5  ret
0x2ea6  ldc.i4.0
0x2ea7  ret
```
