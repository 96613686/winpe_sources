# Microsoft.Crm.StorageNotificationUtility::UpdateOrganizationData

- ea: `0x24d30`
- end: `0x24d65`
- name: `Microsoft.Crm.StorageNotificationUtility::UpdateOrganizationData`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x24490`
- `0x24690`
- `0x246f0`

## callees

- `0x24d30`

## string_xrefs

- `0x24d48`: `UpdateOrganizationData`

## pseudocode

```c

```

## disassembly

```asm
0x24d30  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24d35  stloc.0
0x24d36  ldloc.0
0x24d37  ldstr    aOrganization// "Organization"
0x24d3c  ldarg.0
0x24d3d  box      [mscorlib]System.Guid
0x24d42  ldarg.1
0x24d43  ldc.i4   0x1C5
0x24d48  ldstr    aUpdateorganiza// "UpdateOrganizationData"
0x24d4d  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x24d52  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x24d57  pop
0x24d58  leave.s  loc_24D64
0x24d5a  ldloc.0
0x24d5b  brfalse.s loc_24D63
0x24d5d  ldloc.0
0x24d5e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24d63  endfinally
0x24d64  ret
```
