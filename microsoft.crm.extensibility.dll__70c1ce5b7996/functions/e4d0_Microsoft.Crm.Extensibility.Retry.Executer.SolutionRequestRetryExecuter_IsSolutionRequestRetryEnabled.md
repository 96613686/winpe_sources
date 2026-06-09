# Microsoft.Crm.Extensibility.Retry.Executer.SolutionRequestRetryExecuter::IsSolutionRequestRetryEnabled

- ea: `0xe4d0`
- end: `0xe65a`
- name: `Microsoft.Crm.Extensibility.Retry.Executer.SolutionRequestRetryExecuter::IsSolutionRequestRetryEnabled`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xe4d0`

## string_xrefs

- `0xe506`: `SolutionImportRetryAttempts`

## pseudocode

```c

```

## disassembly

```asm
0xe4d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xe4d5  stloc.0
0xe4d6  ldstr    aUsesolutionimp// "UseSolutionImportRetry"
0xe4db  ldloca.s 4
0xe4dd  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0xe4e3  ldloc.s  4
0xe4e5  call     T0x2B00005E
0xe4ea  stloc.1
0xe4eb  ldarg.0
0xe4ec  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.Retry.Executer.OrganizationRequestBaseRetryExecuter::OrganizationId
0xe4f1  ldstr    aUsesolutionimp// "UseSolutionImportRetry"
0xe4f6  ldloca.s 4
0xe4f8  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0xe4fe  ldloc.s  4
0xe500  call     T0x2B00005F
0xe505  stloc.2
0xe506  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xe50b  ldnull
0xe50c  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xe511  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xe516  stloc.3
0xe517  ldloc.0
0xe518  ldstr    aSgretryvalue// "SGRetryValue"
0xe51d  ldloca.s 1
0xe51f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xe524  brtrue.s loc_E52D
0xe526  ldstr    aNotset// "NotSet"
0xe52b  br.s     loc_E53A
0xe52d  ldloca.s 1
0xe52f  constrained. valuetype [mscorlib]System.Nullable`1<bool>
0xe535  callvirt instance string [mscorlib]System.Object::ToString()
0xe53a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe53f  ldloc.0
0xe540  ldstr    aOrgretryvalue// "OrgRetryValue"
0xe545  ldloca.s 2
0xe547  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xe54c  brtrue.s loc_E555
0xe54e  ldstr    aNotset// "NotSet"
0xe553  br.s     loc_E562
0xe555  ldloca.s 2
0xe557  constrained. valuetype [mscorlib]System.Nullable`1<bool>
0xe55d  callvirt instance string [mscorlib]System.Object::ToString()
0xe562  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe567  ldloc.0
0xe568  ldstr    aMachineretryva// "MachineRetryValue"
0xe56d  ldloca.s 3
0xe56f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xe574  brtrue.s loc_E57D
0xe576  ldstr    aNotset// "NotSet"
0xe57b  br.s     loc_E58A
0xe57d  ldloca.s 3
0xe57f  constrained. valuetype [mscorlib]System.Nullable`1<int32>
0xe585  callvirt instance string [mscorlib]System.Object::ToString()
0xe58a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe58f  ldloca.s 1
0xe591  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xe596  brfalse.s loc_E5D7
0xe598  ldloca.s 1
0xe59a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xe59f  brfalse.s loc_E5B3
0xe5a1  ldloca.s 2
0xe5a3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xe5a8  brtrue.s loc_E5D7
0xe5aa  ldloca.s 3
0xe5ac  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xe5b1  brtrue.s loc_E5D7
0xe5b3  ldloca.s 1
0xe5b5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xe5ba  stloc.s  5
0xe5bc  ldloc.0
0xe5bd  ldstr    aIsretryenabled// "IsRetryEnabled"
0xe5c2  ldloca.s 5
0xe5c4  call     instance string [mscorlib]System.Boolean::ToString()
0xe5c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe5ce  ldloc.0
0xe5cf  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xe5d4  ldloc.s  5
0xe5d6  ret
0xe5d7  ldloca.s 2
0xe5d9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xe5de  brfalse.s loc_E60D
0xe5e0  ldloca.s 3
0xe5e2  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xe5e7  brtrue.s loc_E60D
0xe5e9  ldloca.s 2
0xe5eb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xe5f0  stloc.s  6
0xe5f2  ldloc.0
0xe5f3  ldstr    aIsretryenabled// "IsRetryEnabled"
0xe5f8  ldloca.s 6
0xe5fa  call     instance string [mscorlib]System.Boolean::ToString()
0xe5ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe604  ldloc.0
0xe605  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xe60a  ldloc.s  6
0xe60c  ret
0xe60d  ldloca.s 3
0xe60f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xe614  brfalse.s loc_E63D
0xe616  ldloca.s 3
0xe618  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xe61d  ldc.i4.0
0xe61e  cgt
0xe620  stloc.s  7
0xe622  ldloc.0
0xe623  ldstr    aIsretryenabled// "IsRetryEnabled"
0xe628  ldloca.s 7
0xe62a  call     instance string [mscorlib]System.Boolean::ToString()
0xe62f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe634  ldloc.0
0xe635  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xe63a  ldloc.s  7
0xe63c  ret
0xe63d  ldloc.0
0xe63e  ldstr    aIsretryenabled// "IsRetryEnabled"
0xe643  ldc.i4.1
0xe644  stloc.s  8
0xe646  ldloca.s 8
0xe648  call     instance string [mscorlib]System.Boolean::ToString()
0xe64d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe652  ldloc.0
0xe653  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xe658  ldc.i4.1
0xe659  ret
```
