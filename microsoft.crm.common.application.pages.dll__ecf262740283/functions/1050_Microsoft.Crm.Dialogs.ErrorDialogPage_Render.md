# Microsoft.Crm.Dialogs.ErrorDialogPage::Render

- ea: `0x1050`
- end: `0x109b`
- name: `Microsoft.Crm.Dialogs.ErrorDialogPage::Render`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1050`
- `0x10a0`

## string_xrefs

- `0x106f`: `excelDownloadToken`
- `0x1086`: `excelDownloadToken`

## pseudocode

```c

```

## disassembly

```asm
0x1050  ldarg.0
0x1051  ldarg.1
0x1052  call     instance void [System.Web]System.Web.UI.Page::Render(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1057  ldarg.0
0x1058  call     instance int32 Microsoft.Crm.Dialogs.ErrorDialogPage::GetErrorCodeNumber()
0x105d  ldc.i4   0x800608C7
0x1062  bne.un.s loc_109A
0x1064  ldarg.0
0x1065  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x106a  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0x106f  ldstr    aExceldownloadt// "excelDownloadToken"
0x1074  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x1079  brfalse.s loc_109A
0x107b  ldarg.0
0x107c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1081  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x1086  ldstr    aExceldownloadt// "excelDownloadToken"
0x108b  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x1090  ldstr    a2// "-2"
0x1095  callvirt instance void [System.Web]System.Web.HttpCookie::set_Value(string)
0x109a  ret
```
