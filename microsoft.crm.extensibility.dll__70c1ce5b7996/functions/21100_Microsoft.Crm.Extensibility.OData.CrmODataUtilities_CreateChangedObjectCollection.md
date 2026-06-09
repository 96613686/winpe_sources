# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateChangedObjectCollection

- ea: `0x21100`
- end: `0x211fe`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateChangedObjectCollection`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1d5e0`

## callees

- `0xf740`
- `0xfab0`
- `0x13460`
- `0x17780`
- `0x17800`
- `0x20200`
- `0x20360`
- `0x21100`
- `0x21270`
- `0x24e10`
- `0x28fe0`

## pseudocode

```c

```

## disassembly

```asm
0x21100  ldarg.2
0x21101  ldarg.3
0x21102  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21107  stloc.0
0x21108  ldarg.0
0x21109  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x2110e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x21113  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x21118  stloc.1
0x21119  ldloc.0
0x2111a  ldc.i4.0
0x2111b  ldarg.0
0x2111c  call     int32 Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x21121  ldarg.1
0x21122  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_PagingCookie()
0x21127  ldarg.0
0x21128  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x2112d  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SerializePagingCookie(int32 pageNumber, string crmPagingCookie, bool isTracking)
0x21132  ldarg.1
0x21133  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_MoreRecords()
0x21138  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmChangedObjectCollection::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType entityType, int32 totalRecordCount, string pagingCookie, bool hasMoreRecords)
0x2113d  stloc.2
0x2113e  ldarg.1
0x2113f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChangesCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_Changes()
0x21144  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem>::get_Count()
0x21149  ldc.i4.0
0x2114a  ble      loc_211F0
0x2114f  ldarg.1
0x21150  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChangesCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_Changes()
0x21155  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem>::GetEnumerator()
0x2115a  stloc.3
0x2115b  br.s     loc_211D9
0x2115d  ldloc.3
0x2115e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem>::get_Current()
0x21163  stloc.s  4
0x21165  ldloc.s  4
0x21167  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ChangeType [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem::get_Type()
0x2116c  brtrue.s loc_21196
0x2116e  ldloc.s  4
0x21170  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.NewOrUpdatedItem
0x21175  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.NewOrUpdatedItem::get_NewOrUpdatedEntity()
0x2117a  ldarg.2
0x2117b  ldarg.3
0x2117c  ldc.i4.1
0x2117d  ldarg.s  4
0x2117f  ldloc.1
0x21180  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObject(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isDeltaEntity, [opt] bool fillAllProperties, [opt] bool noLock)
0x21185  stloc.s  5
0x21187  ldloc.2
0x21188  ldloc.s  5
0x2118a  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmChangedEntityObject
0x2118f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmChangedObject>::Add(var<u1>)
0x21194  br.s     loc_211D9
0x21196  ldloc.0
0x21197  newobj   instance void [System.Web.OData]System.Web.OData.EdmDeltaDeletedEntityObject::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType)
0x2119c  stloc.s  6
0x2119e  ldloc.s  4
0x211a0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemovedOrDeletedItem
0x211a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemovedOrDeletedItem::get_RemovedItem()
0x211aa  stloc.s  7
0x211ac  ldloc.s  6
0x211ae  ldloc.s  7
0x211b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x211b5  stloc.s  8
0x211b7  ldloca.s 8
0x211b9  constrained. [mscorlib]System.Guid
0x211bf  callvirt instance string [mscorlib]System.Object::ToString()
0x211c4  callvirt instance void [System.Web.OData]System.Web.OData.EdmDeltaDeletedEntityObject::set_Id(string)
0x211c9  ldloc.s  6
0x211cb  ldc.i4.0
0x211cc  callvirt instance void [System.Web.OData]System.Web.OData.EdmDeltaDeletedEntityObject::set_Reason(valuetype [Microsoft.OData.Core]Microsoft.OData.DeltaDeletedEntryReason)
0x211d1  ldloc.2
0x211d2  ldloc.s  6
0x211d4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmChangedObject>::Add(var<u1>)
0x211d9  ldloc.3
0x211da  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x211df  brtrue   loc_2115D
0x211e4  leave.s  loc_211F0
0x211e6  ldloc.3
0x211e7  brfalse.s loc_211EF
0x211e9  ldloc.3
0x211ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x211ef  endfinally
0x211f0  ldloc.2
0x211f1  ldarg.1
0x211f2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_DataToken()
0x211f7  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmEdmChangedObjectCollection::set_DeltaToken(string value)
0x211fc  ldloc.2
0x211fd  ret
```
