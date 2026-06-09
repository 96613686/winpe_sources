# Microsoft.Crm.Application.Components.Handlers.WebResource::GetMimeType

- ea: `0xe0f40`
- end: `0xe0fc8`
- name: `Microsoft.Crm.Application.Components.Handlers.WebResource::GetMimeType`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xe0dd0`

## callees

- `0xe0f40`

## string_xrefs

- `0xe0f8c`: `text/xml`
- `0xe0faa`: `text/xml`
- `0xe0fb6`: `image/svg+xml`

## pseudocode

```c

```

## disassembly

```asm
0xe0f40  ldarg.0
0xe0f41  ldc.i4.1
0xe0f42  sub
0xe0f43  switch   loc_E0F7A, loc_E0F80, loc_E0F86, loc_E0F8C, loc_E0F92, loc_E0F98, loc_E0F9E, loc_E0FA4, loc_E0FAA, loc_E0FB0, loc_E0FB6, loc_E0FBC
0xe0f78  br.s     loc_E0FC2
0xe0f7a  ldstr    aTextHtml// "text/html"
0xe0f7f  ret
0xe0f80  ldstr    aTextCss// "text/css"
0xe0f85  ret
0xe0f86  ldstr    aTextJscript// "text/jscript"
0xe0f8b  ret
0xe0f8c  ldstr    aTextXml// "text/xml"
0xe0f91  ret
0xe0f92  ldstr    aImagePng// "image/png"
0xe0f97  ret
0xe0f98  ldstr    aImageJpeg// "image/jpeg"
0xe0f9d  ret
0xe0f9e  ldstr    aImageGif// "image/gif"
0xe0fa3  ret
0xe0fa4  ldstr    aApplicationXSi// "application/x-silverlight-app"
0xe0fa9  ret
0xe0faa  ldstr    aTextXml// "text/xml"
0xe0faf  ret
0xe0fb0  ldstr    aImageXIcon// "image/x-icon"
0xe0fb5  ret
0xe0fb6  ldstr    aImageSvgXml// "image/svg+xml"
0xe0fbb  ret
0xe0fbc  ldstr    aTextResx// "text/resx"
0xe0fc1  ret
0xe0fc2  ldstr    asc_F537C// ""
0xe0fc7  ret
```
