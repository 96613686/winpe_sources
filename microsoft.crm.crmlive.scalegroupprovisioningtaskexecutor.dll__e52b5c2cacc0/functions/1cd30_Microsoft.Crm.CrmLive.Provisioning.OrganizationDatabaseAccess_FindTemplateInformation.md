# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FindTemplateInformation

- ea: `0x1cd30`
- end: `0x1cdcf`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FindTemplateInformation`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x91e0`
- `0x91f0`
- `0x9200`
- `0x9220`
- `0x92f0`
- `0x9410`
- `0x1cd30`
- `0x1cdd0`
- `0x1fc50`

## string_xrefs

- `0x1cd5b`: `No template path\share found for this scalegroup`
- `0x1cd67`: `organizationtemplate`

## pseudocode

```c

```

## disassembly

```asm
0x1cd30  ldarg.1
0x1cd31  ldstr    aOrganizationpr// "organizationProperties"
0x1cd36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1cd3b  ldarg.1
0x1cd3c  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x1cd41  brfalse.s loc_1CD45
0x1cd43  ldc.i4.0
0x1cd44  ret
0x1cd45  ldarg.1
0x1cd46  call     string Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GenerateTemplateBackupPath(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x1cd4b  stloc.0
0x1cd4c  ldarg.1
0x1cd4d  ldloc.0
0x1cd4e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_OrganizationTemplateShare(string value)
0x1cd53  ldloc.0
0x1cd54  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1cd59  brfalse.s loc_1CD66
0x1cd5b  ldstr    aNoTemplatePath// "No template path\\share found for this "...
0x1cd60  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1cd65  throw
0x1cd66  ldloc.0
0x1cd67  ldstr    aOrganizationte// "organizationtemplate"
0x1cd6c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1cd71  stloc.1
0x1cd72  ldloc.1
0x1cd73  ldarg.1
0x1cd74  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_BaseLanguageCode()
0x1cd79  stloc.3
0x1cd7a  ldloca.s 3
0x1cd7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cd81  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1cd86  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1cd8b  stloc.1
0x1cd8c  ldarg.1
0x1cd8d  ldloc.1
0x1cd8e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_OrganizationTemplateName(string value)
0x1cd93  ldarg.1
0x1cd94  ldc.i4.1
0x1cd95  newarr   [mscorlib]System.String
0x1cd9a  dup
0x1cd9b  ldc.i4.0
0x1cd9c  ldloc.1
0x1cd9d  stelem.ref
0x1cd9e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_OrganizationTemplateNames(string[] value)
0x1cda3  ldc.i4.1
0x1cda4  stloc.2
0x1cda5  ldarg.1
0x1cda6  callvirt instance string[] Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationTemplateNames()
0x1cdab  stloc.s  4
0x1cdad  ldc.i4.0
0x1cdae  stloc.3
0x1cdaf  br.s     loc_1CDC6
0x1cdb1  ldloc.s  4
0x1cdb3  ldloc.3
0x1cdb4  ldelem.ref
0x1cdb5  stloc.s  5
0x1cdb7  ldloc.2
0x1cdb8  ldarg.0
0x1cdb9  ldloc.s  5
0x1cdbb  call     instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::ValidateTemplateFiles(string templateFileBaseName)
0x1cdc0  and
0x1cdc1  stloc.2
0x1cdc2  ldloc.3
0x1cdc3  ldc.i4.1
0x1cdc4  add
0x1cdc5  stloc.3
0x1cdc6  ldloc.3
0x1cdc7  ldloc.s  4
0x1cdc9  ldlen
0x1cdca  conv.i4
0x1cdcb  blt.s    loc_1CDB1
0x1cdcd  ldloc.2
0x1cdce  ret
```
