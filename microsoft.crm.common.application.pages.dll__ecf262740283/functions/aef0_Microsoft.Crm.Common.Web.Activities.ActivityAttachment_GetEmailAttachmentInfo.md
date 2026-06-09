# Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetEmailAttachmentInfo

- ea: `0xaef0`
- end: `0xb3b1`
- name: `Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetEmailAttachmentInfo`
- size: `1217`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xab40`
- `0xaef0`
- `0xb3c0`
- `0xb3d0`

## string_xrefs

- `0xaf51`: `_CreateFromId`
- `0xaf68`: `_CreateFromId`
- `0xaf95`: `_CreateFromType`
- `0xafac`: `_CreateFromType`
- `0xb219`: `http://go.microsoft.com/fwlink/p/?LinkId=824705`
- `0xb28f`: `Attachment.OneDriveRemoveError`
- `0xb307`: `http://go.microsoft.com/fwlink/p/?LinkId=824706`
- `0xb37d`: `http://go.microsoft.com/fwlink/p/?LinkId=824706`
- `0xb328`: `Attachment.OneDriveNotConfigured`
- `0xb372`: `Attachment.OneDriveNotConfigured`

## pseudocode

```c

```

## disassembly

```asm
0xaef0  ldsfld   string [mscorlib]System.String::Empty
0xaef5  stloc.0
0xaef6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaefb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsEmailEngagementFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaf00  brtrue.s loc_AF08
0xaf02  ldsfld   string [mscorlib]System.String::Empty
0xaf07  ret
0xaf08  ldarg.0
0xaf09  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf0e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf13  ldstr    aIsh// "ish"
0xaf18  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf1d  brfalse.s loc_AF46
0xaf1f  ldarg.0
0xaf20  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf25  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf2a  ldstr    aIsh// "ish"
0xaf2f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf34  callvirt instance string [mscorlib]System.Object::ToString()
0xaf39  call     bool [mscorlib]System.Boolean::Parse(string)
0xaf3e  brfalse.s loc_AF46
0xaf40  ldsfld   string [mscorlib]System.String::Empty
0xaf45  ret
0xaf46  ldarg.0
0xaf47  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf4c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf51  ldstr    aCreatefromid// "_CreateFromId"
0xaf56  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf5b  brfalse.s loc_AF74
0xaf5d  ldarg.0
0xaf5e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf63  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf68  ldstr    aCreatefromid// "_CreateFromId"
0xaf6d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf72  br.s     loc_AF89
0xaf74  ldarg.0
0xaf75  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf7a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf7f  ldstr    aPid// "pId"
0xaf84  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf89  stloc.2
0xaf8a  ldarg.0
0xaf8b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf90  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf95  ldstr    aCreatefromtype// "_CreateFromType"
0xaf9a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf9f  brfalse.s loc_AFB8
0xafa1  ldarg.0
0xafa2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xafa7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xafac  ldstr    aCreatefromtype// "_CreateFromType"
0xafb1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xafb6  br.s     loc_AFCD
0xafb8  ldarg.0
0xafb9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xafbe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xafc3  ldstr    aPtype// "pType"
0xafc8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xafcd  stloc.3
0xafce  ldarg.0
0xafcf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xafd4  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xafd9  ldc.i4.1
0xafda  bne.un.s loc_AFE2
0xafdc  ldsfld   string [mscorlib]System.String::Empty
0xafe1  ret
0xafe2  ldloc.2
0xafe3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xafe8  brtrue.s loc_AFF2
0xafea  ldloc.3
0xafeb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xaff0  brfalse.s loc_AFF8
0xaff2  ldsfld   string [mscorlib]System.String::Empty
0xaff7  ret
0xaff8  ldloc.3
0xaff9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaffe  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xb003  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb008  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb00d  stloc.1
0xb00e  ldc.i4.m1
0xb00f  stloc.s  4
0xb011  ldarg.0
0xb012  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb017  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb01c  ldstr    aPtype// "pType"
0xb021  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb026  brfalse.s loc_B04F
0xb028  ldarg.0
0xb029  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb02e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb033  ldstr    aPtype// "pType"
0xb038  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb03d  ldloca.s 4
0xb03f  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xb044  brfalse.s loc_B04F
0xb046  ldloc.s  4
0xb048  ldc.i4   0x106A
0xb04d  beq.s    loc_B055
0xb04f  ldsfld   string [mscorlib]System.String::Empty
0xb054  ret
0xb055  ldloc.1
0xb056  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xb05b  ldloc.2
0xb05c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb061  ldc.i4.2
0xb062  newarr   [mscorlib]System.String
0xb067  dup
0xb068  ldc.i4.0
0xb069  ldstr    aStatuscode// "statuscode"
0xb06e  stelem.ref
0xb06f  dup
0xb070  ldc.i4.1
0xb071  ldstr    aIsemailfollowe// "isemailfollowed"
0xb076  stelem.ref
0xb077  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb07c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb081  stloc.s  5
0xb083  ldloc.s  5
0xb085  ldstr    aStatuscode// "statuscode"
0xb08a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb08f  callvirt instance string [mscorlib]System.Object::ToString()
0xb094  call     int32 [mscorlib]System.Int32::Parse(string)
0xb099  ldc.i4.1
0xb09a  bne.un.s loc_B0B4
0xb09c  ldloc.s  5
0xb09e  ldstr    aIsemailfollowe// "isemailfollowed"
0xb0a3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb0a8  callvirt instance string [mscorlib]System.Object::ToString()
0xb0ad  call     bool [mscorlib]System.Boolean::Parse(string)
0xb0b2  brtrue.s loc_B0BA
0xb0b4  ldsfld   string [mscorlib]System.String::Empty
0xb0b9  ret
0xb0ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb0bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xb0c4  ldc.i4.0
0xb0c5  ldc.i4.0
0xb0c6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xb0cb  stloc.s  6
0xb0cd  ldloc.s  6
0xb0cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb0d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xb0d9  ldc.i4.0
0xb0da  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xb0df  ldloc.s  6
0xb0e1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnlineSharepointConfigured(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb0e6  brfalse.s loc_B0F1
0xb0e8  ldloc.s  6
0xb0ea  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOneDriveIntegrationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb0ef  br.s     loc_B0F2
0xb0f1  ldc.i4.0
0xb0f2  stloc.s  7
0xb0f4  ldarg.1
0xb0f5  ldc.i4.1
0xb0f6  bne.un.s loc_B104
0xb0f8  ldstr    aStyleBackgroun// "style='background-color:none  !importan"...
0xb0fd  stloc.s  8
0xb0ff  leave    loc_B3AE
0xb104  ldarg.1
0xb105  ldc.i4.2
0xb106  bne.un.s loc_B114
0xb108  ldstr    aTrTdNbspTdTr// "<tr><td>&nbsp;</td></tr>"
0xb10d  stloc.s  8
0xb10f  leave    loc_B3AE
0xb114  ldloc.s  7
0xb116  brfalse  loc_B323
0xb11b  ldloc.s  6
0xb11d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0xb122  ldc.i4   0x106A
0xb127  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0xb12c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDocumentManagementEnabled()
0xb131  brfalse  loc_B2AD
0xb136  ldc.i4.5
0xb137  newarr   [mscorlib]System.Object
0xb13c  dup
0xb13d  ldc.i4.0
0xb13e  ldstr    aImgIdImginfoAl// "<img id='imgInfo' alt='' src="
0xb143  stelem.ref
0xb144  dup
0xb145  ldc.i4.1
0xb146  ldstr    aImgsIco16InfoG// "/_imgs/ico/16_info.gif"
0xb14b  ldloc.s  6
0xb14d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetIconUrl(string filePath, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb152  stelem.ref
0xb153  dup
0xb154  ldc.i4.2
0xb155  ldstr    aAlignAbsmiddle// " align='absmiddle' border='0'><img id='"...
0xb15a  stelem.ref
0xb15b  dup
0xb15c  ldc.i4.3
0xb15d  ldstr    aImgsIco16Error// "/_imgs/ico/16_error.gif"
0xb162  ldloc.s  6
0xb164  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetIconUrl(string filePath, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb169  stelem.ref
0xb16a  dup
0xb16b  ldc.i4.4
0xb16c  ldstr    aAlignAbsmiddle_0// " align='absmiddle' border='0'>&nbsp;&nb"...
0xb171  stelem.ref
0xb172  call     string [mscorlib]System.String::Concat(object[])
0xb177  stloc.0
0xb178  ldc.i4.0
0xb179  stloc.s  9
0xb17b  ldstr    aActivitymimeat// "activitymimeattachment"
0xb180  ldarg.0
0xb181  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb186  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb18b  ldstr    aId// "id"
0xb190  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb195  callvirt instance string [mscorlib]System.Object::ToString()
0xb19a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb19f  ldc.i4.1
0xb1a0  newarr   [mscorlib]System.String
0xb1a5  dup
0xb1a6  ldc.i4.0
0xb1a7  ldstr    aIsfollowed// "isfollowed"
0xb1ac  stelem.ref
0xb1ad  ldloc.s  6
0xb1af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb1b4  stloc.s  0xA
0xb1b6  ldloc.s  0xA
0xb1b8  ldstr    aIsfollowed// "isfollowed"
0xb1bd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb1c2  brfalse.s loc_B1DC
0xb1c4  ldloc.s  0xA
0xb1c6  ldstr    aIsfollowed// "isfollowed"
0xb1cb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb1d0  callvirt instance string [mscorlib]System.Object::ToString()
0xb1d5  call     bool [mscorlib]System.Boolean::Parse(string)
0xb1da  stloc.s  9
0xb1dc  ldloc.s  9
0xb1de  brtrue.s loc_B251
0xb1e0  ldc.i4.8
0xb1e1  newarr   [mscorlib]System.String
0xb1e6  dup
0xb1e7  ldc.i4.0
0xb1e8  ldloc.0
0xb1e9  stelem.ref
0xb1ea  dup
0xb1eb  ldc.i4.1
0xb1ec  ldstr    aSpanIdDescript// "<span id='descriptionMsg' tabindex='0' "...
0xb1f1  stelem.ref
0xb1f2  dup
0xb1f3  ldc.i4.2
0xb1f4  ldstr    aAttachmentInfo// "Attachment.Information_Follow"
0xb1f9  call     string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetResourceString(string key)
0xb1fe  stelem.ref
0xb1ff  dup
0xb200  ldc.i4.3
0xb201  ldstr    asc_27FC0// "'>"
0xb206  stelem.ref
0xb207  dup
0xb208  ldc.i4.4
0xb209  ldstr    a01// "{0} {1}"
0xb20e  ldstr    aAttachmentInfo// "Attachment.Information_Follow"
0xb213  call     string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetResourceString(string key)
0xb218  ldarg.0
0xb219  ldstr    aHttpGoMicrosof_0// "http://go.microsoft.com/fwlink/p/?LinkI"...
0xb21e  call     instance string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::KnowMoreHyperLink(string url)
0xb223  call     string [mscorlib]System.String::Format(string, object, object)
0xb228  stelem.ref
0xb229  dup
0xb22a  ldc.i4.5
0xb22b  ldstr    aSpanSpanIdErrm// "</span><span id='errMsg' style='display"...
0xb230  stelem.ref
0xb231  dup
0xb232  ldc.i4.6
0xb233  ldstr    aAttachmentOned// "Attachment.OneDriveUploadError"
0xb238  call     string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetResourceString(string key)
0xb23d  stelem.ref
0xb23e  dup
0xb23f  ldc.i4.7
0xb240  ldstr    aSpan// "</span>"
0xb245  stelem.ref
0xb246  call     string [mscorlib]System.String::Concat(string[])
0xb24b  stloc.0
0xb24c  br       loc_B397
0xb251  ldc.i4.8
0xb252  newarr   [mscorlib]System.String
0xb257  dup
0xb258  ldc.i4.0
0xb259  ldloc.0
0xb25a  stelem.ref
0xb25b  dup
0xb25c  ldc.i4.1
0xb25d  ldstr    aSpanIdDescript// "<span id='descriptionMsg' tabindex='0' "...
0xb262  stelem.ref
0xb263  dup
0xb264  ldc.i4.2
0xb265  ldstr    aAttachmentInfo_0// "Attachment.Information_Unfollow"
0xb26a  call     string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetResourceString(string key)
0xb26f  stelem.ref
0xb270  dup
0xb271  ldc.i4.3
0xb272  ldstr    asc_27FC0// "'>"
0xb277  stelem.ref
0xb278  dup
0xb279  ldc.i4.4
0xb27a  ldstr    aAttachmentInfo_0// "Attachment.Information_Unfollow"
0xb27f  call     string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetResourceString(string key)
0xb284  stelem.ref
  ... truncated ...
```
