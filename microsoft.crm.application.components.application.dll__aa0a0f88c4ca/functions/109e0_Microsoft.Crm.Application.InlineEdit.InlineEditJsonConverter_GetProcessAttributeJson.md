# Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetProcessAttributeJson

- ea: `0x109e0`
- end: `0x10b33`
- name: `Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetProcessAttributeJson`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0xf1530`

## callees

- `0x109e0`

## string_xrefs

- `0x109f6`: `{{"activeStageId":"{0}", "traversedPath":"{1}", "businessProcessInstanceId":"{2}", "businessProcessState":"{3}", "businessProcessStatus":"{4}"}}`
- `0x10a26`: `TraversedPath`
- `0x10a3a`: `TraversedPath`
- `0x10b27`: `TraversedPath`
- `0x10ab6`: `{{"_globalNavigationData":{0}, "_processId":"{1}"}}`
- `0x10ac8`: `ProcessId`
- `0x10adc`: `ProcessId`
- `0x10b0f`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0x109e0  ldarg.0
0x109e1  brfalse.s loc_109EB
0x109e3  ldarg.0
0x109e4  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x109e9  brtrue.s loc_109F1
0x109eb  ldsfld   string [mscorlib]System.String::Empty
0x109f0  ret
0x109f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x109f6  ldstr    aActivestageid0// "{{\"activeStageId\":\"{0}\", \"traverse"...
0x109fb  ldc.i4.5
0x109fc  newarr   [mscorlib]System.Object
0x10a01  dup
0x10a02  ldc.i4.0
0x10a03  ldarg.0
0x10a04  ldstr    aActivestageid// "ActiveStageId"
0x10a09  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x10a0e  brtrue.s loc_10A17
0x10a10  ldsfld   string [mscorlib]System.String::Empty
0x10a15  br.s     loc_10A22
0x10a17  ldarg.0
0x10a18  ldstr    aActivestageid// "ActiveStageId"
0x10a1d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x10a22  stelem.ref
0x10a23  dup
0x10a24  ldc.i4.1
0x10a25  ldarg.0
0x10a26  ldstr    aTraversedpath// "TraversedPath"
0x10a2b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x10a30  brtrue.s loc_10A39
0x10a32  ldsfld   string [mscorlib]System.String::Empty
0x10a37  br.s     loc_10A44
0x10a39  ldarg.0
0x10a3a  ldstr    aTraversedpath// "TraversedPath"
0x10a3f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x10a44  stelem.ref
0x10a45  dup
0x10a46  ldc.i4.2
0x10a47  ldarg.0
0x10a48  ldstr    aProcessinstanc// "processinstanceid"
0x10a4d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x10a52  brtrue.s loc_10A5B
0x10a54  ldsfld   string [mscorlib]System.String::Empty
0x10a59  br.s     loc_10A66
0x10a5b  ldarg.0
0x10a5c  ldstr    aProcessinstanc// "processinstanceid"
0x10a61  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x10a66  stelem.ref
0x10a67  dup
0x10a68  ldc.i4.3
0x10a69  ldarg.0
0x10a6a  ldstr    aStatecode// "statecode"
0x10a6f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x10a74  brtrue.s loc_10A7D
0x10a76  ldsfld   string [mscorlib]System.String::Empty
0x10a7b  br.s     loc_10A88
0x10a7d  ldarg.0
0x10a7e  ldstr    aStatecode// "statecode"
0x10a83  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x10a88  stelem.ref
0x10a89  dup
0x10a8a  ldc.i4.4
0x10a8b  ldarg.0
0x10a8c  ldstr    aStatuscode// "statuscode"
0x10a91  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x10a96  brtrue.s loc_10A9F
0x10a98  ldsfld   string [mscorlib]System.String::Empty
0x10a9d  br.s     loc_10AAA
0x10a9f  ldarg.0
0x10aa0  ldstr    aStatuscode// "statuscode"
0x10aa5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x10aaa  stelem.ref
0x10aab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10ab0  stloc.0
0x10ab1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10ab6  ldstr    aGlobalnavigati// "{{\"_globalNavigationData\":{0}, \"_pro"...
0x10abb  ldc.i4.2
0x10abc  newarr   [mscorlib]System.Object
0x10ac1  dup
0x10ac2  ldc.i4.0
0x10ac3  ldloc.0
0x10ac4  stelem.ref
0x10ac5  dup
0x10ac6  ldc.i4.1
0x10ac7  ldarg.0
0x10ac8  ldstr    aProcessid// "ProcessId"
0x10acd  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x10ad2  brtrue.s loc_10ADB
0x10ad4  ldsfld   string [mscorlib]System.String::Empty
0x10ad9  br.s     loc_10AE6
0x10adb  ldarg.0
0x10adc  ldstr    aProcessid// "ProcessId"
0x10ae1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x10ae6  stelem.ref
0x10ae7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10aec  stloc.1
0x10aed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10af2  ldstr    a01_1// "\"{0}\":{1}"
0x10af7  ldc.i4.2
0x10af8  newarr   [mscorlib]System.Object
0x10afd  dup
0x10afe  ldc.i4.0
0x10aff  ldstr    aProcesscontrol// "_processControlDataKey"
0x10b04  stelem.ref
0x10b05  dup
0x10b06  ldc.i4.1
0x10b07  ldloc.1
0x10b08  stelem.ref
0x10b09  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10b0e  ldarg.0
0x10b0f  ldstr    aProcessid// "ProcessId"
0x10b14  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x10b19  pop
0x10b1a  ldarg.0
0x10b1b  ldstr    aActivestageid// "ActiveStageId"
0x10b20  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x10b25  pop
0x10b26  ldarg.0
0x10b27  ldstr    aTraversedpath// "TraversedPath"
0x10b2c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x10b31  pop
0x10b32  ret
```
