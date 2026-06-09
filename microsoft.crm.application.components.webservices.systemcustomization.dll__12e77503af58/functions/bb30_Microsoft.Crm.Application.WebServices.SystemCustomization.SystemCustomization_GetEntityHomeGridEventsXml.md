# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetEntityHomeGridEventsXml

- ea: `0xbb30`
- end: `0xbc62`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetEntityHomeGridEventsXml`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbb30`

## string_xrefs

- `0xbb78`: `CustomControlDefaultConfig`
- `0xbb92`: `eventsxml`
- `0xbbea`: `eventsxml`
- `0xbbf8`: `eventsxml`
- `0xbc1a`: `eventsxml`
- `0xbc29`: `<customControlDefaultConfig>`
- `0xbc38`: `</customControlDefaultConfig>`

## pseudocode

```c

```

## disassembly

```asm
0xbb30  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbb35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xbb3a  ldc.i4.0
0xbb3b  ldc.i4.0
0xbb3c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xbb41  stloc.0
0xbb42  ldloc.0
0xbb43  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbb48  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xbb4d  ldc.i4.0
0xbb4e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xbb53  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xbb58  ldarg.1
0xbb59  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbb5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0xbb63  stloc.1
0xbb64  ldloc.1
0xbb65  brtrue.s loc_BB72
0xbb67  ldstr    aUnableToFindEn// "Unable to find entity metadata"
0xbb6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xbb71  throw
0xbb72  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::.ctor()
0xbb77  stloc.2
0xbb78  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xbb7d  ldloc.0
0xbb7e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xbb83  stloc.3
0xbb84  ldloc.3
0xbb85  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xbb8a  ldc.i4.1
0xbb8b  newarr   [mscorlib]System.String
0xbb90  dup
0xbb91  ldc.i4.0
0xbb92  ldstr    aEventsxml// "eventsxml"
0xbb97  stelem.ref
0xbb98  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xbb9d  ldloc.3
0xbb9e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbba3  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xbba8  ldc.i4.0
0xbba9  ldloc.1
0xbbaa  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xbbaf  box      [mscorlib]System.Int32
0xbbb4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xbbb9  pop
0xbbba  ldloc.2
0xbbbb  ldloc.3
0xbbbc  ldloc.0
0xbbbd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbbc2  stloc.s  4
0xbbc4  ldloc.s  4
0xbbc6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xbbcb  brtrue.s loc_BBD9
0xbbcd  ldstr    aEntityFormForm// "<entity><form></form></entity>"
0xbbd2  stloc.s  6
0xbbd4  leave    loc_BC5F
0xbbd9  ldloc.s  4
0xbbdb  ldc.i4.0
0xbbdc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xbbe1  stloc.s  5
0xbbe3  ldloc.s  5
0xbbe5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xbbea  ldstr    aEventsxml// "eventsxml"
0xbbef  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0xbbf4  brfalse.s loc_BC04
0xbbf6  ldloc.s  5
0xbbf8  ldstr    aEventsxml// "eventsxml"
0xbbfd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc02  brtrue.s loc_BC0D
0xbc04  ldstr    aEntityFormForm// "<entity><form></form></entity>"
0xbc09  stloc.s  6
0xbc0b  leave.s  loc_BC5F
0xbc0d  ldloc.0
0xbc0e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xbc13  ldstr    aEntityForm// "<entity><form>"
0xbc18  ldloc.s  5
0xbc1a  ldstr    aEventsxml// "eventsxml"
0xbc1f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc24  callvirt instance string [mscorlib]System.Object::ToString()
0xbc29  ldstr    aCustomcontrold_0// "<customControlDefaultConfig>"
0xbc2e  ldstr    asc_10614// ""
0xbc33  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xbc38  ldstr    aCustomcontrold_1// "</customControlDefaultConfig>"
0xbc3d  ldstr    asc_10614// ""
0xbc42  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xbc47  ldstr    aFormEntity// "</form></entity>"
0xbc4c  call     string [mscorlib]System.String::Concat(string, string, string)
0xbc51  stloc.s  6
0xbc53  leave.s  loc_BC5F
0xbc55  ldloc.0
0xbc56  brfalse.s loc_BC5E
0xbc58  ldloc.0
0xbc59  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc5e  endfinally
0xbc5f  ldloc.s  6
0xbc61  ret
```
