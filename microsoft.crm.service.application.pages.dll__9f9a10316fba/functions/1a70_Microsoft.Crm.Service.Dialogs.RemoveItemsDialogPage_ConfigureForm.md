# Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::ConfigureForm

- ea: `0x1a70`
- end: `0x1c3a`
- name: `Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::ConfigureForm`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1a70`

## string_xrefs

- `0x1be9`: `Dialog_RemoveMembers_Title`
- `0x1c03`: `Dialog_RemoveMembers_Description`

## pseudocode

```c

```

## disassembly

```asm
0x1a70  ldarg.0
0x1a71  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1a76  ldarg.0
0x1a77  ldarg.0
0x1a78  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a7d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a82  ldstr    aItotal// "iTotal"
0x1a87  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a8c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a91  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1a96  stfld    int32 Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::total
0x1a9b  ldarg.0
0x1a9c  ldc.i4   0xFA7
0x1aa1  stfld    int32 Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::objType
0x1aa6  ldarg.0
0x1aa7  ldarg.0
0x1aa8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1aad  ldarg.0
0x1aae  ldfld    int32 Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::total
0x1ab3  ldc.i4.1
0x1ab4  bgt.s    loc_1ABD
0x1ab6  ldstr    aItemNameSingul// "Item_Name_Singular"
0x1abb  br.s     loc_1AC2
0x1abd  ldstr    aItemNamePlural// "Item_Name_Plural"
0x1ac2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ac7  stfld    string Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::objName
0x1acc  ldarg.0
0x1acd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1ad2  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1ad7  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1adc  ldc.i4.0
0x1add  conv.i8
0x1ade  ble      loc_1BD7
0x1ae3  ldc.i4.1
0x1ae4  newarr   [mscorlib]System.String
0x1ae9  dup
0x1aea  ldc.i4.0
0x1aeb  ldarg.0
0x1aec  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1af1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1af6  ldstr    aIid// "iId"
0x1afb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b00  stelem.ref
0x1b01  dup
0x1b02  ldlen
0x1b03  conv.i4
0x1b04  newarr   [mscorlib]System.Guid
0x1b09  stloc.0
0x1b0a  ldc.i4.0
0x1b0b  stloc.1
0x1b0c  stloc.s  4
0x1b0e  ldc.i4.0
0x1b0f  stloc.s  5
0x1b11  br.s     loc_1B2E
0x1b13  ldloc.s  4
0x1b15  ldloc.s  5
0x1b17  ldelem.ref
0x1b18  stloc.s  6
0x1b1a  ldloc.0
0x1b1b  ldloc.1
0x1b1c  ldloc.s  6
0x1b1e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b23  stelem   [mscorlib]System.Guid
0x1b28  ldloc.s  5
0x1b2a  ldc.i4.1
0x1b2b  add
0x1b2c  stloc.s  5
0x1b2e  ldloc.s  5
0x1b30  ldloc.s  4
0x1b32  ldlen
0x1b33  conv.i4
0x1b34  blt.s    loc_1B13
0x1b36  ldarg.0
0x1b37  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b3c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b41  ldstr    aGroupid// "groupid"
0x1b46  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b4b  stloc.2
0x1b4c  ldc.i4.1
0x1b4d  newarr   [mscorlib]System.String
0x1b52  dup
0x1b53  ldc.i4.0
0x1b54  ldstr    aObjecttypecode// "objecttypecode"
0x1b59  stelem.ref
0x1b5a  stloc.3
0x1b5b  ldstr    aResourcegroup// "resourcegroup"
0x1b60  ldloc.2
0x1b61  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b66  ldloc.3
0x1b67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b6c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b71  ldstr    aObjecttypecode// "objecttypecode"
0x1b76  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1b7b  unbox.any [mscorlib]System.Int32
0x1b80  ldc.i4   0xFA7
0x1b85  bne.un.s loc_1BC4
0x1b87  ldc.i4.1
0x1b88  newarr   [mscorlib]System.String
0x1b8d  dup
0x1b8e  ldc.i4.0
0x1b8f  ldstr    aGrouptypecode// "grouptypecode"
0x1b94  stelem.ref
0x1b95  pop
0x1b96  ldstr    aConstraintbase// "constraintbasedgroup"
0x1b9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ba0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba5  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ConstraintBasedGroup::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1baa  dup
0x1bab  ldloc.2
0x1bac  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1bb1  dup
0x1bb2  ldc.i4.0
0x1bb3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0x1bb8  dup
0x1bb9  ldloc.0
0x1bba  callvirt instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ConstraintBasedGroup::RemoveMembers(valuetype [mscorlib]System.Guid[])
0x1bbf  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1bc4  ldarg.0
0x1bc5  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1bca  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x1bcf  leave.s  loc_1BD7
0x1bd1  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1bd6  throw
0x1bd7  ldarg.0
0x1bd8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1bdd  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1be2  dup
0x1be3  ldarg.0
0x1be4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1be9  ldstr    aDialogRemoveme// "Dialog_RemoveMembers_Title"
0x1bee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1bf3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1bf8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bfd  ldarg.0
0x1bfe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1c03  ldstr    aDialogRemoveme_0// "Dialog_RemoveMembers_Description"
0x1c08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c0d  ldc.i4.2
0x1c0e  newarr   [mscorlib]System.Object
0x1c13  dup
0x1c14  ldc.i4.0
0x1c15  ldarg.0
0x1c16  ldflda   int32 Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::total
0x1c1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c20  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c25  stelem.ref
0x1c26  dup
0x1c27  ldc.i4.1
0x1c28  ldarg.0
0x1c29  ldfld    string Microsoft.Crm.Service.Dialogs.RemoveItemsDialogPage::objName
0x1c2e  stelem.ref
0x1c2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c34  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1c39  ret
```
