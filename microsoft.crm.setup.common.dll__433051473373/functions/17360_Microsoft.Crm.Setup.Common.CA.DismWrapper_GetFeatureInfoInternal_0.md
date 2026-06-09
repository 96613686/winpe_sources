# Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal_0

- ea: `0x17360`
- end: `0x17432`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal_0`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x172e0`

## callees

- `0x17360`
- `0x17440`
- `0x17580`
- `0x176c0`

## string_xrefs

- `0x17394`: ` /featurename:"{0}"`

## pseudocode

```c

```

## disassembly

```asm
0x17360  ldarg.1
0x17361  brtrue.s loc_1736E
0x17363  ldstr    aFeatures// "features"
0x17368  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1736d  throw
0x1736e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x17373  stloc.0
0x17374  ldloc.0
0x17375  ldstr    aOnlineEnglishG_1// "/online /english /get-featureinfo"
0x1737a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1737f  pop
0x17380  ldarg.1
0x17381  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x17386  stloc.s  5
0x17388  br.s     loc_173A1
0x1738a  ldloc.s  5
0x1738c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x17391  stloc.s  6
0x17393  ldloc.0
0x17394  ldstr    aFeaturename0_0// " /featurename:\"{0}\""
0x17399  ldloc.s  6
0x1739b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x173a0  pop
0x173a1  ldloc.s  5
0x173a3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x173a8  brtrue.s loc_1738A
0x173aa  leave.s  loc_173B8
0x173ac  ldloc.s  5
0x173ae  brfalse.s loc_173B7
0x173b0  ldloc.s  5
0x173b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x173b7  endfinally
0x173b8  ldstr    asc_18D5A// ""
0x173bd  stloc.1
0x173be  ldarg.0
0x173bf  call     instance string Microsoft.Crm.Setup.Common.CA.DismWrapper::get_GetExePath()
0x173c4  ldarg.0
0x173c5  ldfld    string Microsoft.Crm.Setup.Common.CA.DismWrapper::_fileName
0x173ca  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x173cf  ldloc.0
0x173d0  callvirt instance string [mscorlib]System.Object::ToString()
0x173d5  ldloca.s 1
0x173d7  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RunProcess(string, string, string&)
0x173dc  stloc.2
0x173dd  ldarg.0
0x173de  ldloc.1
0x173df  ldloc.2
0x173e0  call     instance valuetype Microsoft.Crm.Setup.Common.CA.DismCode Microsoft.Crm.Setup.Common.CA.DismWrapper::DismResults(string output, int32 exitCode)
0x173e5  pop
0x173e6  ldc.i4.1
0x173e7  newarr   [mscorlib]System.String
0x173ec  dup
0x173ed  ldc.i4.0
0x173ee  ldstr    aFeatureInforma// "Feature Information:"
0x173f3  stelem.ref
0x173f4  stloc.3
0x173f5  ldloc.1
0x173f6  ldloc.3
0x173f7  ldc.i4.1
0x173f8  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x173fd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.CA.IFeatureInfo>::.ctor()
0x17402  stloc.s  4
0x17404  stloc.s  7
0x17406  ldc.i4.0
0x17407  stloc.s  8
0x17409  br.s     loc_17427
0x1740b  ldloc.s  7
0x1740d  ldloc.s  8
0x1740f  ldelem.ref
0x17410  stloc.s  9
0x17412  ldloc.s  4
0x17414  ldarg.0
0x17415  ldloc.s  9
0x17417  call     instance class Microsoft.Crm.Setup.Common.CA.IFeatureInfo Microsoft.Crm.Setup.Common.CA.DismWrapper::MapOutputToFeatureDetail(string data)
0x1741c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.CA.IFeatureInfo>::Add(var<u1>)
0x17421  ldloc.s  8
0x17423  ldc.i4.1
0x17424  add
0x17425  stloc.s  8
0x17427  ldloc.s  8
0x17429  ldloc.s  7
0x1742b  ldlen
0x1742c  conv.i4
0x1742d  blt.s    loc_1740B
0x1742f  ldloc.s  4
0x17431  ret
```
