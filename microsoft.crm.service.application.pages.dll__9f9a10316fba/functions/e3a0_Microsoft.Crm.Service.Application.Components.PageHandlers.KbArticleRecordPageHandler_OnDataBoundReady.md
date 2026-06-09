# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::OnDataBoundReady

- ea: `0xe3a0`
- end: `0xe3c6`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::OnDataBoundReady`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xe190`
- `0xe3a0`

## string_xrefs

- `0xe3a6`: `articlexml`

## pseudocode

```c

```

## disassembly

```asm
0xe3a0  ldarg.2
0xe3a1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0xe3a6  ldstr    aArticlexml// "articlexml"
0xe3ab  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xe3b0  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0xe3b5  stloc.0
0xe3b6  ldloc.0
0xe3b7  brfalse.s loc_E3C5
0xe3b9  ldloc.0
0xe3ba  ldarg.0
0xe3bb  call     instance string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXmlValue()
0xe3c0  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xe3c5  ret
```
