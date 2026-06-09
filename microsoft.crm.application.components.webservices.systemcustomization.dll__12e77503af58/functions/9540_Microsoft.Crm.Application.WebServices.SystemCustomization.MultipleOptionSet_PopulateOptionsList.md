# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateOptionsList

- ea: `0x9540`
- end: `0x95f3`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateOptionsList`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb4a0`

## callees

- `0x9540`

## pseudocode

```c

```

## disassembly

```asm
0x9540  ldarg.0
0x9541  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::Clear()
0x9546  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x954b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9550  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9555  stloc.0
0x9556  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x955b  ldc.i4.1
0x955c  ldc.i4.1
0x955d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetByIdDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSets(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetGlobalFilters, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetTypeFilters)
0x9562  ldarg.0
0x9563  ldsfld   string [mscorlib]System.String::Empty
0x9568  ldsfld   string [mscorlib]System.String::Empty
0x956d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x9572  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>>::GetEnumerator()
0x9577  stloc.1
0x9578  br.s     loc_95B1
0x957a  ldloc.1
0x957b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>>::get_Current()
0x9580  stloc.2
0x9581  ldloca.s 2
0x9583  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::get_Key()
0x9588  stloc.3
0x9589  ldloca.s 2
0x958b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::get_Value()
0x9590  stloc.s  4
0x9592  ldarg.0
0x9593  ldloc.s  4
0x9595  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_DisplayNames()
0x959a  ldloc.0
0x959b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x95a0  ldloca.s 3
0x95a2  ldstr    aB// "B"
0x95a7  call     instance string [mscorlib]System.Guid::ToString(string)
0x95ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x95b1  ldloc.1
0x95b2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x95b7  brtrue.s loc_957A
0x95b9  leave.s  loc_95C5
0x95bb  ldloc.1
0x95bc  brfalse.s loc_95C4
0x95be  ldloc.1
0x95bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x95c4  endfinally
0x95c5  ldarg.0
0x95c6  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x95cb  ldc.i4.0
0x95cc  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x95d1  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x95d6  ldc.i4.1
0x95d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_Sorting(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x95dc  ldarg.0
0x95dd  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x95e2  ldc.i4.0
0x95e3  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x95e8  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x95ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::ExecuteSort()
0x95f2  ret
```
