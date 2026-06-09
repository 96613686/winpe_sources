# Microsoft.Crm.Application.Bundling.ScriptBundleConfig::GetWebServerBundleUri

- ea: `0x13280`
- end: `0x13345`
- name: `Microsoft.Crm.Application.Bundling.ScriptBundleConfig::GetWebServerBundleUri`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x131d0`

## callees

- `0x12800`
- `0x12820`
- `0x129a0`
- `0x13280`
- `0x13350`

## string_xrefs

- `0x13287`: `/_common/JsProvider.ashx`

## pseudocode

```c

```

## disassembly

```asm
0x13280  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x13285  stloc.0
0x13286  ldloc.0
0x13287  ldstr    aCommonJsprovid// "/_common/JsProvider.ashx"
0x1328c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13291  ldstr    aBundle_0// "?bundle="
0x13296  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1329b  ldarg.0
0x1329c  callvirt instance string Microsoft.Crm.Application.Bundling.JsBundle::get_Name()
0x132a1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x132a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x132ab  ldstr    aVer// "&ver="
0x132b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x132b5  call     string Microsoft.Crm.Application.Bundling.ScriptBundleConfig::get_StaticFileVersionStamp()
0x132ba  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x132bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x132c4  ldstr    aIds// "&ids="
0x132c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x132ce  pop
0x132cf  ldarg.0
0x132d0  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<string> Microsoft.Crm.Application.Bundling.JsBundle::get_Scripts()
0x132d5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x132da  stloc.1
0x132db  br.s     loc_1331A
0x132dd  ldloc.1
0x132de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x132e3  ldc.i4.1
0x132e4  newarr   [mscorlib]System.Char
0x132e9  dup
0x132ea  ldc.i4.0
0x132eb  ldc.i4.s 0x7E
0x132ed  stelem.i2
0x132ee  callvirt instance string [mscorlib]System.String::TrimStart(char[])
0x132f3  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x132f8  call     int32 Microsoft.Crm.Application.Bundling.JsFile::GetHashKey(string path)
0x132fd  stloc.2
0x132fe  ldloc.0
0x132ff  ldloca.s 2
0x13301  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13306  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1330b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13310  pop
0x13311  ldloc.0
0x13312  ldc.i4.s 0x2D
0x13314  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x13319  pop
0x1331a  ldloc.1
0x1331b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13320  brtrue.s loc_132DD
0x13322  leave.s  loc_1332E
0x13324  ldloc.1
0x13325  brfalse.s loc_1332D
0x13327  ldloc.1
0x13328  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1332d  endfinally
0x1332e  ldloc.0
0x1332f  dup
0x13330  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x13335  stloc.3
0x13336  ldloc.3
0x13337  ldc.i4.1
0x13338  sub
0x13339  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x1333e  ldloc.0
0x1333f  callvirt instance string [mscorlib]System.Object::ToString()
0x13344  ret
```
