# Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::HandlePostback

- ea: `0x2b0`
- end: `0x454`
- name: `Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::HandlePostback`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf0`

## callees

- `0x2b0`

## string_xrefs

- `0x431`: `XML loaded from the stream returned String.Empty.`
- `0x43b`: `XML loaded from the stream returned String.Empty.`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.1
0x2b1  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x2b6  stloc.0
0x2b7  ldloc.0
0x2b8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2bd  brfalse  loc_428
0x2c2  ldarg.0
0x2c3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2c8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2cd  ldstr    aIid// "iId"
0x2d2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2d7  stloc.1
0x2d8  ldarg.0
0x2d9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2de  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2e3  ldstr    aItemobjectid// "itemObjectId"
0x2e8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ed  stloc.2
0x2ee  ldstr    aCampaign// "campaign"
0x2f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2fd  newobj   instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x302  ldloc.2
0x303  ldloc.1
0x304  ldc.i4   0x10CC
0x309  callvirt instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::SetAssociation(string, string, int32)
0x30e  ldarg.0
0x30f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x314  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x319  ldstr    aSubtype// "subtype"
0x31e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x323  brfalse  loc_41B
0x328  ldstr    aCampaignactivi// "campaignactivity"
0x32d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x332  stloc.3
0x333  ldloc.3
0x334  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x339  ldstr    aActivityid// "activityid"
0x33e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x343  ldloc.3
0x344  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x349  ldstr    aRegardingobjec// "regardingobjectid"
0x34e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x353  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x358  stloc.s  4
0x35a  ldloc.s  4
0x35c  ldc.i4.0
0x35d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x362  ldloc.s  4
0x364  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x369  ldstr    aRegardingobjec// "regardingobjectid"
0x36e  ldc.i4.0
0x36f  ldloc.2
0x370  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x375  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x37a  pop
0x37b  ldloc.s  4
0x37d  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x382  ldstr    aStatecode// "statecode"
0x387  ldc.i4.0
0x388  ldc.i4.0
0x389  stloc.s  6
0x38b  ldloca.s 6
0x38d  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.CampaignActivityState
0x393  callvirt instance string [mscorlib]System.Object::ToString()
0x398  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x39d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3a2  pop
0x3a3  ldloc.3
0x3a4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x3a9  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Filters()
0x3ae  ldloc.s  4
0x3b0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3b5  pop
0x3b6  ldloc.2
0x3b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3bc  ldloc.3
0x3bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveByParty(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3c7  ldloca.s 5
0x3c9  ldloc.1
0x3ca  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3cf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x3d4  stloc.s  7
0x3d6  br.s     loc_404
0x3d8  ldloc.s  7
0x3da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x3df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x3e4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e9  ldloc.s  5
0x3eb  ldstr    aList// "list"
0x3f0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3ff  call     void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.MarketingDataSource::AddItemCampaignActivity(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x404  ldloc.s  7
0x406  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x40b  brtrue.s loc_3D8
0x40d  leave.s  loc_41B
0x40f  ldloc.s  7
0x411  brfalse.s loc_41A
0x413  ldloc.s  7
0x415  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41a  endfinally
0x41b  ldarg.0
0x41c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x421  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x426  br.s     loc_44B
0x428  ldloc.0
0x429  callvirt instance int32 [mscorlib]System.String::get_Length()
0x42e  ldc.i4.0
0x42f  cgt.un
0x431  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x436  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x43b  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x440  ldc.i4   0x80049002
0x445  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x44a  throw
0x44b  leave.s  loc_453
0x44d  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x452  throw
0x453  ret
```
