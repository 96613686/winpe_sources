# Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::ValidateInputsForUpdate

- ea: `0x17bb00`
- end: `0x17bd3f`
- name: `Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::ValidateInputsForUpdate`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x17bb00`
- `0x17c3c0`
- `0x17c910`

## string_xrefs

- `0x17bb01`: `servicetype`
- `0x17bb0e`: `servicetype`
- `0x17bb2b`: `servicetype`
- `0x17bb48`: `servicetype`
- `0x17bb58`: `servicetype`
- `0x17bb75`: `servicetype`
- `0x17bba9`: `servicetype`
- `0x17bbfa`: `Please enable One Drive for Business feature to create ODB site`
- `0x17bbc7`: `ValidateInputsForUpdate`
- `0x17bbdf`: `ValidateInputsForUpdate`
- `0x17bbd1`: `You cannot update location with this service type`
- `0x17bbe9`: `You cannot update or delete SharePoint Document Location of type ODB(OneDrive for Business)`

## pseudocode

```c

```

## disassembly

```asm
0x17bb00  ldarg.1
0x17bb01  ldstr    aServicetype// "servicetype"
0x17bb06  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bb0b  brtrue.s loc_17BB47
0x17bb0d  ldarg.1
0x17bb0e  ldstr    aServicetype// "servicetype"
0x17bb13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17bb18  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb1d  ldc.i4.1
0x17bb1e  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17bb23  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb28  beq.s    loc_17BB91
0x17bb2a  ldarg.1
0x17bb2b  ldstr    aServicetype// "servicetype"
0x17bb30  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17bb35  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb3a  ldc.i4.2
0x17bb3b  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17bb40  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb45  beq.s    loc_17BB91
0x17bb47  ldarg.2
0x17bb48  ldstr    aServicetype// "servicetype"
0x17bb4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x17bb52  brtrue   loc_17BC09
0x17bb57  ldarg.2
0x17bb58  ldstr    aServicetype// "servicetype"
0x17bb5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17bb62  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb67  ldc.i4.1
0x17bb68  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17bb6d  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb72  beq.s    loc_17BB91
0x17bb74  ldarg.2
0x17bb75  ldstr    aServicetype// "servicetype"
0x17bb7a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17bb7f  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb84  ldc.i4.2
0x17bb85  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17bb8a  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bb8f  bne.un.s loc_17BC09
0x17bb91  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17bb96  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17bb9b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OneDriveIntegration()
0x17bba0  ldarg.3
0x17bba1  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17bba6  brfalse.s loc_17BBF5
0x17bba8  ldarg.1
0x17bba9  ldstr    aServicetype// "servicetype"
0x17bbae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17bbb3  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bbb8  ldc.i4.2
0x17bbb9  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17bbbe  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bbc3  bne.un.s loc_17BBDD
0x17bbc5  ldc.i4.0
0x17bbc6  ldarg.3
0x17bbc7  ldstr    aValidateinputs// "ValidateInputsForUpdate"
0x17bbcc  ldc.i4   0x80060736
0x17bbd1  ldstr    aYouCannotUpdat_2// "You cannot update location with this se"...
0x17bbd6  ldnull
0x17bbd7  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17bbdc  throw
0x17bbdd  ldc.i4.0
0x17bbde  ldarg.3
0x17bbdf  ldstr    aValidateinputs// "ValidateInputsForUpdate"
0x17bbe4  ldc.i4   0x80060736
0x17bbe9  ldstr    aYouCannotUpdat_3// "You cannot update or delete SharePoint "...
0x17bbee  ldnull
0x17bbef  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17bbf4  throw
0x17bbf5  ldc.i4   0x8006072E
0x17bbfa  ldstr    aPleaseEnableOn// "Please enable One Drive for Business fe"...
0x17bbff  ldc.i4.s 9
0x17bc01  ldarg.3
0x17bc02  ldc.i4.0
0x17bc03  ldnull
0x17bc04  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17bc09  ldarg.1
0x17bc0a  ldstr    aRelativeurl// "relativeurl"
0x17bc0f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bc14  brtrue.s loc_17BC31
0x17bc16  ldarg.1
0x17bc17  ldstr    aRelativeurl// "relativeurl"
0x17bc1c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17bc21  callvirt instance string [mscorlib]System.Object::ToString()
0x17bc26  ldstr    aSharepointdocu_4// "SharePointDocumentLocation"
0x17bc2b  ldarg.3
0x17bc2c  call     void class Microsoft.Crm.ObjectModel.SharePointProvisioningHelperServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::ValidateSpecialCharaterInRelativeUrl(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17bc31  ldarg.1
0x17bc32  ldstr    aAbsoluteurl// "absoluteurl"
0x17bc37  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bc3c  brtrue.s loc_17BC54
0x17bc3e  ldarg.1
0x17bc3f  ldstr    aAbsoluteurl// "absoluteurl"
0x17bc44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17bc49  callvirt instance string [mscorlib]System.Object::ToString()
0x17bc4e  ldarg.3
0x17bc4f  call     void class Microsoft.Crm.ObjectModel.SharePointProvisioningHelperServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::CheckConsecutiveSlashes(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17bc54  ldarg.2
0x17bc55  ldarg.1
0x17bc56  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Merge(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x17bc5b  stloc.0
0x17bc5c  ldloc.0
0x17bc5d  ldstr    aAbsoluteurl// "absoluteurl"
0x17bc62  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bc67  brfalse.s loc_17BC86
0x17bc69  ldloc.0
0x17bc6a  ldstr    aRelativeurl// "relativeurl"
0x17bc6f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bc74  brfalse.s loc_17BC86
0x17bc76  ldstr    aBothAbsoluteur// "Both absoluteurl and relativeurl cannot"...
0x17bc7b  ldc.i4   0x80048149
0x17bc80  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string, int32)
0x17bc85  throw
0x17bc86  ldloc.0
0x17bc87  ldstr    aRelativeurl// "relativeurl"
0x17bc8c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bc91  brtrue.s loc_17BCAB
0x17bc93  ldloc.0
0x17bc94  ldstr    aAbsoluteurl// "absoluteurl"
0x17bc99  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bc9e  brtrue.s loc_17BCAB
0x17bca0  ldstr    aSharepointdocu_6// "SharePointDocumentLocation cannot have "...
0x17bca5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x17bcaa  throw
0x17bcab  ldloc.0
0x17bcac  ldstr    aAbsoluteurl// "absoluteurl"
0x17bcb1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bcb6  brtrue.s loc_17BCD0
0x17bcb8  ldloc.0
0x17bcb9  ldstr    aParentsiteorlo// "parentsiteorlocation"
0x17bcbe  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bcc3  brtrue.s loc_17BCD0
0x17bcc5  ldstr    aSharepointdocu_7// "SharePointDocumentLocation cannot have "...
0x17bcca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x17bccf  throw
0x17bcd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17bcd5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17bcda  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OneNoteIntegration()
0x17bcdf  ldarg.3
0x17bce0  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17bce5  brfalse.s loc_17BD3E
0x17bce7  ldarg.1
0x17bce8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x17bced  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x17bcf2  ldstr    aLocationtype// "locationtype"
0x17bcf7  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x17bcfc  brfalse.s loc_17BD3E
0x17bcfe  ldloc.0
0x17bcff  ldstr    aRegardingobjec_0// "regardingobjectid"
0x17bd04  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bd09  brtrue.s loc_17BD3E
0x17bd0b  ldloc.0
0x17bd0c  ldstr    aLocationtype// "locationtype"
0x17bd11  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17bd16  brtrue.s loc_17BD3E
0x17bd18  ldloc.0
0x17bd19  ldstr    aLocationtype// "locationtype"
0x17bd1e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17bd23  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bd28  ldc.i4.1
0x17bd29  box      [Microsoft.Crm]Microsoft.Crm.SharePointDocumentLocationType
0x17bd2e  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17bd33  bne.un.s loc_17BD3E
0x17bd35  ldarg.0
0x17bd36  ldloc.0
0x17bd37  ldarg.3
0x17bd38  ldc.i4.1
0x17bd39  call     instance void class Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1<var<u1>>::ValidateOneNoteDocumentLocation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x17bd3e  ret
```
