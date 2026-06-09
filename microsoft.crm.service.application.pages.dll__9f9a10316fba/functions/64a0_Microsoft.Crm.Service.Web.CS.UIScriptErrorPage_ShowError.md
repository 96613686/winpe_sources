# Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowError

- ea: `0x64a0`
- end: `0x6555`
- name: `Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowError`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6430`

## callees

- `0x64a0`
- `0x65f0`
- `0x6620`

## pseudocode

```c

```

## disassembly

```asm
0x64a0  ldc.i4   0x8004F211
0x64a5  ldarg.1
0x64a6  bne.un.s loc_64C1
0x64a8  ldarg.0
0x64a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x64ae  ldstr    aWebUiscriptsUi// "Web.UIScripts.UIImportError.InvalidUISc"...
0x64b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x64b8  stloc.0
0x64b9  ldarg.0
0x64ba  ldloc.0
0x64bb  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowImportError(string description)
0x64c0  ret
0x64c1  ldc.i4   0x8004F212
0x64c6  ldarg.1
0x64c7  bne.un.s loc_64E2
0x64c9  ldarg.0
0x64ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x64cf  ldstr    aWebUiscriptsUi_0// "Web.UIScripts.UIImportError.ErrorScript"...
0x64d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x64d9  stloc.1
0x64da  ldarg.0
0x64db  ldloc.1
0x64dc  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowImportError(string description)
0x64e1  ret
0x64e2  ldc.i4   0x80048296
0x64e7  ldarg.1
0x64e8  bne.un.s loc_6503
0x64ea  ldarg.0
0x64eb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x64f0  ldstr    aWebUiscriptsUi_1// "Web.UIScripts.UIImportError.ReportFileZ"...
0x64f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x64fa  stloc.2
0x64fb  ldarg.0
0x64fc  ldloc.2
0x64fd  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowImportError(string description)
0x6502  ret
0x6503  ldarga.s 1
0x6505  ldstr    aX// "X"
0x650a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x650f  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x6514  stloc.3
0x6515  ldarg.0
0x6516  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x651b  ldstr    aErrorTitle0x// "Error_Title_0x"
0x6520  ldloc.3
0x6521  call     string [mscorlib]System.String::Concat(string, string)
0x6526  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x652b  stloc.s  4
0x652d  ldarg.0
0x652e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6533  ldstr    aErrorMessage0x// "Error_Message_0x"
0x6538  ldloc.3
0x6539  call     string [mscorlib]System.String::Concat(string, string)
0x653e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6543  stloc.s  5
0x6545  ldarg.0
0x6546  ldstr    asc_15D82// ""
0x654b  ldloc.s  4
0x654d  ldloc.s  5
0x654f  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowStandardDialog(string header, string title, string message)
0x6554  ret
```
