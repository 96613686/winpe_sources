# Microsoft.Crm.ParameterFilterBase::TryValidateParameter

- ea: `0x1200`
- end: `0x128e`
- name: `Microsoft.Crm.ParameterFilterBase::TryValidateParameter`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1300`

## callees

- `0x930`
- `0x940`
- `0x960`
- `0x1200`
- `0x1290`

## pseudocode

```c

```

## disassembly

```asm
0x1200  ldc.i4.0
0x1201  stloc.0
0x1202  ldarg.1
0x1203  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1208  stloc.1
0x1209  br.s     loc_1271
0x120b  ldloc.1
0x120c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1211  castclass Microsoft.Crm.IWebParameter
0x1216  stloc.2
0x1217  ldloc.2
0x1218  callvirt instance bool Microsoft.Crm.IWebParameter::get_IsPassThrough()
0x121d  brfalse.s loc_1253
0x121f  ldloc.2
0x1220  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0x1225  ldarg.s  4
0x1227  and
0x1228  brfalse.s loc_1253
0x122a  ldarg.2
0x122b  brtrue.s loc_1235
0x122d  ldloc.2
0x122e  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0x1233  brfalse.s loc_124F
0x1235  ldarg.2
0x1236  brfalse.s loc_1271
0x1238  ldloc.2
0x1239  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0x123e  brfalse.s loc_1271
0x1240  ldarg.2
0x1241  ldloc.2
0x1242  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0x1247  ldc.i4.5
0x1248  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x124d  brtrue.s loc_1271
0x124f  ldc.i4.1
0x1250  stloc.0
0x1251  leave.s  loc_128C
0x1253  ldarg.2
0x1254  ldloc.2
0x1255  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0x125a  ldc.i4.5
0x125b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1260  brtrue.s loc_1271
0x1262  ldarg.0
0x1263  ldloc.2
0x1264  ldarg.2
0x1265  ldarg.3
0x1266  ldarg.s  4
0x1268  callvirt instance void Microsoft.Crm.ParameterFilterBase::ValidateParameter(class Microsoft.Crm.IWebParameter parameter, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x126d  ldc.i4.1
0x126e  stloc.0
0x126f  leave.s  loc_128C
0x1271  ldloc.1
0x1272  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1277  brtrue.s loc_120B
0x1279  leave.s  loc_128C
0x127b  ldloc.1
0x127c  isinst   [mscorlib]System.IDisposable
0x1281  stloc.3
0x1282  ldloc.3
0x1283  brfalse.s loc_128B
0x1285  ldloc.3
0x1286  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x128b  endfinally
0x128c  ldloc.0
0x128d  ret
```
