# Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::Delete

- ea: `0x17b510`
- end: `0x17b5b6`
- name: `Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::Delete`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x17b510`
- `0x17c3c0`
- `0x17c910`
- `0x1c5470`

## string_xrefs

- `0x17b51b`: `servicetype`
- `0x17b533`: `servicetype`
- `0x17b541`: `servicetype`
- `0x17b54e`: `servicetype`
- `0x17b59e`: `Please enable One Drive for Business feature to create ODB site`
- `0x17b583`: `SharePointDocumentLocationService Delete`
- `0x17b58d`: `You cannot update or delete SharePoint Document Location of type ODB (OneDrive for Business)`

## pseudocode

```c

```

## disassembly

```asm
0x17b510  ldarg.1
0x17b511  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x17b516  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x17b51b  ldstr    aServicetype// "servicetype"
0x17b520  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x17b525  brfalse  loc_17B5AD
0x17b52a  ldarg.1
0x17b52b  ldc.i4.1
0x17b52c  newarr   [mscorlib]System.String
0x17b531  dup
0x17b532  ldc.i4.0
0x17b533  ldstr    aServicetype// "servicetype"
0x17b538  stelem.ref
0x17b539  ldarg.2
0x17b53a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.ObjectServiceUtility::RetrieveEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker entityMoniker, string[] fields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17b53f  stloc.0
0x17b540  ldloc.0
0x17b541  ldstr    aServicetype// "servicetype"
0x17b546  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x17b54b  brtrue.s loc_17B5AD
0x17b54d  ldloc.0
0x17b54e  ldstr    aServicetype// "servicetype"
0x17b553  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17b558  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b55d  ldc.i4.1
0x17b55e  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b563  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b568  bne.un.s loc_17B5AD
0x17b56a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17b56f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17b574  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OneDriveIntegration()
0x17b579  ldarg.2
0x17b57a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17b57f  brfalse.s loc_17B599
0x17b581  ldc.i4.0
0x17b582  ldarg.2
0x17b583  ldstr    aSharepointdocu_8// "SharePointDocumentLocationService Delet"...
0x17b588  ldc.i4   0x80060736
0x17b58d  ldstr    aYouCannotUpdat_1// "You cannot update or delete SharePoint "...
0x17b592  ldnull
0x17b593  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17b598  throw
0x17b599  ldc.i4   0x8006072E
0x17b59e  ldstr    aPleaseEnableOn// "Please enable One Drive for Business fe"...
0x17b5a3  ldc.i4.s 9
0x17b5a5  ldarg.2
0x17b5a6  ldc.i4.0
0x17b5a7  ldnull
0x17b5a8  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17b5ad  ldarg.0
0x17b5ae  ldarg.1
0x17b5af  ldarg.2
0x17b5b0  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17b5b5  ret
```
