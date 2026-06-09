# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForRelationship

- ea: `0x64d0`
- end: `0x651d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForRelationship`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6380`

## callees

- `0x64d0`

## pseudocode

```c

```

## disassembly

```asm
0x64d0  ldc.i4.0
0x64d1  stloc.0
0x64d2  ldarg.1
0x64d3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x64d8  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x64dd  stloc.1
0x64de  br.s     loc_64F7
0x64e0  ldarg.1
0x64e1  ldloca.s 0
0x64e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64e8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x64ed  call     string [mscorlib]System.String::Concat(string, string)
0x64f2  stloc.1
0x64f3  ldloc.0
0x64f4  ldc.i4.1
0x64f5  add
0x64f6  stloc.0
0x64f7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x64fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x6501  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6506  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x650b  ldloc.1
0x650c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityRelationship(string)
0x6511  brtrue.s loc_64E0
0x6513  ldloc.1
0x6514  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6519  brtrue.s loc_64E0
0x651b  ldloc.1
0x651c  ret
```
