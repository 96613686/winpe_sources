# Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::GetImages

- ea: `0x11280`
- end: `0x1130c`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::GetImages`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x11280`

## string_xrefs

- `0x11280`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x11280  ldstr    aUpdate// "Update"
0x11285  ldarg.1
0x11286  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1128b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11290  brfalse.s loc_11305
0x11292  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x11297  stloc.0
0x11298  ldloc.0
0x11299  ldstr    aEntitlementid// "entitlementid"
0x1129e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112a3  ldloc.0
0x112a4  ldstr    aStatecode// "statecode"
0x112a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112ae  ldloc.0
0x112af  ldstr    aCaseorigincode// "caseorigincode"
0x112b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112b9  ldloc.0
0x112ba  ldstr    aStatuscode// "statuscode"
0x112bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112c4  ldloc.0
0x112c5  ldstr    aDecremententit// "decremententitlementterm"
0x112ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112cf  ldloc.0
0x112d0  ldstr    aSlainvokedid// "slainvokedid"
0x112d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112da  ldloc.0
0x112db  ldstr    aSlaid// "slaid"
0x112e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x112e5  ldc.i4.1
0x112e6  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription
0x112eb  dup
0x112ec  ldc.i4.0
0x112ed  ldstr    aTarget// "Target"
0x112f2  ldc.i4.0
0x112f3  ldstr    aPrebusinessent// "PreBusinessEntity"
0x112f8  ldloc.0
0x112f9  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x112fe  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription::.ctor(string, int32, string, string[])
0x11303  stelem.ref
0x11304  ret
0x11305  ldc.i4.0
0x11306  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription
0x1130b  ret
```
