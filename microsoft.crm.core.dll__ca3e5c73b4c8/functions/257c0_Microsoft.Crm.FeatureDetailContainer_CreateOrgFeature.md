# Microsoft.Crm.FeatureDetailContainer::CreateOrgFeature

- ea: `0x257c0`
- end: `0x258c8`
- name: `Microsoft.Crm.FeatureDetailContainer::CreateOrgFeature`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x25460`

## callees

- `0x1b340`
- `0x24cc0`
- `0x24d70`
- `0x24d90`
- `0x24db0`
- `0x24dd0`
- `0x24e10`
- `0x257c0`
- `0x2bc70`

## string_xrefs

- `0x257ef`: `Atleast one MinimumOrgDBVersion entry is required for Organization Features. FeatureName {0}`
- `0x25856`: `MinimumOrgDBVersion is required for Organization Features, FeatureName {0}`
- `0x25877`: `When adding the FeatureVersionDetail, add them in the increasing order of the releases. FeatureName {0} `

## pseudocode

```c

```

## disassembly

```asm
0x257c0  newobj   instance void Microsoft.Crm.FeatureDetail::.ctor()
0x257c5  dup
0x257c6  ldarg.1
0x257c7  callvirt instance void Microsoft.Crm.FeatureDetail::set_Name(string value)
0x257cc  dup
0x257cd  ldc.i4.0
0x257ce  callvirt instance void Microsoft.Crm.FeatureDetail::set_FeatureLocation(valuetype Microsoft.Crm.FeatureLocation value)
0x257d3  dup
0x257d4  ldarg.2
0x257d5  callvirt instance void Microsoft.Crm.FeatureDetail::set_FeatureType(valuetype Microsoft.Crm.FeatureType value)
0x257da  dup
0x257db  ldarg.3
0x257dc  callvirt instance void Microsoft.Crm.FeatureDetail::set_ConfigSku(valuetype Microsoft.Crm.SharedDatabase.ConfigSku value)
0x257e1  stloc.0
0x257e2  ldarg.s  4
0x257e4  brfalse.s loc_257EF
0x257e6  ldarg.s  4
0x257e8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.FeatureVersionDetail>::get_Count()
0x257ed  brtrue.s loc_25800
0x257ef  ldstr    aAtleastOneMini// "Atleast one MinimumOrgDBVersion entry i"...
0x257f4  ldarg.1
0x257f5  call     string [mscorlib]System.String::Format(string, object)
0x257fa  newobj   instance void Microsoft.Crm.CrmArgumentException::.ctor(string message)
0x257ff  throw
0x25800  ldarg.s  4
0x25802  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.FeatureVersionDetail>::get_Count()
0x25807  ldc.i4.1
0x25808  ble      loc_258AE
0x2580d  ldarg.s  4
0x2580f  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.FeatureVersionDetail, class [mscorlib]System.Version> <>c::<>9__5_0
0x25814  dup
0x25815  brtrue.s loc_2582E
0x25817  pop
0x25818  ldsfld   class <>c <>c::<>9
0x2581d  ldftn    instance class [mscorlib]System.Version <>c::<CreateOrgFeature>b__5_0(class Microsoft.Crm.FeatureVersionDetail _)
0x25823  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.FeatureVersionDetail, class [mscorlib]System.Version>::.ctor(object, native int)
0x25828  dup
0x25829  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.FeatureVersionDetail, class [mscorlib]System.Version> <>c::<>9__5_0
0x2582e  call     T0x2B00006B
0x25833  call     T0x2B00006C
0x25838  stloc.1
0x25839  ldloc.1
0x2583a  ldc.i4.0
0x2583b  ldelem.ref
0x2583c  callvirt instance class [mscorlib]System.Version Microsoft.Crm.FeatureVersionDetail::get_MinimumOrgDBVersion()
0x25841  stloc.2
0x25842  ldc.i4.1
0x25843  stloc.3
0x25844  br.s     loc_25895
0x25846  ldloc.1
0x25847  ldloc.3
0x25848  ldelem.ref
0x25849  callvirt instance class [mscorlib]System.Version Microsoft.Crm.FeatureVersionDetail::get_MinimumOrgDBVersion()
0x2584e  ldnull
0x2584f  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x25854  brfalse.s loc_25867
0x25856  ldstr    aMinimumorgdbve_0// "MinimumOrgDBVersion is required for Org"...
0x2585b  ldarg.1
0x2585c  call     string [mscorlib]System.String::Format(string, object)
0x25861  newobj   instance void Microsoft.Crm.CrmArgumentException::.ctor(string message)
0x25866  throw
0x25867  ldloc.1
0x25868  ldloc.3
0x25869  ldelem.ref
0x2586a  callvirt instance class [mscorlib]System.Version Microsoft.Crm.FeatureVersionDetail::get_MinimumOrgDBVersion()
0x2586f  ldloc.2
0x25870  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x25875  brfalse.s loc_25888
0x25877  ldstr    aWhenAddingTheF// "When adding the FeatureVersionDetail, a"...
0x2587c  ldarg.1
0x2587d  call     string [mscorlib]System.String::Format(string, object)
0x25882  newobj   instance void Microsoft.Crm.CrmArgumentException::.ctor(string message)
0x25887  throw
0x25888  ldloc.1
0x25889  ldloc.3
0x2588a  ldelem.ref
0x2588b  callvirt instance class [mscorlib]System.Version Microsoft.Crm.FeatureVersionDetail::get_MinimumOrgDBVersion()
0x25890  stloc.2
0x25891  ldloc.3
0x25892  ldc.i4.1
0x25893  add
0x25894  stloc.3
0x25895  ldloc.3
0x25896  ldloc.1
0x25897  ldlen
0x25898  conv.i4
0x25899  blt.s    loc_25846
0x2589b  ldloc.0
0x2589c  ldloc.1
0x2589d  call     T0x2B00006D
0x258a2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.IFeatureVersionDetail>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x258a7  callvirt instance void Microsoft.Crm.FeatureDetail::set_Versions(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.IFeatureVersionDetail> value)
0x258ac  br.s     loc_258C6
0x258ae  ldloc.0
0x258af  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.IFeatureVersionDetail>::.ctor()
0x258b4  dup
0x258b5  ldarg.s  4
0x258b7  call     T0x2B00006E
0x258bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.IFeatureVersionDetail>::Add(var<u1>)
0x258c1  callvirt instance void Microsoft.Crm.FeatureDetail::set_Versions(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.IFeatureVersionDetail> value)
0x258c6  ldloc.0
0x258c7  ret
```
