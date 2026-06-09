# Microsoft.Crm.Tools.Admin.OrganizationManifestService::CreateManifest

- ea: `0xb9d0`
- end: `0xb9f3`
- name: `Microsoft.Crm.Tools.Admin.OrganizationManifestService::CreateManifest`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xb9dc`: `filePath`

## pseudocode

```c

```

## disassembly

```asm
0xb9d0  ldarg.1
0xb9d1  ldstr    aOrganizationid_0// "organizationId"
0xb9d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xb9db  ldarg.2
0xb9dc  ldstr    aFilepath// "filePath"
0xb9e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xb9e6  ldarg.1
0xb9e7  ldarg.2
0xb9e8  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::.ctor(valuetype [mscorlib]System.Guid, string)
0xb9ed  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::Do()
0xb9f2  ret
```
