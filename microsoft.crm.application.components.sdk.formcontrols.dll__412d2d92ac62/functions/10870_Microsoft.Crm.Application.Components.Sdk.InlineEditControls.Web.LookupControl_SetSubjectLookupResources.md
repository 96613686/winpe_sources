# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::SetSubjectLookupResources

- ea: `0x10870`
- end: `0x108b4`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::SetSubjectLookupResources`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf6d0`

## callees

- `0xe430`

## string_xrefs

- `0x1087c`: `/_static/_common/scripts/jquery.hotkeys.js`
- `0x10887`: `/_static/_common/scripts/jquery.jstree.js`

## pseudocode

```c

```

## disassembly

```asm
0x10870  ldarg.0
0x10871  ldstr    aStaticControls_9// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x10876  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1087b  ldarg.0
0x1087c  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/jquery.hotkeys"...
0x10881  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x10886  ldarg.0
0x10887  ldstr    aStaticCommonSc_10// "/_static/_common/scripts/jquery.jstree."...
0x1088c  ldc.i4.2
0x1088d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFileWithStage(string, valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ScriptLoadingStage)
0x10892  ldarg.0
0x10893  ldstr    aLocidJstreeLoa// "LOCID_JSTREE_LOADING"
0x10898  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1089d  ldstr    aJstreeLoading// "Jstree.Loading"
0x108a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x108a7  ldc.i4.0
0x108a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x108ad  ldarg.0
0x108ae  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigurePresenceSupport(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager currentHeader)
0x108b3  ret
```
