# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::get_YammerEmbedScriptURL

- ea: `0x7f00`
- end: `0x7f24`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::get_YammerEmbedScriptURL`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x7f0a`: `https://assets.yammer.com/platform/yam.js`

## pseudocode

```c

```

## disassembly

```asm
0x7f00  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x7f05  ldstr    aYammerembedscr// "YammerEmbedScriptURL"
0x7f0a  ldstr    aHttpsAssetsYam// "https://assets.yammer.com/platform/yam."...
0x7f0f  callvirt T0x2B000003
0x7f14  ldstr    aPlatformYamJs// "platform/yam.js"
0x7f19  ldstr    aAssetsPlatform// "assets/platform_embed.js"
0x7f1e  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x7f23  ret
```
