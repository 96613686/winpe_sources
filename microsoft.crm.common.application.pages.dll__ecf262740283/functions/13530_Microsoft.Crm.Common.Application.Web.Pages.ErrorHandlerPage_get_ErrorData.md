# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData

- ea: `0x13530`
- end: `0x1356b`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData`
- size: `59`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x134d0`
- `0x13630`
- `0x13810`
- `0x13920`

## callees

- `0x13530`

## pseudocode

```c

```

## disassembly

```asm
0x13530  ldarg.0
0x13531  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_error
0x13536  brtrue.s loc_13564
0x13538  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x1353d  stloc.0
0x1353e  ldarg.0
0x1353f  ldloc.0
0x13540  ldarg.0
0x13541  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13546  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1354b  ldstr    aErrorcode// "ErrorCode"
0x13550  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13555  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1355a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::GetError(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1355f  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_error
0x13564  ldarg.0
0x13565  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_error
0x1356a  ret
```
