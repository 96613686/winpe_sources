# Microsoft.Crm.Tools.Admin.CreateOrganizationCollector::SetOperationParameters

- ea: `0x7350`
- end: `0x736a`
- name: `Microsoft.Crm.Tools.Admin.CreateOrganizationCollector::SetOperationParameters`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7320`

## callees

- `0x11ee0`
- `0x11f80`
- `0x11fa0`

## string_xrefs

- `0x7358`: `DMSnapIn.Organization.Create`

## pseudocode

```c

```

## disassembly

```asm
0x7350  ldarg.0
0x7351  ldc.i4.1
0x7352  callvirt instance void Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo::set_OperationType(valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType value)
0x7357  ldarg.0
0x7358  ldstr    aDmsnapinOrgani// "DMSnapIn.Organization.Create"
0x735d  callvirt instance void Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo::set_EdwMode(string value)
0x7362  ldarg.0
0x7363  ldc.i4.1
0x7364  callvirt instance void Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo::set_CreateDatabase(bool value)
0x7369  ret
```
