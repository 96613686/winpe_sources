# Microsoft.Xrm.Async.Bridges.WebApp.HttpRequestMessageExtensions::GetHeaderValue

- ea: `0x10`
- end: `0x64`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.HttpRequestMessageExtensions::GetHeaderValue`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x16  stloc.0
0x17  ldloc.0
0x18  ldarg.1
0x19  ldloca.s 1
0x1b  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryGetValues(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>&)
0x20  brtrue.s loc_2D
0x22  ldloca.s 4
0x24  initobj  mvar<u1>
0x2a  ldloc.s  4
0x2c  ret
0x2d  ldloc.1
0x2e  call     T0x2B000001
0x33  stloc.2
0x34  ldloc.2
0x35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a  brfalse.s loc_47
0x3c  ldloca.s 4
0x3e  initobj  mvar<u1>
0x44  ldloc.s  4
0x46  ret
0x47  ldtoken  mvar<u1>
0x4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x51  call     class [System]System.ComponentModel.TypeConverter [System]System.ComponentModel.TypeDescriptor::GetConverter(class [mscorlib]System.Type)
0x56  stloc.3
0x57  ldloc.3
0x58  ldloc.2
0x59  callvirt instance object [System]System.ComponentModel.TypeConverter::ConvertFromInvariantString(string)
0x5e  unbox.any mvar<u1>
0x63  ret
```
