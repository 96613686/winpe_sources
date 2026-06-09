# Microsoft.Crm.Controls.Header::AddDownloadNoOpenMetaTag

- ea: `0x6eb0`
- end: `0x6ed1`
- name: `Microsoft.Crm.Controls.Header::AddDownloadNoOpenMetaTag`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6eb0`

## string_xrefs

- `0x6eb0`: `<meta name="DownloadOptions" content="noopen" />`

## pseudocode

```c

```

## disassembly

```asm
0x6eb0  ldstr    aMetaNameDownlo// "<meta name=\"DownloadOptions\" content="...
0x6eb5  stloc.0
0x6eb6  ldarg.0
0x6eb7  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.Header::_metaTags
0x6ebc  ldloc.0
0x6ebd  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x6ec2  brtrue.s loc_6ED0
0x6ec4  ldarg.0
0x6ec5  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.Header::_metaTags
0x6eca  ldloc.0
0x6ecb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6ed0  ret
```
