# Microsoft.Crm.Extensibility.RetryHelper::IsSolutionImportRetryEnabledInternal

- ea: `0xc490`
- end: `0xc61e`
- name: `Microsoft.Crm.Extensibility.RetryHelper::IsSolutionImportRetryEnabledInternal`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2faa0`

## callees

- `0xc490`

## string_xrefs

- `0xc4c1`: `SolutionImportRetryAttempts`

## pseudocode

```c

```

## disassembly

```asm
0xc490  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xc495  stloc.0
0xc496  ldstr    aUsesolutionimp// "UseSolutionImportRetry"
0xc49b  ldloca.s 4
0xc49d  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0xc4a3  ldloc.s  4
0xc4a5  call     T0x2B000043
0xc4aa  stloc.1
0xc4ab  ldarg.0
0xc4ac  ldstr    aUsesolutionimp// "UseSolutionImportRetry"
0xc4b1  ldloca.s 4
0xc4b3  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0xc4b9  ldloc.s  4
0xc4bb  call     T0x2B000044
0xc4c0  stloc.2
0xc4c1  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xc4c6  ldnull
0xc4c7  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xc4cc  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xc4d1  stloc.3
0xc4d2  ldloc.0
0xc4d3  ldstr    aSgretryvalue// "SGRetryValue"
0xc4d8  ldloca.s 1
0xc4da  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc4df  brtrue.s loc_C4E8
0xc4e1  ldstr    aNotset// "NotSet"
0xc4e6  br.s     loc_C4F5
0xc4e8  ldloca.s 1
0xc4ea  constrained. valuetype [mscorlib]System.Nullable`1<bool>
0xc4f0  callvirt instance string [mscorlib]System.Object::ToString()
0xc4f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc4fa  ldloc.0
0xc4fb  ldstr    aOrgretryvalue// "OrgRetryValue"
0xc500  ldloca.s 2
0xc502  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc507  brtrue.s loc_C510
0xc509  ldstr    aNotset// "NotSet"
0xc50e  br.s     loc_C51D
0xc510  ldloca.s 2
0xc512  constrained. valuetype [mscorlib]System.Nullable`1<bool>
0xc518  callvirt instance string [mscorlib]System.Object::ToString()
0xc51d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc522  ldloc.0
0xc523  ldstr    aMachineretryva// "MachineRetryValue"
0xc528  ldloca.s 3
0xc52a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc52f  brtrue.s loc_C538
0xc531  ldstr    aNotset// "NotSet"
0xc536  br.s     loc_C545
0xc538  ldloca.s 3
0xc53a  constrained. valuetype [mscorlib]System.Nullable`1<int32>
0xc540  callvirt instance string [mscorlib]System.Object::ToString()
0xc545  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc54a  ldloca.s 1
0xc54c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc551  brfalse.s loc_C592
0xc553  ldloca.s 1
0xc555  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xc55a  brfalse.s loc_C56E
0xc55c  ldloca.s 2
0xc55e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc563  brtrue.s loc_C592
0xc565  ldloca.s 3
0xc567  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc56c  brtrue.s loc_C592
0xc56e  ldloca.s 1
0xc570  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xc575  stloc.s  5
0xc577  ldloc.0
0xc578  ldstr    aIsretryenabled// "IsRetryEnabled"
0xc57d  ldloca.s 5
0xc57f  call     instance string [mscorlib]System.Boolean::ToString()
0xc584  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc589  ldloc.0
0xc58a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xc58f  ldloc.s  5
0xc591  ret
0xc592  ldloca.s 2
0xc594  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc599  brfalse.s loc_C5D1
0xc59b  ldloca.s 2
0xc59d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc5a2  brfalse.s loc_C5AD
0xc5a4  ldloca.s 3
0xc5a6  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc5ab  brtrue.s loc_C5D1
0xc5ad  ldloca.s 2
0xc5af  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xc5b4  stloc.s  6
0xc5b6  ldloc.0
0xc5b7  ldstr    aIsretryenabled// "IsRetryEnabled"
0xc5bc  ldloca.s 6
0xc5be  call     instance string [mscorlib]System.Boolean::ToString()
0xc5c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc5c8  ldloc.0
0xc5c9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xc5ce  ldloc.s  6
0xc5d0  ret
0xc5d1  ldloca.s 3
0xc5d3  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc5d8  brfalse.s loc_C601
0xc5da  ldloca.s 3
0xc5dc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xc5e1  ldc.i4.0
0xc5e2  cgt
0xc5e4  stloc.s  7
0xc5e6  ldloc.0
0xc5e7  ldstr    aIsretryenabled// "IsRetryEnabled"
0xc5ec  ldloca.s 7
0xc5ee  call     instance string [mscorlib]System.Boolean::ToString()
0xc5f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc5f8  ldloc.0
0xc5f9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xc5fe  ldloc.s  7
0xc600  ret
0xc601  ldloc.0
0xc602  ldstr    aIsretryenabled// "IsRetryEnabled"
0xc607  ldc.i4.1
0xc608  stloc.s  8
0xc60a  ldloca.s 8
0xc60c  call     instance string [mscorlib]System.Boolean::ToString()
0xc611  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xc616  ldloc.0
0xc617  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xc61c  ldc.i4.1
0xc61d  ret
```
