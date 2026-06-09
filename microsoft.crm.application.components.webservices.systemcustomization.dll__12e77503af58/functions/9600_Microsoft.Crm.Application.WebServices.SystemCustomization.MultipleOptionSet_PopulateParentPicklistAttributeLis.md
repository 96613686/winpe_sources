# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateParentPicklistAttributeList

- ea: `0x9600`
- end: `0x9771`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateParentPicklistAttributeList`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb4d0`

## callees

- `0x9600`

## pseudocode

```c

```

## disassembly

```asm
0x9600  ldarg.0
0x9601  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::Clear()
0x9606  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x960b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9610  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9615  stloc.0
0x9616  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x961b  stloc.1
0x961c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9621  stloc.2
0x9622  ldarg.2
0x9623  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9628  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x962d  brfalse.s loc_965B
0x962f  ldloc.1
0x9630  ldarg.2
0x9631  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetOptionSet(valuetype [mscorlib]System.Guid)
0x9636  stloc.3
0x9637  ldloc.3
0x9638  brfalse.s loc_965B
0x963a  ldloc.3
0x963b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_IsGlobal()
0x9640  brfalse.s loc_965B
0x9642  ldloc.3
0x9643  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_ParentOptionSetId()
0x9648  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x964d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9652  brfalse.s loc_965B
0x9654  ldloc.3
0x9655  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_ParentOptionSetId()
0x965a  stloc.2
0x965b  ldarg.0
0x965c  ldsfld   string [mscorlib]System.String::Empty
0x9661  ldsfld   string [mscorlib]System.String::Empty
0x9666  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x966b  ldloc.1
0x966c  ldarg.1
0x966d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x9672  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x9677  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x967c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9681  stloc.s  4
0x9683  br       loc_9720
0x9688  ldloc.s  4
0x968a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x968f  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x9694  stloc.s  5
0x9696  ldloc.s  5
0x9698  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x969d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x96a2  ldc.i4.s 0xC
0x96a4  bne.un.s loc_9720
0x96a6  ldarg.2
0x96a7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x96ac  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x96b1  brtrue.s loc_96D4
0x96b3  ldloc.2
0x96b4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x96b9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x96be  brfalse.s loc_9720
0x96c0  ldloc.s  5
0x96c2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata
0x96c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSetId()
0x96cc  ldloc.2
0x96cd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x96d2  brfalse.s loc_9720
0x96d4  ldarg.0
0x96d5  ldloc.s  5
0x96d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x96dc  ldloc.0
0x96dd  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x96e2  ldloc.s  5
0x96e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x96e9  stloc.s  6
0x96eb  ldloca.s 6
0x96ed  ldstr    aB// "B"
0x96f2  call     instance string [mscorlib]System.Guid::ToString(string)
0x96f7  ldstr    asc_10540// "|"
0x96fc  ldloc.s  5
0x96fe  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata
0x9703  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSetId()
0x9708  stloc.s  6
0x970a  ldloca.s 6
0x970c  ldstr    aB// "B"
0x9711  call     instance string [mscorlib]System.Guid::ToString(string)
0x9716  call     string [mscorlib]System.String::Concat(string, string, string)
0x971b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x9720  ldloc.s  4
0x9722  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9727  brtrue   loc_9688
0x972c  leave.s  loc_9743
0x972e  ldloc.s  4
0x9730  isinst   [mscorlib]System.IDisposable
0x9735  stloc.s  7
0x9737  ldloc.s  7
0x9739  brfalse.s loc_9742
0x973b  ldloc.s  7
0x973d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9742  endfinally
0x9743  ldarg.0
0x9744  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x9749  ldc.i4.0
0x974a  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x974f  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x9754  ldc.i4.1
0x9755  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_Sorting(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x975a  ldarg.0
0x975b  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x9760  ldc.i4.0
0x9761  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9766  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x976b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::ExecuteSort()
0x9770  ret
```
