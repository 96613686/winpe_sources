# Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::VerifyOneDriveLocationAlreadyExists

- ea: `0x17b260`
- end: `0x17b415`
- name: `Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::VerifyOneDriveLocationAlreadyExists`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x17b260`
- `0x17c3c0`
- `0x17c910`

## string_xrefs

- `0x17b263`: `servicetype`
- `0x17b270`: `servicetype`
- `0x17b27d`: `servicetype`
- `0x17b387`: `servicetype`
- `0x17b405`: `Please enable One Drive for Business feature to create ODB site`
- `0x17b2db`: `VerifyOneDriveLocationAlreadyExists`
- `0x17b3ea`: `VerifyOneDriveLocationAlreadyExists`
- `0x17b2e5`: `You cannot create location with this service type`

## pseudocode

```c

```

## disassembly

```asm
0x17b260  ldc.i4.0
0x17b261  stloc.0
0x17b262  ldarg.1
0x17b263  ldstr    aServicetype// "servicetype"
0x17b268  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17b26d  brtrue.s loc_17B292
0x17b26f  ldarg.1
0x17b270  ldstr    aServicetype// "servicetype"
0x17b275  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x17b27a  brfalse.s loc_17B292
0x17b27c  ldarg.1
0x17b27d  ldstr    aServicetype// "servicetype"
0x17b282  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x17b287  callvirt instance string [mscorlib]System.Object::ToString()
0x17b28c  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x17b291  stloc.0
0x17b292  ldloc.0
0x17b293  ldc.i4.1
0x17b294  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b299  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b29e  beq.s    loc_17B2B1
0x17b2a0  ldloc.0
0x17b2a1  ldc.i4.2
0x17b2a2  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b2a7  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b2ac  bne.un   loc_17B414
0x17b2b1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17b2b6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17b2bb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OneDriveIntegration()
0x17b2c0  ldarg.2
0x17b2c1  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17b2c6  brfalse  loc_17B400
0x17b2cb  ldloc.0
0x17b2cc  ldc.i4.2
0x17b2cd  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b2d2  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b2d7  bne.un.s loc_17B2F1
0x17b2d9  ldc.i4.0
0x17b2da  ldarg.2
0x17b2db  ldstr    aVerifyonedrive// "VerifyOneDriveLocationAlreadyExists"
0x17b2e0  ldc.i4   0x80060736
0x17b2e5  ldstr    aYouCannotCreat_0// "You cannot create location with this se"...
0x17b2ea  ldnull
0x17b2eb  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17b2f0  throw
0x17b2f1  ldarg.1
0x17b2f2  ldstr    aRegardingobjec_0// "regardingobjectid"
0x17b2f7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17b2fc  brtrue   loc_17B414
0x17b301  ldarg.1
0x17b302  ldstr    aRegardingobjec_0// "regardingobjectid"
0x17b307  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x17b30c  brfalse  loc_17B414
0x17b311  ldarg.1
0x17b312  ldstr    aUserid_3// "userid"
0x17b317  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17b31c  brtrue   loc_17B414
0x17b321  ldarg.1
0x17b322  ldstr    aUserid_3// "userid"
0x17b327  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x17b32c  brfalse  loc_17B414
0x17b331  ldstr    aSharepointdocu_4// "SharePointDocumentLocation"
0x17b336  ldarg.2
0x17b337  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x17b33c  stloc.1
0x17b33d  ldloc.1
0x17b33e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x17b343  ldstr    aRegardingobjec_0// "regardingobjectid"
0x17b348  ldc.i4.0
0x17b349  ldarg.1
0x17b34a  ldstr    aRegardingobjec_0// "regardingobjectid"
0x17b34f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17b354  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x17b359  pop
0x17b35a  ldloc.1
0x17b35b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x17b360  ldstr    aUserid_3// "userid"
0x17b365  ldc.i4.0
0x17b366  ldarg.1
0x17b367  ldstr    aUserid_3// "userid"
0x17b36c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17b371  unbox.any [mscorlib]System.Guid
0x17b376  box      [mscorlib]System.Guid
0x17b37b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x17b380  pop
0x17b381  ldloc.1
0x17b382  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x17b387  ldstr    aServicetype// "servicetype"
0x17b38c  ldc.i4.0
0x17b38d  ldc.i4.1
0x17b38e  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b393  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b398  box      [mscorlib]System.Int32
0x17b39d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x17b3a2  pop
0x17b3a3  ldloc.1
0x17b3a4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x17b3a9  ldstr    aStatuscode// "statuscode"
0x17b3ae  ldc.i4.0
0x17b3af  ldc.i4.1
0x17b3b0  box      [mscorlib]System.Int32
0x17b3b5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x17b3ba  pop
0x17b3bb  ldloc.1
0x17b3bc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x17b3c1  ldstr    aStatecode// "statecode"
0x17b3c6  ldc.i4.0
0x17b3c7  ldc.i4.0
0x17b3c8  box      [mscorlib]System.Int32
0x17b3cd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x17b3d2  pop
0x17b3d3  ldarg.0
0x17b3d4  ldloc.1
0x17b3d5  ldarg.2
0x17b3d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17b3db  stloc.2
0x17b3dc  ldloc.2
0x17b3dd  brfalse.s loc_17B414
0x17b3df  ldloc.2
0x17b3e0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x17b3e5  ldc.i4.0
0x17b3e6  ble.s    loc_17B414
0x17b3e8  ldc.i4.0
0x17b3e9  ldarg.2
0x17b3ea  ldstr    aVerifyonedrive// "VerifyOneDriveLocationAlreadyExists"
0x17b3ef  ldc.i4   0x80060735
0x17b3f4  ldstr    aMoreThanOneOdb// "More than one ODB (OneDrive for Busines"...
0x17b3f9  ldnull
0x17b3fa  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17b3ff  throw
0x17b400  ldc.i4   0x8006072E
0x17b405  ldstr    aPleaseEnableOn// "Please enable One Drive for Business fe"...
0x17b40a  ldc.i4.s 9
0x17b40c  ldarg.2
0x17b40d  ldc.i4.0
0x17b40e  ldnull
0x17b40f  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17b414  ret
```
