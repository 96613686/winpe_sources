# Microsoft.Crm.Tools.Admin.UpdateOrganizationCollector::Collect

- ea: `0x7490`
- end: `0x74bf`
- name: `Microsoft.Crm.Tools.Admin.UpdateOrganizationCollector::Collect`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x72f0`
- `0x84f0`
- `0x15a50`
- `0x15b40`
- `0x15b60`

## string_xrefs

- `0x74b4`: `DMSnapIn.Organization.Update`

## pseudocode

```c

```

## disassembly

```asm
0x7490  ldarg.1
0x7491  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x7496  stloc.0
0x7497  ldloc.0
0x7498  dup
0x7499  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.IUpdateOrganizationInfo::get_OrganizationId()
0x749e  stloc.1
0x749f  ldarg.1
0x74a0  callvirt instance void [mscorlib]System.Collections.IDictionary::Clear()
0x74a5  ldarg.0
0x74a6  ldloc.0
0x74a7  ldloc.1
0x74a8  call     instance void Microsoft.Crm.Tools.Admin.ExistingOrganizationCollector::RetrieveConfigurationSettings(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype [mscorlib]System.Guid organizationId)
0x74ad  dup
0x74ae  ldc.i4.3
0x74af  callvirt instance void Microsoft.Crm.Tools.Admin.IUpdateOrganizationInfo::set_OperationType(valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType value)
0x74b4  ldstr    aDmsnapinOrgani_1// "DMSnapIn.Organization.Update"
0x74b9  callvirt instance void Microsoft.Crm.Tools.Admin.IUpdateOrganizationInfo::set_EdwMode(string value)
0x74be  ret
```
