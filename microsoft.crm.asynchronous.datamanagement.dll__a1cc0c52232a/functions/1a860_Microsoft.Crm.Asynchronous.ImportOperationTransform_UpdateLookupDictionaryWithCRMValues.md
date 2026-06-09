# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateLookupDictionaryWithCRMValues

- ea: `0x1a860`
- end: `0x1aa51`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateLookupDictionaryWithCRMValues`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19ee0`

## callees

- `0xaab0`
- `0x1a260`
- `0x1a860`
- `0x1afd0`

## pseudocode

```c

```

## disassembly

```asm
0x1a860  ldarg.1
0x1a861  brfalse  loc_1AA50
0x1a866  ldarg.1
0x1a867  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1a86c  brfalse  loc_1AA50
0x1a871  ldarg.1
0x1a872  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1a877  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1a87c  ldc.i4.0
0x1a87d  ble      loc_1AA50
0x1a882  ldc.i4.0
0x1a883  stloc.0
0x1a884  br       loc_1AA3F
0x1a889  ldsfld   string [mscorlib]System.String::Empty
0x1a88e  stloc.1
0x1a88f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a894  stloc.2
0x1a895  ldarg.1
0x1a896  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1a89b  ldloc.0
0x1a89c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x1a8a1  stloc.3
0x1a8a2  ldloc.3
0x1a8a3  brfalse  loc_1AA3B
0x1a8a8  ldsfld   string [mscorlib]System.String::Empty
0x1a8ad  stloc.s  4
0x1a8af  ldloc.3
0x1a8b0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1a8b5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x1a8ba  stloc.s  5
0x1a8bc  br.s     loc_1A91B
0x1a8be  ldloc.s  5
0x1a8c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x1a8c5  stloc.s  6
0x1a8c7  ldloca.s 6
0x1a8c9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1a8ce  stloc.s  4
0x1a8d0  ldloc.s  4
0x1a8d2  ldarg.s  4
0x1a8d4  ldc.i4.0
0x1a8d5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1a8da  brfalse.s loc_1A91B
0x1a8dc  ldarg.0
0x1a8dd  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1a8e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1a8e7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1a8ec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a8f1  ldloc.3
0x1a8f2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1a8f7  ldc.i4.1
0x1a8f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1a8fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x1a902  ldloc.s  4
0x1a904  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x1a909  stloc.s  7
0x1a90b  ldarg.0
0x1a90c  ldloca.s 6
0x1a90e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1a913  ldloc.s  7
0x1a915  call     instance string Microsoft.Crm.Asynchronous.ImportOperationTransform::GetPropertyValue(object attribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x1a91a  stloc.1
0x1a91b  ldloc.s  5
0x1a91d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a922  brtrue.s loc_1A8BE
0x1a924  leave.s  loc_1A932
0x1a926  ldloc.s  5
0x1a928  brfalse.s loc_1A931
0x1a92a  ldloc.s  5
0x1a92c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a931  endfinally
0x1a932  ldloc.3
0x1a933  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1a938  stloc.2
0x1a939  ldloc.1
0x1a93a  brfalse  loc_1AA3B
0x1a93f  ldloc.1
0x1a940  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a945  ldc.i4.0
0x1a946  ble      loc_1AA3B
0x1a94b  ldarg.2
0x1a94c  ldloc.1
0x1a94d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::ContainsKey(var<u1>)
0x1a952  brfalse.s loc_1A99C
0x1a954  ldarg.2
0x1a955  ldloc.1
0x1a956  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Item(void)
0x1a95b  brfalse.s loc_1A965
0x1a95d  ldarg.3
0x1a95e  call     bool Microsoft.Crm.Asynchronous.ImportOperationTransform::BypassDuplicateForSpecificEntities(string entityName)
0x1a963  brfalse.s loc_1A980
0x1a965  ldarg.2
0x1a966  ldloc.1
0x1a967  ldarg.3
0x1a968  ldloc.2
0x1a969  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1a96e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::set_Item(var<u1>, !!T0)
0x1a973  ldarg.0
0x1a974  ldfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.ImportOperation::_throughputCounter
0x1a979  call     void Microsoft.Crm.Asynchronous.ImportOperation::IncrementPerfCounter(class [System]System.Diagnostics.PerformanceCounter pc)
0x1a97e  br.s     loc_1A99C
0x1a980  ldarg.2
0x1a981  ldloc.1
0x1a982  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Item(void)
0x1a987  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1a98c  ldloc.2
0x1a98d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a992  brfalse.s loc_1A99C
0x1a994  ldarg.2
0x1a995  ldloc.1
0x1a996  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Remove(var<u1>)
0x1a99b  pop
0x1a99c  ldarg.2
0x1a99d  ldstr    asc_2F8EE// "{"
0x1a9a2  ldloc.1
0x1a9a3  ldstr    asc_2F8F2// "}"
0x1a9a8  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a9ad  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::ContainsKey(var<u1>)
0x1a9b2  brfalse  loc_1AA3B
0x1a9b7  ldarg.2
0x1a9b8  ldstr    asc_2F8EE// "{"
0x1a9bd  ldloc.1
0x1a9be  ldstr    asc_2F8F2// "}"
0x1a9c3  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a9c8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Item(void)
0x1a9cd  brfalse.s loc_1A9D7
0x1a9cf  ldarg.3
0x1a9d0  call     bool Microsoft.Crm.Asynchronous.ImportOperationTransform::BypassDuplicateForSpecificEntities(string entityName)
0x1a9d5  brfalse.s loc_1AA01
0x1a9d7  ldarg.2
0x1a9d8  ldstr    asc_2F8EE// "{"
0x1a9dd  ldloc.1
0x1a9de  ldstr    asc_2F8F2// "}"
0x1a9e3  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a9e8  ldarg.3
0x1a9e9  ldloc.2
0x1a9ea  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1a9ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::set_Item(var<u1>, !!T0)
0x1a9f4  ldarg.0
0x1a9f5  ldfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.ImportOperation::_throughputCounter
0x1a9fa  call     void Microsoft.Crm.Asynchronous.ImportOperation::IncrementPerfCounter(class [System]System.Diagnostics.PerformanceCounter pc)
0x1a9ff  br.s     loc_1AA3B
0x1aa01  ldarg.2
0x1aa02  ldstr    asc_2F8EE// "{"
0x1aa07  ldloc.1
0x1aa08  ldstr    asc_2F8F2// "}"
0x1aa0d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1aa12  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Item(void)
0x1aa17  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1aa1c  ldloc.2
0x1aa1d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1aa22  brfalse.s loc_1AA3B
0x1aa24  ldarg.2
0x1aa25  ldstr    asc_2F8EE// "{"
0x1aa2a  ldloc.1
0x1aa2b  ldstr    asc_2F8F2// "}"
0x1aa30  call     string [mscorlib]System.String::Concat(string, string, string)
0x1aa35  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Remove(var<u1>)
0x1aa3a  pop
0x1aa3b  ldloc.0
0x1aa3c  ldc.i4.1
0x1aa3d  add
0x1aa3e  stloc.0
0x1aa3f  ldloc.0
0x1aa40  ldarg.1
0x1aa41  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1aa46  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1aa4b  blt      loc_1A889
0x1aa50  ret
```
