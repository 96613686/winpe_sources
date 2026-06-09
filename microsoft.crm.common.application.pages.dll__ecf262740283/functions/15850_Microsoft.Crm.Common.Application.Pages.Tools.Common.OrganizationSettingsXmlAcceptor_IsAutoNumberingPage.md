# Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::IsAutoNumberingPage

- ea: `0x15850`
- end: `0x1586b`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::IsAutoNumberingPage`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15240`

## string_xrefs

- `0x15860`: `Tools/AutoNumbering/cmds/cmd_update.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x15850  ldarg.0
0x15851  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x15856  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1585b  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x15860  ldstr    aToolsAutonumbe// "Tools/AutoNumbering/cmds/cmd_update.asp"...
0x15865  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x1586a  ret
```
