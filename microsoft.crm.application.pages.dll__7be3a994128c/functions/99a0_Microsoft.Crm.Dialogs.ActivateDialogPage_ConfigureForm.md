# Microsoft.Crm.Dialogs.ActivateDialogPage::ConfigureForm

- ea: `0x99a0`
- end: `0xa6e3`
- name: `Microsoft.Crm.Dialogs.ActivateDialogPage::ConfigureForm`
- size: `3395`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x99a0`
- `0xa6f0`
- `0xa7a0`
- `0xa910`
- `0xa940`
- `0xa980`
- `0xaad0`
- `0xab30`
- `0xaba0`
- `0xabf0`

## string_xrefs

- `0x9f00`: `XML loaded from the stream returned String.Empty.`
- `0x9f0a`: `XML loaded from the stream returned String.Empty.`
- `0x9d37`: `kbarticletemplate`
- `0x9d6d`: `service`
- `0xa2d1`: `ChannelAccessProfileRule_Enable_Dialog_Message`
- `0xa2f3`: `Dialog_Activate_For_ChannelAccessProfileRule`
- `0xa30e`: `Dialog_Activate_ChannelAccessProfile_Title`
- `0xa382`: `Dialog_Activate_ChannelAccessProfile_Title`
- `0xa3ab`: `Dialog_Activate_Multiple_ChannelAccessProfile_Description`
- `0xa3d6`: `Dialog_Activate_Single_ChannelAccessProfile_Description`

## pseudocode

```c

