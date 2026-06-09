# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSdkMessageDetails

- ea: `0x6230`
- end: `0x635b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSdkMessageDetails`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6100`
- `0x61a0`
- `0x6360`

## callees

- `0x6230`

## pseudocode

```c

```

## disassembly

```asm
0x6230  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x6235  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x623a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WorkflowOobSdkMsgSupport()
0x623f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6244  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6249  ldstr    aSdkmessage// "sdkmessage"
0x624e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6253  stloc.0
0x6254  ldloc.0
0x6255  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x625a  ldstr    aSdkmessageid// "sdkmessageid"
0x625f  ldc.i4.0
0x6260  ldarg.1
0x6261  box      [mscorlib]System.Guid
0x6266  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x626b  ldloc.0
0x626c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x6271  ldstr    aName// "name"
0x6276  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x627b  ldloc.0
0x627c  ldstr    aSdkmessagefilt// "sdkmessagefilter"
0x6281  ldstr    aSdkmessageid// "sdkmessageid"
0x6286  ldstr    aSdkmessageid// "sdkmessageid"
0x628b  ldc.i4.0
0x628c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6291  stloc.1
0x6292  brfalse.s loc_62B8
0x6294  ldarg.3
0x6295  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x629a  brtrue.s loc_62B8
0x629c  ldloc.1
0x629d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x62a2  ldstr    aSdkmessagefilt_0// "sdkmessagefilterid"
0x62a7  ldc.i4.0
0x62a8  ldarg.3
0x62a9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x62ae  box      [mscorlib]System.Guid
0x62b3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x62b8  ldloc.1
0x62b9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_Columns()
0x62be  ldc.i4.1
0x62bf  newarr   [mscorlib]System.String
0x62c4  dup
0x62c5  ldc.i4.0
0x62c6  ldstr    aPrimaryobjectt// "primaryobjecttypecode"
0x62cb  stelem.ref
0x62cc  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x62d1  ldloc.1
0x62d2  ldstr    aSdkmessagefilt// "sdkmessagefilter"
0x62d7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::set_Alias(string)
0x62dc  ldloc.0
0x62dd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62e7  stloc.2
0x62e8  ldloc.2
0x62e9  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x62ee  ldc.i4.0
0x62ef  ble.s    loc_635A
0x62f1  ldloc.2
0x62f2  ldc.i4.0
0x62f3  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x62f8  stloc.3
0x62f9  ldloc.3
0x62fa  brfalse.s loc_635A
0x62fc  ldarg.2
0x62fd  ldloc.3
0x62fe  ldstr    aName// "name"
0x6303  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6308  callvirt instance string [mscorlib]System.Object::ToString()
0x630d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::set_SdkMessageName(string)
0x6312  ldloc.3
0x6313  ldstr    aSdkmessagefilt_1// "sdkmessagefilter.primaryobjecttypecode"
0x6318  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string)
0x631d  brfalse.s loc_635A
0x631f  ldloc.3
0x6320  ldstr    aSdkmessagefilt_1// "sdkmessagefilter.primaryobjecttypecode"
0x6325  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x632a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x632f  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x6334  stloc.s  4
0x6336  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x633b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6340  ldloc.s  4
0x6342  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x6347  stloc.s  5
0x6349  ldloc.s  5
0x634b  brfalse.s loc_635A
0x634d  ldarg.2
0x634e  ldloc.s  5
0x6350  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x6355  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::set_SdkMessageEntityName(string)
0x635a  ret
```
