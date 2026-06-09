# Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl

- ea: `0x1a350`
- end: `0x1a38f`
- name: `Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl`
- size: `63`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x97b0`
- `0xca40`
- `0x16260`
- `0x1a410`
- `0x24a50`
- `0x24eb0`
- `0x253d0`
- `0x284a0`
- `0x29330`
- `0x29540`
- `0x29980`

## callees

- `0x1a0b0`
- `0x1a350`

## pseudocode

```c

```

## disassembly

```asm
0x1a350  call     bool Microsoft.Crm.Application.Components.UI.ImageStrip::get_ImageStripsEnabled()
0x1a355  brfalse.s loc_1A388
0x1a357  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a35c  brfalse.s loc_1A388
0x1a35e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a363  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1a368  brfalse.s loc_1A388
0x1a36a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a36f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1a374  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsInternetExplorer(class [System.Web]System.Web.HttpRequest)
0x1a379  brfalse.s loc_1A382
0x1a37b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsHighContrastEnabled()
0x1a380  brtrue.s loc_1A388
0x1a382  ldsfld   class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStrip::TransparentImagePathUri
0x1a387  ret
0x1a388  ldarg.0
0x1a389  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::_imageStripUrl
0x1a38e  ret
```
