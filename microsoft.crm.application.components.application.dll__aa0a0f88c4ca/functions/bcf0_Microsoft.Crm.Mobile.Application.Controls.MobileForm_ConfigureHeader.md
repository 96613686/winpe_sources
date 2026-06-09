# Microsoft.Crm.Mobile.Application.Controls.MobileForm::ConfigureHeader

- ea: `0xbcf0`
- end: `0xbd3a`
- name: `Microsoft.Crm.Mobile.Application.Controls.MobileForm::ConfigureHeader`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x82fb0`

## string_xrefs

- `0xbcf6`: `LOCID_MEXPRESS_DELETE`
- `0xbd00`: `Espresso_DeleteAll`
- `0xbd15`: `WrpcTokenQSForDelete`

## pseudocode

```c

```

## disassembly

```asm
0xbcf0  ldarg.0
0xbcf1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xbcf6  ldstr    aLocidMexpressD// "LOCID_MEXPRESS_DELETE"
0xbcfb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xbd00  ldstr    aEspressoDelete// "Espresso_DeleteAll"
0xbd05  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbd0a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbd0f  ldarg.0
0xbd10  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xbd15  ldstr    aWrpctokenqsfor// "WrpcTokenQSForDelete"
0xbd1a  ldarg.0
0xbd1b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext Microsoft.Crm.Application.Controls.AppControl::get_CurrentWrpcContext()
0xbd20  ldstr    aMEdAspx// "/m/ed.aspx"
0xbd25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbd2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbd2f  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xbd34  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbd39  ret
```
