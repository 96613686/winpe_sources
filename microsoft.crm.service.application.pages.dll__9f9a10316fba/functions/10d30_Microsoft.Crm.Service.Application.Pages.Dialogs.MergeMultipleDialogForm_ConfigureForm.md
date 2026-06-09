# Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::ConfigureForm

- ea: `0x10d30`
- end: `0x110e7`
- name: `Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::ConfigureForm`
- size: `951`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x10ce0`
- `0x10d00`
- `0x10d30`
- `0x110f0`
- `0x11130`
- `0x11160`

## string_xrefs

- `0x10f8b`: `text/xml`
- `0x10df7`: `The records dialog must be opened with at least 2 selected records`

## pseudocode

```c

```

## disassembly

```asm
0x10d30  ldarg.0
0x10d31  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x10d36  ldarg.0
0x10d37  ldarg.0
0x10d38  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10d3d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10d42  ldstr    aIobjtype// "iObjType"
0x10d47  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10d4c  ldc.i4.7
0x10d4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10d52  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x10d57  call     instance void Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::set_EntityTypeCode(int32 value)
0x10d5c  ldarg.0
0x10d5d  ldarg.0
0x10d5e  call     instance int32 Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::get_EntityTypeCode()
0x10d63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10d68  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10d6d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x10d72  ldarg.0
0x10d73  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x10d78  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x10d7d  stloc.0
0x10d7e  ldarg.0
0x10d7f  ldarg.0
0x10d80  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10d85  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10d8a  ldstr    aRequesttype// "requestType"
0x10d8f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10d94  stfld    string Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::requestType
0x10d99  ldarg.0
0x10d9a  ldfld    string Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::requestType
0x10d9f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10da4  ldc.i4.0
0x10da5  ceq
0x10da7  ldstr    aInvalidRequest// "Invalid request type."
0x10dac  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x10db1  ldarg.0
0x10db2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10db7  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x10dbc  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x10dc1  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x10dc6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10dcb  brtrue   loc_10F84
0x10dd0  ldc.i4.0
0x10dd1  stloc.1
0x10dd2  ldarg.0
0x10dd3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10dd8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10ddd  ldstr    aItotal// "iTotal"
0x10de2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10de7  ldc.i4.7
0x10de8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10ded  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x10df2  stloc.2
0x10df3  ldloc.2
0x10df4  ldc.i4.1
0x10df5  cgt
0x10df7  ldstr    aTheRecordsDial// "The records dialog must be opened with "...
0x10dfc  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x10e01  ldarg.0
0x10e02  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x10e07  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x10e0c  stloc.3
0x10e0d  ldstr    asc_15D82// ""
0x10e12  stloc.s  4
0x10e14  ldsfld   string [mscorlib]System.String::Empty
0x10e19  stloc.s  5
0x10e1b  ldsfld   string [mscorlib]System.String::Empty
0x10e20  stloc.s  6
0x10e22  ldarg.0
0x10e23  ldfld    string Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::requestType
0x10e28  stloc.s  7
0x10e2a  ldloc.s  7
0x10e2c  ldstr    aMerge// "merge"
0x10e31  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e36  brtrue.s loc_10E4E
0x10e38  ldloc.s  7
0x10e3a  ldstr    aAssociatechild// "associatechild"
0x10e3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e44  brtrue   loc_10ED8
0x10e49  br       loc_10F5D
0x10e4e  ldarg.0
0x10e4f  ldstr    aMaxincidentmer// "MaxIncidentMergeNumber"
0x10e54  ldc.i4.s 0xA
0x10e56  box      [mscorlib]System.Int32
0x10e5b  call     instance object Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::GetOrgPropertyValue(string propertyName, object defVal)
0x10e60  unbox.any [mscorlib]System.Int32
0x10e65  stloc.1
0x10e66  ldloc.2
0x10e67  ldloc.1
0x10e68  cgt
0x10e6a  ldc.i4.0
0x10e6b  ceq
0x10e6d  ldstr    aYouCanMergeOnl// "You can merge only "
0x10e72  ldloc.1
0x10e73  box      [mscorlib]System.Int32
0x10e78  ldstr    aCasesAtATime// " cases at a time"
0x10e7d  call     string [mscorlib]System.String::Concat(object, object, object)
0x10e82  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x10e87  ldloc.3
0x10e88  ldarg.0
0x10e89  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10e8e  ldstr    aMultipleMergeT// "Multiple_Merge_Title"
0x10e93  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10e98  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x10e9d  ldloc.3
0x10e9e  ldarg.0
0x10e9f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10ea4  ldstr    aMultipleDialog// "Multiple_Dialog_Merge_Description"
0x10ea9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10eae  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x10eb3  ldarg.0
0x10eb4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10eb9  ldstr    aMergerecordsNo// "MergeRecords_NoActive_Error"
0x10ebe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10ec3  stloc.s  4
0x10ec5  ldstr    aE1d7d576Da764f// "E1D7D576-DA76-4F22-8A65-CC57E23C41BB"
0x10eca  stloc.s  5
0x10ecc  ldstr    aButtonLabelMer// "Button_Label_Merge"
0x10ed1  stloc.s  6
0x10ed3  br       loc_10F5D
0x10ed8  ldarg.0
0x10ed9  ldstr    aMaxchildincide// "MaxChildIncidentNumber"
0x10ede  ldc.i4.s 0x64
0x10ee0  box      [mscorlib]System.Int32
0x10ee5  call     instance object Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::GetOrgPropertyValue(string propertyName, object defVal)
0x10eea  unbox.any [mscorlib]System.Int32
0x10eef  stloc.1
0x10ef0  ldloc.2
0x10ef1  ldloc.1
0x10ef2  cgt
0x10ef4  ldc.i4.0
0x10ef5  ceq
0x10ef7  ldstr    aAParentCaseCan// "A Parent Case cannot have more than "
0x10efc  ldloc.1
0x10efd  box      [mscorlib]System.Int32
0x10f02  ldstr    aChildCasesCont// "child cases. Contact your administrator"...
0x10f07  call     string [mscorlib]System.String::Concat(object, object, object)
0x10f0c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x10f11  ldloc.3
0x10f12  ldarg.0
0x10f13  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10f18  ldstr    aAssociateChild// "Associate_Child_Title"
0x10f1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f22  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x10f27  ldloc.3
0x10f28  ldarg.0
0x10f29  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10f2e  ldstr    aAssociateChild_0// "Associate_Child_Description"
0x10f33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f38  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x10f3d  ldarg.0
0x10f3e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10f43  ldstr    aParentchildNoa// "ParentChild_NoActive_Error"
0x10f48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f4d  stloc.s  4
0x10f4f  ldstr    a5dbd358d667041// "5dbd358d-6670-4138-92b3-b5810fa2a0e8"
0x10f54  stloc.s  5
0x10f56  ldstr    aButtonLabelSet// "Button_Label_Set"
0x10f5b  stloc.s  6
0x10f5d  ldloc.3
0x10f5e  ldc.i4.0
0x10f5f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x10f64  ldloc.3
0x10f65  ldc.i4.1
0x10f66  ldloc.s  6
0x10f68  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x10f6d  ldloc.3
0x10f6e  ldc.i4.2
0x10f6f  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x10f74  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x10f79  ldarg.0
0x10f7a  ldloc.s  4
0x10f7c  ldloc.s  5
0x10f7e  call     instance void Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::LoadAppGrid(string emptyGridMessage, string viewId)
0x10f83  ret
0x10f84  nop
0x10f85  ldarg.0
0x10f86  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x10f8b  ldstr    aTextXml// "text/xml"
0x10f90  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x10f95  ldarg.0
0x10f96  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10f9b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10fa0  ldstr    aIid// "iId"
0x10fa5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10faa  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x10faf  stloc.s  0xA
0x10fb1  ldloca.s 0xA
0x10fb3  ldstr    aB// "B"
0x10fb8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10fbd  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x10fc2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10fc7  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x10fcc  stloc.s  8
0x10fce  ldarg.0
0x10fcf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10fd4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10fd9  ldstr    aMasterid// "masterId"
0x10fde  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10fe3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10fe8  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x10fed  stloc.s  9
0x10fef  ldloc.s  9
0x10ff1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10ff6  ldc.i4.0
0x10ff7  ceq
0x10ff9  ldstr    aMasterIdCanTBe// "Master Id can't be null or enmpty"
0x10ffe  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x11003  ldloc.s  8
0x11005  ldloc.s  9
0x11007  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1100c  brfalse  loc_110A7
0x11011  ldloc.0
0x11012  ldloc.s  8
0x11014  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x11019  ldarg.0
0x1101a  ldfld    string Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::requestType
0x1101f  stloc.s  7
0x11021  ldloc.s  7
0x11023  ldstr    aAssociatechild// "associatechild"
0x11028  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1102d  brtrue.s loc_1103F
0x1102f  ldloc.s  7
0x11031  ldstr    aMerge// "merge"
0x11036  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1103b  brtrue.s loc_1106B
0x1103d  br.s     loc_110A7
0x1103f  ldloc.0
0x11040  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x11045  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x1104a  ldstr    aParentcaseid// "parentcaseid"
0x1104f  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x11054  brfalse.s loc_110A7
0x11056  ldloc.0
0x11057  ldstr    aParentcaseid// "parentcaseid"
0x1105c  ldloc.s  9
0x1105e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x11063  ldloc.0
0x11064  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x11069  br.s     loc_110A7
0x1106b  ldloc.0
0x1106c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x11071  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x11076  ldstr    aMasterid_0// "masterid"
0x1107b  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x11080  brfalse.s loc_110A7
0x11082  ldloc.s  9
0x11084  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11089  ldloc.0
0x1108a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x1108f  ldloc.0
0x11090  ldloc.s  8
0x11092  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11097  ldc.i4.1
0x11098  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1109d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.MergeCommand::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x110a2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.MergeCommand::Execute()
0x110a7  leave.s  loc_110E0
0x110a9  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x110ae  throw
0x110af  stloc.s  0xB
0x110b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x110b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x110bb  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x110c0  ldstr    a0_0// "{0}"
0x110c5  ldc.i4.1
0x110c6  newarr   [mscorlib]System.Object
0x110cb  dup
0x110cc  ldc.i4.0
0x110cd  ldstr    aErrorEncounter_0// "Error encountered in post back of Merge"...
0x110d2  stelem.ref
0x110d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x110d8  ldloc.s  0xB
0x110da  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x110df  throw
0x110e0  ldarg.0
0x110e1  call     instance void Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::SendOK()
0x110e6  ret
```
