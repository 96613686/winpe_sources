# Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsQuickCreateEnabledMethod

- ea: `0x1b4a0`
- end: `0x1b587`
- name: `Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsQuickCreateEnabledMethod`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1afa0`

## callees

- `0x1b4a0`

## string_xrefs

- `0x1b4a7`: `{0}.isQuickCreateEnabled=function(entityName){{`

## pseudocode

```c

```

## disassembly

```asm
0x1b4a0  ldarg.1
0x1b4a1  ldind.ref
0x1b4a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b4a7  ldstr    a0Isquickcreate// "{0}.isQuickCreateEnabled=function(entit"...
0x1b4ac  ldc.i4.1
0x1b4ad  newarr   [mscorlib]System.Object
0x1b4b2  dup
0x1b4b3  ldc.i4.0
0x1b4b4  ldstr    aMscrmEntitypro// "Mscrm.EntityPropUtil"
0x1b4b9  stelem.ref
0x1b4ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1b4bf  pop
0x1b4c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1b4c5  stloc.0
0x1b4c6  ldloc.0
0x1b4c7  ldstr    aSwitchEntityna// "switch (entityName) {"
0x1b4cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b4d1  pop
0x1b4d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b4d7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b4dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x1b4e1  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x1b4e6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1b4eb  stloc.1
0x1b4ec  br.s     loc_1B523
0x1b4ee  ldloc.1
0x1b4ef  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b4f4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x1b4f9  stloc.2
0x1b4fa  ldloc.2
0x1b4fb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsQuickCreateEnabled()
0x1b500  brfalse.s loc_1B523
0x1b502  ldloc.2
0x1b503  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b508  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetQuickCreateFormDescriptor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b50d  brfalse.s loc_1B523
0x1b50f  ldloc.2
0x1b510  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1b515  stloc.3
0x1b516  ldloc.0
0x1b517  ldstr    aCase0_0// "case '{0}' : "
0x1b51c  ldloc.3
0x1b51d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1b522  pop
0x1b523  ldloc.1
0x1b524  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b529  brtrue.s loc_1B4EE
0x1b52b  leave.s  loc_1B541
0x1b52d  ldloc.1
0x1b52e  isinst   [mscorlib]System.IDisposable
0x1b533  stloc.s  4
0x1b535  ldloc.s  4
0x1b537  brfalse.s loc_1B540
0x1b539  ldloc.s  4
0x1b53b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b540  endfinally
0x1b541  ldloc.0
0x1b542  ldstr    aReturnTrue// " return true;"
0x1b547  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b54c  pop
0x1b54d  ldloc.0
0x1b54e  ldstr    aDefaultReturnF// "default: return false;}"
0x1b553  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b558  pop
0x1b559  ldarg.1
0x1b55a  ldind.ref
0x1b55b  ldloc.0
0x1b55c  callvirt instance string [mscorlib]System.Object::ToString()
0x1b561  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b566  pop
0x1b567  leave.s  loc_1B579
0x1b569  pop
0x1b56a  ldarg.1
0x1b56b  ldind.ref
0x1b56c  ldstr    aReturnFalse_0// "return false;"
0x1b571  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b576  pop
0x1b577  leave.s  loc_1B579
0x1b579  ldarg.1
0x1b57a  ldind.ref
0x1b57b  ldstr    asc_35ADA// "};"
0x1b580  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b585  pop
0x1b586  ret
```
