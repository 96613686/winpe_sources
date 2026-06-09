# Microsoft.Crm.ObjectModel.SharePointSiteServiceInternal`1::ValidateInputsForUpdate

- ea: `0x17acb0`
- end: `0x17ae71`
- name: `Microsoft.Crm.ObjectModel.SharePointSiteServiceInternal`1::ValidateInputsForUpdate`
- size: `449`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x17acb0`
- `0x17c3c0`
- `0x17c910`

## string_xrefs

- `0x17acb3`: `servicetype`
- `0x17acc0`: `servicetype`
- `0x17ada7`: `servicetype`
- `0x17adb4`: `servicetype`
- `0x17ad43`: `Please enable One Drive for Business feature to create ODB site`
- `0x17ad2e`: `You cannot update or delete One Drive For Business site`
- `0x17add5`: `You cannot update or delete One Drive For Business site`
- `0x17ad13`: `ValidateInputsForUpdate`
- `0x17ad1d`: `You cannot update site with this service type`

## pseudocode

```c

```

## disassembly

```asm
0x17acb0  ldc.i4.0
0x17acb1  stloc.0
0x17acb2  ldarg.2
0x17acb3  ldstr    aServicetype// "servicetype"
0x17acb8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x17acbd  brtrue.s loc_17ACD0
0x17acbf  ldarg.2
0x17acc0  ldstr    aServicetype// "servicetype"
0x17acc5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17acca  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17accf  stloc.0
0x17acd0  ldloc.0
0x17acd1  ldc.i4.1
0x17acd2  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17acd7  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17acdc  beq.s    loc_17ACEC
0x17acde  ldloc.0
0x17acdf  ldc.i4.2
0x17ace0  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17ace5  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17acea  bne.un.s loc_17AD52
0x17acec  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17acf1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17acf6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OneDriveIntegration()
0x17acfb  ldarg.3
0x17acfc  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17ad01  brfalse.s loc_17AD3E
0x17ad03  ldloc.0
0x17ad04  ldc.i4.2
0x17ad05  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17ad0a  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17ad0f  bne.un.s loc_17AD29
0x17ad11  ldc.i4.3
0x17ad12  ldarg.3
0x17ad13  ldstr    aValidateinputs// "ValidateInputsForUpdate"
0x17ad18  ldc.i4   0x8006072F
0x17ad1d  ldstr    aYouCannotUpdat_0// "You cannot update site with this servic"...
0x17ad22  ldnull
0x17ad23  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17ad28  throw
0x17ad29  ldc.i4   0x8006072F
0x17ad2e  ldstr    aYouCannotUpdat// "You cannot update or delete One Drive F"...
0x17ad33  ldc.i4.4
0x17ad34  ldarg.3
0x17ad35  ldc.i4.3
0x17ad36  ldnull
0x17ad37  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17ad3c  br.s     loc_17AD52
0x17ad3e  ldc.i4   0x8006072E
0x17ad43  ldstr    aPleaseEnableOn// "Please enable One Drive for Business fe"...
0x17ad48  ldc.i4.s 9
0x17ad4a  ldarg.3
0x17ad4b  ldc.i4.3
0x17ad4c  ldnull
0x17ad4d  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17ad52  ldarg.1
0x17ad53  ldstr    aRelativeurl// "relativeurl"
0x17ad58  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ad5d  brtrue.s loc_17AD7A
0x17ad5f  ldarg.1
0x17ad60  ldstr    aRelativeurl// "relativeurl"
0x17ad65  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17ad6a  callvirt instance string [mscorlib]System.Object::ToString()
0x17ad6f  ldstr    aSharepointsite// "SharePointSite"
0x17ad74  ldarg.3
0x17ad75  call     void class Microsoft.Crm.ObjectModel.SharePointProvisioningHelperServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::ValidateSpecialCharaterInRelativeUrl(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17ad7a  ldarg.1
0x17ad7b  ldstr    aAbsoluteurl// "absoluteurl"
0x17ad80  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ad85  brtrue.s loc_17AD9E
0x17ad87  ldarg.0
0x17ad88  ldarg.1
0x17ad89  ldstr    aAbsoluteurl// "absoluteurl"
0x17ad8e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17ad93  callvirt instance string [mscorlib]System.Object::ToString()
0x17ad98  ldarg.3
0x17ad99  call     instance void class Microsoft.Crm.ObjectModel.SharePointSiteServiceInternal`1<var<u1>>::ValidateAbsoluteUrlFormat(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17ad9e  ldarg.2
0x17ad9f  ldarg.1
0x17ada0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Merge(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x17ada5  stloc.1
0x17ada6  ldloc.1
0x17ada7  ldstr    aServicetype// "servicetype"
0x17adac  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17adb1  brtrue.s loc_17ADE3
0x17adb3  ldloc.1
0x17adb4  ldstr    aServicetype// "servicetype"
0x17adb9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17adbe  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17adc3  ldc.i4.1
0x17adc4  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17adc9  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17adce  bne.un.s loc_17ADE3
0x17add0  ldc.i4   0x8006072F
0x17add5  ldstr    aYouCannotUpdat// "You cannot update or delete One Drive F"...
0x17adda  ldc.i4.4
0x17addb  ldarg.3
0x17addc  ldc.i4.3
0x17addd  ldnull
0x17adde  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17ade3  ldloc.1
0x17ade4  ldstr    aAbsoluteurl// "absoluteurl"
0x17ade9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17adee  brfalse.s loc_17AE0D
0x17adf0  ldloc.1
0x17adf1  ldstr    aRelativeurl// "relativeurl"
0x17adf6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17adfb  brfalse.s loc_17AE0D
0x17adfd  ldstr    aBothAbsoluteur// "Both absoluteurl and relativeurl cannot"...
0x17ae02  ldc.i4   0x80048149
0x17ae07  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string, int32)
0x17ae0c  throw
0x17ae0d  ldloc.1
0x17ae0e  ldstr    aRelativeurl// "relativeurl"
0x17ae13  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ae18  brtrue.s loc_17AE32
0x17ae1a  ldloc.1
0x17ae1b  ldstr    aAbsoluteurl// "absoluteurl"
0x17ae20  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ae25  brtrue.s loc_17AE32
0x17ae27  ldstr    aSharepointSite// "SharePoint site cannot have both absolu"...
0x17ae2c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x17ae31  throw
0x17ae32  ldloc.1
0x17ae33  ldstr    aParentsite// "parentsite"
0x17ae38  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ae3d  brtrue.s loc_17AE57
0x17ae3f  ldloc.1
0x17ae40  ldstr    aAbsoluteurl// "absoluteurl"
0x17ae45  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ae4a  brtrue.s loc_17AE57
0x17ae4c  ldstr    aSharepointSite_0// "SharePoint site cannot have both absolu"...
0x17ae51  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x17ae56  throw
0x17ae57  ldloc.1
0x17ae58  ldstr    aRelativeurl// "relativeurl"
0x17ae5d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17ae62  brtrue.s loc_17AE70
0x17ae64  ldarg.1
0x17ae65  ldstr    aIsgridpresent// "isgridpresent"
0x17ae6a  ldnull
0x17ae6b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x17ae70  ret
```
