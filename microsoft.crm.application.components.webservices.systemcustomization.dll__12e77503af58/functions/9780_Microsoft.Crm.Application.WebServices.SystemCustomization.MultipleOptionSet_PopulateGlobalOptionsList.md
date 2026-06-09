# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateGlobalOptionsList

- ea: `0x9780`
- end: `0x984d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateGlobalOptionsList`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9780`

## pseudocode

```c

```

## disassembly

```asm
0x9780  ldarg.0
0x9781  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::Clear()
0x9786  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x978b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9790  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9795  stloc.0
0x9796  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x979b  ldc.i4.1
0x979c  ldc.i4.1
0x979d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetByIdDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSets(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetGlobalFilters, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetTypeFilters)
0x97a2  ldarg.0
0x97a3  ldsfld   string [mscorlib]System.String::Empty
0x97a8  ldsfld   string [mscorlib]System.String::Empty
0x97ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x97b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>>::GetEnumerator()
0x97b7  stloc.1
0x97b8  br.s     loc_980B
0x97ba  ldloc.1
0x97bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>>::get_Current()
0x97c0  stloc.2
0x97c1  ldloca.s 2
0x97c3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::get_Key()
0x97c8  stloc.3
0x97c9  ldloc.3
0x97ca  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::principalobjectaccessreadsnapshot_objecttypecode
0x97cf  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x97d4  brtrue.s loc_980B
0x97d6  ldloc.3
0x97d7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::recordcountsnapshot_objecttypecode
0x97dc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x97e1  brtrue.s loc_980B
0x97e3  ldloca.s 2
0x97e5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::get_Value()
0x97ea  stloc.s  4
0x97ec  ldarg.0
0x97ed  ldloc.s  4
0x97ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_DisplayNames()
0x97f4  ldloc.0
0x97f5  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x97fa  ldloca.s 3
0x97fc  ldstr    aB// "B"
0x9801  call     instance string [mscorlib]System.Guid::ToString(string)
0x9806  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x980b  ldloc.1
0x980c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9811  brtrue.s loc_97BA
0x9813  leave.s  loc_981F
0x9815  ldloc.1
0x9816  brfalse.s loc_981E
0x9818  ldloc.1
0x9819  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x981e  endfinally
0x981f  ldarg.0
0x9820  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x9825  ldc.i4.0
0x9826  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x982b  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x9830  ldc.i4.1
0x9831  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_Sorting(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x9836  ldarg.0
0x9837  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x983c  ldc.i4.0
0x983d  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9842  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x9847  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::ExecuteSort()
0x984c  ret
```
