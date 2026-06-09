# Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::RenderFormData

- ea: `0xb3db0`
- end: `0xb405f`
- name: `Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::RenderFormData`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xb3b90`

## callees

- `0x26620`
- `0x3b7a0`
- `0x3b7b0`
- `0x3b7e0`
- `0x3bb10`
- `0x46e30`
- `0x8cc00`
- `0xb2bd0`
- `0xb3ad0`

## string_xrefs

- `0xb3ea5`: `openlui(new Sys.UI.DomEvent(event))`
- `0xb3fcc`: `saveandopenfollowup`
- `0xb3fd1`: `RelatedInformation_FollowUp_SaveOpen_Button`
- `0xb3fdb`: `CategoryData{0}.SaveAndOpenFollowUp({1}, '{2}', crmFollowUpForm);`

## pseudocode

```c

```

## disassembly

```asm
0xb3db0  ldarg.0
0xb3db1  call     instance int32 Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::get_EntityType()
0xb3db6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb3dbb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb3dc0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xb3dc5  stloc.0
0xb3dc6  newobj   instance void Microsoft.Crm.Application.Forms.FollowUpForm::.ctor()
0xb3dcb  stloc.1
0xb3dcc  ldloc.1
0xb3dcd  ldloc.0
0xb3dce  callvirt instance void Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xb3dd3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::.ctor()
0xb3dd8  stloc.2
0xb3dd9  ldloc.2
0xb3dda  ldstr    aOwnerid// "ownerid"
0xb3ddf  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb3de4  ldloc.2
0xb3de5  ldstr    aLookuptypes// "lookuptypes"
0xb3dea  ldc.i4.8
0xb3deb  stloc.s  6
0xb3ded  ldloca.s 6
0xb3def  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb3df4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb3df9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3dfe  ldloc.2
0xb3dff  ldstr    aLookuptypename_1// "lookuptypenames"
0xb3e04  ldc.i4.5
0xb3e05  newarr   [mscorlib]System.Object
0xb3e0a  dup
0xb3e0b  ldc.i4.0
0xb3e0c  ldc.i4.8
0xb3e0d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0xb3e12  stelem.ref
0xb3e13  dup
0xb3e14  ldc.i4.1
0xb3e15  ldstr    asc_12FE0A// ":"
0xb3e1a  stelem.ref
0xb3e1b  dup
0xb3e1c  ldc.i4.2
0xb3e1d  ldc.i4.8
0xb3e1e  box      [mscorlib]System.Int32
0xb3e23  stelem.ref
0xb3e24  dup
0xb3e25  ldc.i4.3
0xb3e26  ldstr    asc_12FE0A// ":"
0xb3e2b  stelem.ref
0xb3e2c  dup
0xb3e2d  ldc.i4.4
0xb3e2e  ldc.i4.8
0xb3e2f  ldc.i4.1
0xb3e30  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xb3e35  stelem.ref
0xb3e36  call     string [mscorlib]System.String::Concat(object[])
0xb3e3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3e40  ldloc.2
0xb3e41  ldstr    aLookuptypeicon// "lookuptypeIcons"
0xb3e46  ldc.i4.8
0xb3e47  ldc.i4.0
0xb3e48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb3e4d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb3e52  callvirt instance string [mscorlib]System.Object::ToString()
0xb3e57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3e5c  ldloc.2
0xb3e5d  ldstr    aLookupbrowse// "lookupbrowse"
0xb3e62  ldstr    a0// "0"
0xb3e67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3e6c  ldloc.2
0xb3e6d  ldstr    aLookupstyle_2// "lookupstyle"
0xb3e72  ldstr    aSingle// "single"
0xb3e77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3e7c  ldloc.2
0xb3e7d  ldstr    aReq// "req"
0xb3e82  ldstr    a2_0// "2"
0xb3e87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3e8c  ldloc.2
0xb3e8d  ldc.i4.2
0xb3e8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0xb3e93  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xb3e98  stloc.3
0xb3e99  ldloc.3
0xb3e9a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0xb3e9f  ldnull
0xb3ea0  ldstr    aMsCrmLookupIte_0// "ms-crm-Lookup-Item"
0xb3ea5  ldstr    aOpenluiNewSysU// "openlui(new Sys.UI.DomEvent(event))"
0xb3eaa  ldc.i4.8
0xb3eab  ldc.i4.0
0xb3eac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb3eb1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb3eb6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::.ctor(string, string, string, string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xb3ebb  stloc.s  4
0xb3ebd  ldloc.s  4
0xb3ebf  ldstr    aOid// "oid"
0xb3ec4  ldloc.3
0xb3ec5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xb3eca  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xb3ecf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3ed4  ldloc.s  4
0xb3ed6  ldstr    aOtype// "otype"
0xb3edb  ldc.i4.8
0xb3edc  stloc.s  6
0xb3ede  ldloca.s 6
0xb3ee0  ldstr    aD// "D"
0xb3ee5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb3eea  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xb3eef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0xb3ef4  ldloc.2
0xb3ef5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::get_Items()
0xb3efa  ldloc.s  4
0xb3efc  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem)
0xb3f01  pop
0xb3f02  ldc.i4.1
0xb3f03  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb3f08  ldstr    aRelatedinforma_16// "RelatedInformation_Category_FollowUp_La"...
0xb3f0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb3f12  ldc.i4.2
0xb3f13  newobj   instance void Microsoft.Crm.Application.Forms.FollowUpFormCell::.ctor(bool showLabel, string label, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel requiredLevel)
0xb3f18  stloc.s  5
0xb3f1a  ldloc.s  5
0xb3f1c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb3f21  ldloc.2
0xb3f22  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xb3f27  ldloc.1
0xb3f28  callvirt instance class Microsoft.Crm.Application.Forms.FollowUpFormBody Microsoft.Crm.Application.Forms.FollowUpForm::get_FormBody()
0xb3f2d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb3f32  ldloc.1
0xb3f33  callvirt instance class Microsoft.Crm.Application.Forms.FollowUpFormBody Microsoft.Crm.Application.Forms.FollowUpForm::get_FormBody()
0xb3f38  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb3f3d  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0xb3f42  ldloc.s  5
0xb3f44  callvirt instance void [System.Web]System.Web.UI.ControlCollection::AddAt(int32, class [System.Web]System.Web.UI.Control)
0xb3f49  ldloc.1
0xb3f4a  ldarg.1
0xb3f4b  callvirt instance void Microsoft.Crm.Application.Forms.FollowUpForm::RenderForm(class [System.Web]System.Web.UI.HtmlTextWriter output)
0xb3f50  ldarg.1
0xb3f51  ldstr    aTableCellspaci_11// "<table cellspacing=\"0\" cellpadding=\""...
0xb3f56  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3f5b  ldstr    aSavefollowup// "savefollowup"
0xb3f60  ldstr    aRelatedinforma_17// "RelatedInformation_FollowUp_Save_Button"
0xb3f65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb3f6a  ldstr    aCategorydata0S// "CategoryData{0}.SaveFollowUp({1}, '{2}'"...
0xb3f6f  ldc.i4.3
0xb3f70  newarr   [mscorlib]System.Object
0xb3f75  dup
0xb3f76  ldc.i4.0
0xb3f77  ldarg.0
0xb3f78  callvirt instance string Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::get_CategoryId()
0xb3f7d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xb3f82  stelem.ref
0xb3f83  dup
0xb3f84  ldc.i4.1
0xb3f85  ldarg.0
0xb3f86  call     instance int32 Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::get_EntityType()
0xb3f8b  box      [mscorlib]System.Int32
0xb3f90  stelem.ref
0xb3f91  dup
0xb3f92  ldc.i4.2
0xb3f93  ldarg.0
0xb3f94  call     instance int32 Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::get_EntityType()
0xb3f99  ldc.i4.1
0xb3f9a  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xb3f9f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xb3fa4  stelem.ref
0xb3fa5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb3faa  ldc.i4.0
0xb3fab  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor(string, string, string, bool)
0xb3fb0  ldarg.1
0xb3fb1  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xb3fb6  ldarg.1
0xb3fb7  ldstr    aTdTr// "</td></tr>"
0xb3fbc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3fc1  ldarg.1
0xb3fc2  ldstr    aTrTdAlignCente// "<tr><td align=\"center\">"
0xb3fc7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3fcc  ldstr    aSaveandopenfol// "saveandopenfollowup"
0xb3fd1  ldstr    aRelatedinforma_18// "RelatedInformation_FollowUp_SaveOpen_Bu"...
0xb3fd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb3fdb  ldstr    aCategorydata0S_0// "CategoryData{0}.SaveAndOpenFollowUp({1}"...
0xb3fe0  ldc.i4.3
0xb3fe1  newarr   [mscorlib]System.Object
0xb3fe6  dup
0xb3fe7  ldc.i4.0
0xb3fe8  ldarg.0
0xb3fe9  callvirt instance string Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::get_CategoryId()
0xb3fee  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xb3ff3  stelem.ref
0xb3ff4  dup
0xb3ff5  ldc.i4.1
0xb3ff6  ldarg.0
0xb3ff7  call     instance int32 Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::get_EntityType()
0xb3ffc  box      [mscorlib]System.Int32
0xb4001  stelem.ref
0xb4002  dup
0xb4003  ldc.i4.2
0xb4004  ldarg.0
0xb4005  call     instance int32 Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FollowUpCategory::get_EntityType()
0xb400a  ldc.i4.1
0xb400b  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xb4010  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xb4015  stelem.ref
0xb4016  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb401b  ldc.i4.0
0xb401c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor(string, string, string, bool)
0xb4021  ldarg.1
0xb4022  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xb4027  ldarg.1
0xb4028  ldstr    aTdTr// "</td></tr>"
0xb402d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb4032  ldarg.1
0xb4033  ldstr    aTrTd// "<tr><td>"
0xb4038  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb403d  newobj   instance void Microsoft.Crm.Application.Controls.AppNotifications::.ctor()
0xb4042  dup
0xb4043  ldstr    aSavemessage// "savemessage"
0xb4048  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb404d  ldarg.1
0xb404e  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xb4053  ldarg.1
0xb4054  ldstr    aTdTrTable// "</td></tr></table>"
0xb4059  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb405e  ret
```
