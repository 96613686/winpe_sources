# Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeItemRecordPageHandler::ConfigureFormHandler

- ea: `0x122d0`
- end: `0x123b6`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeItemRecordPageHandler::ConfigureFormHandler`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x122d0`

## string_xrefs

- `0x12310`: `_CreateFromId`
- `0x1234a`: `<columnset><column>isamounttype</column></columnset>`
- `0x1235b`: `isamounttype`
- `0x12378`: `isamounttype`
- `0x123a5`: `IS_AMOUNT_TYPE`

## pseudocode

```c

```

## disassembly

```asm
0x122d0  ldarg.0
0x122d1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x122d6  ldarg.0
0x122d7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x122dc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x122e1  ldarg.0
0x122e2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x122e7  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x122ec  ldc.i4.1
0x122ed  bne.un.s loc_1236C
0x122ef  ldstr    aDiscounttype// "discounttype"
0x122f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x122f9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x122fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x12303  stloc.0
0x12304  ldloc.0
0x12305  ldarg.0
0x12306  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x1230b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12310  ldstr    aCreatefromid// "_CreateFromId"
0x12315  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1231a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1231f  ldloc.0
0x12320  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x12325  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::IsValidGuid(string)
0x1232a  ldstr    aInvalid// "Invalid "
0x1232f  ldc.i4   0x3F5
0x12334  ldc.i4.1
0x12335  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1233a  ldstr    aTypeGuid// " Type GUID"
0x1233f  call     string [mscorlib]System.String::Concat(string, string, string)
0x12344  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x12349  ldloc.0
0x1234a  ldstr    aColumnsetColum_1// "<columnset><column>isamounttype</column"...
0x1234f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x12354  ldarg.0
0x12355  ldloc.0
0x12356  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x1235b  ldstr    aIsamounttype// "isamounttype"
0x12360  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x12365  stfld    bool Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeItemRecordPageHandler::_isAmountType
0x1236a  br.s     loc_1239F
0x1236c  ldarg.0
0x1236d  ldarg.0
0x1236e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x12373  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_DataXml()
0x12378  ldstr    aIsamounttype// "isamounttype"
0x1237d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x12382  stfld    bool Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeItemRecordPageHandler::_isAmountType
0x12387  ldarg.0
0x12388  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x1238d  ldarg.0
0x1238e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0x12393  ldc.i4.1
0x12394  ldnull
0x12395  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x1239a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x1239f  ldarg.0
0x123a0  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x123a5  ldstr    aIsAmountType// "IS_AMOUNT_TYPE"
0x123aa  ldarg.0
0x123ab  ldfld    bool Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeItemRecordPageHandler::_isAmountType
0x123b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x123b5  ret
```
