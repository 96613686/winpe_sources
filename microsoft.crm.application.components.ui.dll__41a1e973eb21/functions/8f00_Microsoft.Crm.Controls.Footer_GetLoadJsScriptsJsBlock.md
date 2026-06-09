# Microsoft.Crm.Controls.Footer::GetLoadJsScriptsJsBlock

- ea: `0x8f00`
- end: `0x90a8`
- name: `Microsoft.Crm.Controls.Footer::GetLoadJsScriptsJsBlock`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x91a0`

## callees

- `0x22f0`
- `0x2360`
- `0x2440`
- `0x25e0`
- `0x8bb0`
- `0x8c60`
- `0x8f00`
- `0x90b0`
- `0xa340`

## string_xrefs

- `0x8f96`: `/_static/_common/scripts/jquery-2.1.1.min.js`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8f05  stloc.0
0x8f06  ldarg.0
0x8f07  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_OutlookStageContext()
0x8f0c  brfalse.s loc_8F1C
0x8f0e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x8f13  brfalse.s loc_8F1C
0x8f15  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x8f1a  br.s     loc_8F1D
0x8f1c  ldc.i4.0
0x8f1d  stloc.1
0x8f1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f23  ldstr    aLoadscriptadv0_0// "loadScriptAdv({{0}}, {{1}}, {0});"
0x8f28  ldc.i4.1
0x8f29  newarr   [mscorlib]System.Object
0x8f2e  dup
0x8f2f  ldc.i4.0
0x8f30  ldloc.1
0x8f31  brtrue.s loc_8F3A
0x8f33  ldstr    aFalse// "false"
0x8f38  br.s     loc_8F3F
0x8f3a  ldstr    aTrue// "true"
0x8f3f  stelem.ref
0x8f40  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8f45  stloc.2
0x8f46  ldarg.1
0x8f47  ldc.i4.1
0x8f48  and
0x8f49  ldc.i4.0
0x8f4a  ble.s    loc_8F54
0x8f4c  ldarg.0
0x8f4d  ldloc.0
0x8f4e  ldloc.1
0x8f4f  call     instance void Microsoft.Crm.Controls.Footer::AppendGlobalScriptsLoader(class [mscorlib]System.Text.StringBuilder jsSnippet, bool needOutlookCookiesPreloader)
0x8f54  ldarg.1
0x8f55  ldc.i4.2
0x8f56  and
0x8f57  ldc.i4.0
0x8f58  ble.s    loc_8F8E
0x8f5a  ldarg.0
0x8f5b  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x8f60  brtrue.s loc_8F8E
0x8f62  ldarg.0
0x8f63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.ScriptResource::get_ScriptResourceInclude()
0x8f68  call     instance string Microsoft.Crm.Controls.Footer::GetHeaderListItemUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri headerListItem)
0x8f6d  stloc.3
0x8f6e  ldloc.0
0x8f6f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f74  ldloc.2
0x8f75  ldc.i4.2
0x8f76  newarr   [mscorlib]System.Object
0x8f7b  dup
0x8f7c  ldc.i4.0
0x8f7d  ldloc.3
0x8f7e  stelem.ref
0x8f7f  dup
0x8f80  ldc.i4.1
0x8f81  ldloc.3
0x8f82  stelem.ref
0x8f83  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8f88  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8f8d  pop
0x8f8e  ldarg.0
0x8f8f  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadJQuery()
0x8f94  brfalse.s loc_9008
0x8f96  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/jquery-2.1.1.m"...
0x8f9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fa0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fa5  stloc.s  4
0x8fa7  ldarg.0
0x8fa8  ldloc.s  4
0x8faa  call     instance string[] Microsoft.Crm.Controls.Footer::GetHeaderListItemUrlWithDependencies(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri headerListItem)
0x8faf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8fb4  stloc.s  5
0x8fb6  stloc.s  6
0x8fb8  ldc.i4.0
0x8fb9  stloc.s  7
0x8fbb  br.s     loc_9000
0x8fbd  ldloc.s  6
0x8fbf  ldloc.s  7
0x8fc1  ldelem.ref
0x8fc2  stloc.s  8
0x8fc4  ldloc.s  5
0x8fc6  ldloc.s  8
0x8fc8  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x8fcd  brtrue.s loc_8FFA
0x8fcf  ldloc.0
0x8fd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fd5  ldloc.2
0x8fd6  ldc.i4.2
0x8fd7  newarr   [mscorlib]System.Object
0x8fdc  dup
0x8fdd  ldc.i4.0
0x8fde  ldloc.s  8
0x8fe0  stelem.ref
0x8fe1  dup
0x8fe2  ldc.i4.1
0x8fe3  ldloc.s  8
0x8fe5  stelem.ref
0x8fe6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8feb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8ff0  pop
0x8ff1  ldloc.s  5
0x8ff3  ldloc.s  8
0x8ff5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ffa  ldloc.s  7
0x8ffc  ldc.i4.1
0x8ffd  add
0x8ffe  stloc.s  7
0x9000  ldloc.s  7
0x9002  ldloc.s  6
0x9004  ldlen
0x9005  conv.i4
0x9006  blt.s    loc_8FBD
0x9008  ldarg.1
0x9009  ldc.i4.4
0x900a  and
0x900b  ldc.i4.0
0x900c  ble      loc_90A1
0x9011  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x9016  stloc.s  9
0x9018  ldarg.0
0x9019  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::get_Scripts()
0x901e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::GetEnumerator()
0x9023  stloc.s  0xA
0x9025  br.s     loc_908A
0x9027  ldloc.s  0xA
0x9029  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Current()
0x902e  stloc.s  0xB
0x9030  ldarg.0
0x9031  ldloc.s  0xB
0x9033  call     instance string[] Microsoft.Crm.Controls.Footer::GetHeaderListItemUrlWithDependencies(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri headerListItem)
0x9038  stloc.s  6
0x903a  ldc.i4.0
0x903b  stloc.s  7
0x903d  br.s     loc_9082
0x903f  ldloc.s  6
0x9041  ldloc.s  7
0x9043  ldelem.ref
0x9044  stloc.s  0xC
0x9046  ldloc.s  9
0x9048  ldloc.s  0xC
0x904a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x904f  brtrue.s loc_907C
0x9051  ldloc.0
0x9052  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9057  ldloc.2
0x9058  ldc.i4.2
0x9059  newarr   [mscorlib]System.Object
0x905e  dup
0x905f  ldc.i4.0
0x9060  ldloc.s  0xC
0x9062  stelem.ref
0x9063  dup
0x9064  ldc.i4.1
0x9065  ldloc.s  0xC
0x9067  stelem.ref
0x9068  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x906d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9072  pop
0x9073  ldloc.s  9
0x9075  ldloc.s  0xC
0x9077  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x907c  ldloc.s  7
0x907e  ldc.i4.1
0x907f  add
0x9080  stloc.s  7
0x9082  ldloc.s  7
0x9084  ldloc.s  6
0x9086  ldlen
0x9087  conv.i4
0x9088  blt.s    loc_903F
0x908a  ldloc.s  0xA
0x908c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9091  brtrue.s loc_9027
0x9093  leave.s  loc_90A1
0x9095  ldloc.s  0xA
0x9097  brfalse.s loc_90A0
0x9099  ldloc.s  0xA
0x909b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x90a0  endfinally
0x90a1  ldloc.0
0x90a2  callvirt instance string [mscorlib]System.Object::ToString()
0x90a7  ret
```
