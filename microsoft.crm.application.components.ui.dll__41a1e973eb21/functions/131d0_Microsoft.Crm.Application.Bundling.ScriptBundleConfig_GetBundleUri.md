# Microsoft.Crm.Application.Bundling.ScriptBundleConfig::GetBundleUri

- ea: `0x131d0`
- end: `0x1327c`
- name: `Microsoft.Crm.Application.Bundling.ScriptBundleConfig::GetBundleUri`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3d60`
- `0x64a0`
- `0x6560`

## callees

- `0x6b30`
- `0x12800`
- `0x12820`
- `0x131d0`
- `0x13280`
- `0x13390`
- `0x133a0`

## pseudocode

```c

```

## disassembly

```asm
0x131d0  ldarg.0
0x131d1  brtrue.s loc_131E3
0x131d3  ldstr    aBundle// "bundle"
0x131d8  ldstr    aBundleMustBePr// "Bundle must be provided"
0x131dd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string, string)
0x131e2  throw
0x131e3  ldarg.0
0x131e4  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<string> Microsoft.Crm.Application.Bundling.JsBundle::get_Scripts()
0x131e9  callvirt instance int32 class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<string>::get_Count()
0x131ee  brtrue.s loc_13200
0x131f0  ldstr    aBundleScriptsC// "Bundle Scripts collection must not be e"...
0x131f5  ldstr    aBundle// "bundle"
0x131fa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x131ff  throw
0x13200  ldarg.0
0x13201  call     string Microsoft.Crm.Application.Bundling.ScriptBundleConfig::GetWebServerBundleUri(class Microsoft.Crm.Application.Bundling.JsBundle bundle)
0x13206  stloc.0
0x13207  ldsfld   string [mscorlib]System.String::Empty
0x1320c  stloc.1
0x1320d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x13212  stloc.2
0x13213  call     bool Microsoft.Crm.Application.Bundling.JsStaticBundleCDNUtilities::IsCDNStaticBundlingEnabled()
0x13218  brfalse.s loc_1326D
0x1321a  call     string Microsoft.Crm.Application.Bundling.JsStaticBundleCDNUtilities::GetCDNServerURL()
0x1321f  stloc.1
0x13220  ldloc.2
0x13221  ldloc.1
0x13222  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x13227  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1322c  ldstr    aJsbundles// "jsbundles/"
0x13231  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13236  ldarg.0
0x13237  callvirt instance string Microsoft.Crm.Application.Bundling.JsBundle::get_Name()
0x1323c  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x13241  ldstr    aJs// ".js"
0x13246  call     string [mscorlib]System.String::Concat(string, string)
0x1324b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x13250  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13255  ldstr    aFallbackurl// "?fallbackURL="
0x1325a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1325f  ldloc.0
0x13260  call     string Microsoft.Crm.Controls.PageResourceManager::GetEncodedUri(string inputUrl)
0x13265  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1326a  pop
0x1326b  br.s     loc_13275
0x1326d  ldloc.2
0x1326e  ldloc.0
0x1326f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13274  pop
0x13275  ldloc.2
0x13276  callvirt instance string [mscorlib]System.Object::ToString()
0x1327b  ret
```