```

## disassembly

```asm
0x99a0  ldarg.0
0x99a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x99a6  ldstr    aDialogActivate// "Dialog_Activate_Description_Activate"
0x99ab  stloc.0
0x99ac  ldarg.0
0x99ad  ldarg.0
0x99ae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99b3  ldstr    aDialogLabelAct// "Dialog_Label_Active"
0x99b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99bd  stfld    string Microsoft.Crm.Dialogs.ActivateDialogPage::statusString
0x99c2  ldarg.0
0x99c3  ldarg.0
0x99c4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x99c9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x99ce  ldstr    aItotal// "iTotal"
0x99d3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99d8  ldc.i4.7
0x99d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x99de  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x99e3  stfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::Total
0x99e8  ldarg.0
0x99e9  ldarg.0
0x99ea  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x99ef  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x99f4  ldstr    aIobjtype// "iObjType"
0x99f9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99fe  ldc.i4.7
0x99ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a04  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x9a09  stfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::ObjType
0x9a0e  ldarg.0
0x9a0f  ldarg.0
0x9a10  ldfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::ObjType
0x9a15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9a1a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9a1f  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.ActivateDialogPage::entityType
0x9a24  ldarg.0
0x9a25  ldarg.0
0x9a26  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9a2b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9a30  ldstr    aIid// "iId"
0x9a35  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9a3a  brtrue.s loc_9A43
0x9a3c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9a41  br.s     loc_9A5D
0x9a43  ldarg.0
0x9a44  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9a49  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9a4e  ldstr    aIid// "iId"
0x9a53  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9a58  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9a5d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateDialogPage::entityId
0x9a62  ldarg.0
0x9a63  ldarg.0
0x9a64  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.ActivateDialogPage::entityType
0x9a69  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x9a6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9a73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9a78  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::IsStateModelAware(valuetype [mscorlib]System.Guid)
0x9a7d  brfalse.s loc_9A91
0x9a7f  ldarg.0
0x9a80  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.ActivateDialogPage::entityType
0x9a85  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x9a8a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EnforceStateTransitions()
0x9a8f  br.s     loc_9A92
0x9a91  ldc.i4.0
0x9a92  stfld    bool Microsoft.Crm.Dialogs.ActivateDialogPage::isStateModelAwareAndEnforceStateTransitons
0x9a97  ldarg.0
0x9a98  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a9d  ldstr    aEnforcestatetr// "_EnforceStateTransitions"
0x9aa2  ldarg.0
0x9aa3  ldfld    bool Microsoft.Crm.Dialogs.ActivateDialogPage::isStateModelAwareAndEnforceStateTransitons
0x9aa8  brtrue.s loc_9AB1
0x9aaa  ldstr    a0_1// "0"
0x9aaf  br.s     loc_9AB6
0x9ab1  ldstr    a1// "1"
0x9ab6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9abb  ldarg.0
0x9abc  ldfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::Total
0x9ac1  ldc.i4.1
0x9ac2  beq.s    loc_9AD8
0x9ac4  ldarg.0
0x9ac5  ldarg.0
0x9ac6  ldfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::ObjType
0x9acb  ldc.i4.2
0x9acc  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x9ad1  stfld    string Microsoft.Crm.Dialogs.ActivateDialogPage::ObjName
0x9ad6  br.s     loc_9AEA
0x9ad8  ldarg.0
0x9ad9  ldarg.0
0x9ada  ldfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::ObjType
0x9adf  ldc.i4.1
0x9ae0  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x9ae5  stfld    string Microsoft.Crm.Dialogs.ActivateDialogPage::ObjName
0x9aea  ldarg.0
0x9aeb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9af0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9af5  ldstr    aIobjsubtype// "iObjSubtype"
0x9afa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9aff  brfalse.s loc_9B33
0x9b01  ldarg.0
0x9b02  ldarg.0
0x9b03  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9b08  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9b0d  ldstr    aIobjsubtype// "iObjSubtype"
0x9b12  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9b17  ldc.i4.7
0x9b18  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b1d  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x9b22  stfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::iObjSubtype
0x9b27  leave.s  loc_9B33
0x9b29  pop
0x9b2a  ldarg.0
0x9b2b  ldc.i4.1
0x9b2c  stfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::iObjSubtype
0x9b31  leave.s  loc_9B33
0x9b33  ldarg.0
0x9b34  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Dialogs.ActivateDialogPage::WarningMessageDiv
0x9b39  ldc.i4.0
0x9b3a  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x9b3f  ldarg.0
0x9b40  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9b45  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x9b4a  stloc.1
0x9b4b  ldloc.1
0x9b4c  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x9b51  ldc.i4.0
0x9b52  conv.i8
0x9b53  ble      loc_9F22
0x9b58  ldloc.1
0x9b59  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x9b5e  stloc.2
0x9b5f  ldloc.2
0x9b60  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9b65  brfalse  loc_9EF7
0x9b6a  ldsfld   string [mscorlib]System.String::Empty
0x9b6f  stloc.3
0x9b70  ldarg.0
0x9b71  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9b76  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9b7b  ldstr    aIid// "iId"
0x9b80  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9b85  stloc.s  4
0x9b87  ldloc.s  4
0x9b89  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9b8e  brtrue.s loc_9BA5
0x9b90  ldloc.s  4
0x9b92  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x9b97  stloc.3
0x9b98  ldarg.0
0x9b99  ldloc.s  4
0x9b9b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9ba0  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateDialogPage::entityId
0x9ba5  ldsfld   string [mscorlib]System.String::Empty
0x9baa  stloc.s  5
0x9bac  ldnull
0x9bad  stloc.s  6
0x9baf  ldarg.0
0x9bb0  ldfld    int32 Microsoft.Crm.Dialogs.ActivateDialogPage::ObjType
0x9bb5  stloc.s  7
0x9bb7  ldloc.s  7
0x9bb9  ldc.i4   0x1086
0x9bbe  bgt      loc_9C78
0x9bc3  ldloc.s  7
0x9bc5  ldc.i4   0x3F8
0x9bca  bgt.s    loc_9C1D
0x9bcc  ldloc.s  7
0x9bce  ldc.i4.8
0x9bcf  bgt.s    loc_9BF7
0x9bd1  ldloc.s  7
0x9bd3  ldc.i4.1
0x9bd4  sub
0x9bd5  switch   loc_9E7D, loc_9E7D, loc_9E7D, loc_9E62
0x9bea  ldloc.s  7
0x9bec  ldc.i4.8
0x9bed  beq      loc_9E20
0x9bf2  br       loc_9E7D
0x9bf7  ldloc.s  7
0x9bf9  ldc.i4.s 0xA
0x9bfb  beq      loc_9E7D
0x9c00  ldloc.s  7
0x9c02  ldc.i4   0x3F2
0x9c07  beq      loc_9E6B
0x9c0c  ldloc.s  7
0x9c0e  ldc.i4   0x3F8
0x9c13  beq      loc_9D37
0x9c18  br       loc_9E7D
0x9c1d  ldloc.s  7
0x9c1f  ldc.i4   0x438
0x9c24  bgt.s    loc_9C4F
0x9c26  ldloc.s  7
0x9c28  ldc.i4   0x3FE
0x9c2d  beq      loc_9E7D
0x9c32  ldloc.s  7
0x9c34  ldc.i4   0x400
0x9c39  beq      loc_9E7D
0x9c3e  ldloc.s  7
0x9c40  ldc.i4   0x438
0x9c45  beq      loc_9E7D
0x9c4a  br       loc_9E7D
0x9c4f  ldloc.s  7
0x9c51  ldc.i4   0xBC0
0x9c56  beq      loc_9E74
0x9c5b  ldloc.s  7
0x9c5d  ldc.i4   0xFA1
0x9c62  beq      loc_9D6D
0x9c67  ldloc.s  7
0x9c69  ldc.i4   0x1086
0x9c6e  beq      loc_9E7D
0x9c73  br       loc_9E7D
0x9c78  ldloc.s  7
0x9c7a  ldc.i4   0x1FF5
0x9c7f  bgt.s    loc_9CDC
0x9c81  ldloc.s  7
0x9c83  ldc.i4   0x1194
0x9c88  bgt.s    loc_9CB3
0x9c8a  ldloc.s  7
0x9c8c  ldc.i4   0x10CC
0x9c91  beq      loc_9E7D
0x9c96  ldloc.s  7
0x9c98  ldc.i4   0x1131
0x9c9d  beq      loc_9DA3
0x9ca2  ldloc.s  7
0x9ca4  ldc.i4   0x1194
0x9ca9  beq      loc_9E7D
0x9cae  br       loc_9E7D
0x9cb3  ldloc.s  7
0x9cb5  ldc.i4   0x1200
0x9cba  beq      loc_9E74
0x9cbf  ldloc.s  7
0x9cc1  ldc.i4   0x125F
0x9cc6  beq      loc_9E11
0x9ccb  ldloc.s  7
0x9ccd  ldc.i4   0x1FF5
0x9cd2  beq      loc_9E7D
0x9cd7  br       loc_9E7D
0x9cdc  ldloc.s  7
0x9cde  ldc.i4   0x24B8
0x9ce3  bgt.s    loc_9D0E
0x9ce5  ldloc.s  7
0x9ce7  ldc.i4   0x232C
0x9cec  beq      loc_9E01
0x9cf1  ldloc.s  7
0x9cf3  ldc.i4   0x2454
0x9cf8  beq      loc_9E7D
0x9cfd  ldloc.s  7
0x9cff  ldc.i4   0x24B8
0x9d04  beq      loc_9E7D
0x9d09  br       loc_9E7D
0x9d0e  ldloc.s  7
0x9d10  ldc.i4   0x25E4
0x9d15  beq      loc_9E7D
0x9d1a  ldloc.s  7
0x9d1c  ldc.i4   0x2616
0x9d21  beq      loc_9E7D
0x9d26  ldloc.s  7
0x9d28  ldc.i4   0x2703
0x9d2d  beq      loc_9E74
0x9d32  br       loc_9E7D
0x9d37  ldstr    aKbarticletempl// "kbarticletemplate"
0x9d3c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9d4b  dup
0x9d4c  ldloc.3
0x9d4d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x9d52  dup
0x9d53  ldstr    aIsactive// "isactive"
0x9d58  ldc.i4.1
0x9d59  box      [mscorlib]System.Boolean
0x9d5e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9d63  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x9d68  br       loc_9E84
0x9d6d  ldstr    aService// "service"
0x9d72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d77  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9d81  dup
0x9d82  ldloc.3
0x9d83  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x9d88  dup
0x9d89  ldstr    aIsschedulable// "isschedulable"
0x9d8e  ldc.i4.1
0x9d8f  box      [mscorlib]System.Boolean
0x9d94  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9d99  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x9d9e  br       loc_9E84
0x9da3  ldarg.0
0x9da4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9da9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9dae  ldstr    aIstatecode// "iStateCode"
0x9db3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9db8  stloc.s  8
0x9dba  ldloc.s  8
0x9dbc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9dc1  brtrue   loc_9E84
0x9dc6  ldloc.s  8
0x9dc8  ldc.i4.7
0x9dc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9dce  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
  ... truncated ...
```
