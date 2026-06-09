# Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteEntityLogicalNameToLocalizedNameMap

- ea: `0x1b670`
- end: `0x1b786`
- name: `Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteEntityLogicalNameToLocalizedNameMap`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1afa0`

## callees

- `0x1b670`

## pseudocode

```c

```

## disassembly

```asm
0x1b670  ldstr    aEntitylogicaln// "EntityLogicalNameToLocalizedMap"
0x1b675  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x1b67a  stloc.0
0x1b67b  ldloc.0
0x1b67c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x1b681  ldarg.1
0x1b682  ldind.ref
0x1b683  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b688  ldstr    a0Entitylogical// "{0}.EntityLogicalNameToLocalizedNameMap"...
0x1b68d  ldc.i4.1
0x1b68e  newarr   [mscorlib]System.Object
0x1b693  dup
0x1b694  ldc.i4.0
0x1b695  ldstr    aMscrmEntitypro// "Mscrm.EntityPropUtil"
0x1b69a  stelem.ref
0x1b69b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1b6a0  pop
0x1b6a1  ldc.i4.1
0x1b6a2  stloc.1
0x1b6a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b6a8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b6ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x1b6b2  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x1b6b7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1b6bc  stloc.2
0x1b6bd  br       loc_1B751
0x1b6c2  ldloc.2
0x1b6c3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b6c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x1b6cd  stloc.3
0x1b6ce  ldloc.3
0x1b6cf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsLookupTable()
0x1b6d4  brtrue.s loc_1B751
0x1b6d6  ldloc.3
0x1b6d7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x1b6dc  brtrue.s loc_1B751
0x1b6de  ldloc.3
0x1b6df  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSecurityIntersect()
0x1b6e4  brtrue.s loc_1B751
0x1b6e6  ldloc.1
0x1b6e7  brfalse.s loc_1B6ED
0x1b6e9  ldc.i4.0
0x1b6ea  stloc.1
0x1b6eb  br.s     loc_1B705
0x1b6ed  ldarg.1
0x1b6ee  ldind.ref
0x1b6ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b6f4  ldstr    asc_35B2C// ","
0x1b6f9  ldc.i4.0
0x1b6fa  newarr   [mscorlib]System.Object
0x1b6ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1b704  pop
0x1b705  ldloc.3
0x1b706  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x1b70b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1b710  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1b715  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b71a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b71f  stloc.s  4
0x1b721  ldarg.1
0x1b722  ldind.ref
0x1b723  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b728  ldstr    a01_0// "{0} : {1}"
0x1b72d  ldc.i4.2
0x1b72e  newarr   [mscorlib]System.Object
0x1b733  dup
0x1b734  ldc.i4.0
0x1b735  ldloc.3
0x1b736  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1b73b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1b740  stelem.ref
0x1b741  dup
0x1b742  ldc.i4.1
0x1b743  ldloc.s  4
0x1b745  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1b74a  stelem.ref
0x1b74b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1b750  pop
0x1b751  ldloc.2
0x1b752  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b757  brtrue   loc_1B6C2
0x1b75c  leave.s  loc_1B772
0x1b75e  ldloc.2
0x1b75f  isinst   [mscorlib]System.IDisposable
0x1b764  stloc.s  5
0x1b766  ldloc.s  5
0x1b768  brfalse.s loc_1B771
0x1b76a  ldloc.s  5
0x1b76c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b771  endfinally
0x1b772  ldarg.1
0x1b773  ldind.ref
0x1b774  ldstr    asc_35ADA// "};"
0x1b779  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b77e  pop
0x1b77f  ldloc.0
0x1b780  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x1b785  ret
```
