# Microsoft.Crm.CrmTrace::GetFileVersion

- ea: `0x20220`
- end: `0x202e2`
- name: `Microsoft.Crm.CrmTrace::GetFileVersion`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1f9d0`

## callees

- `0x20220`
- `0x3d870`

## string_xrefs

- `0x20240`: `Microsoft.Crm.dll`
- `0x20248`: `Microsoft.Crm.DiscoveryService.dll`
- `0x20250`: `Microsoft.Crm.Site.Core.dll`

## pseudocode

```c

```

## disassembly

```asm
0x20220  ldsfld   class [System]System.Diagnostics.FileVersionInfo Microsoft.Crm.CrmTrace::_tracedllVersion
0x20225  brtrue   loc_202CE
0x2022a  ldsfld   bool Microsoft.Crm.CrmTrace::_checkNotComplete
0x2022f  brtrue.s loc_20237
0x20231  call     string Microsoft.Crm.ProductVersion::get_FileVersion()
0x20236  ret
0x20237  nop
0x20238  ldc.i4.3
0x20239  newarr   [mscorlib]System.String
0x2023e  dup
0x2023f  ldc.i4.0
0x20240  ldstr    aMicrosoftCrmDl// "Microsoft.Crm.dll"
0x20245  stelem.ref
0x20246  dup
0x20247  ldc.i4.1
0x20248  ldstr    aMicrosoftCrmDi// "Microsoft.Crm.DiscoveryService.dll"
0x2024d  stelem.ref
0x2024e  dup
0x2024f  ldc.i4.2
0x20250  ldstr    aMicrosoftCrmSi// "Microsoft.Crm.Site.Core.dll"
0x20255  stelem.ref
0x20256  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x2025b  callvirt instance class [mscorlib]System.Reflection.Assembly[] [mscorlib]System.AppDomain::GetAssemblies()
0x20260  stloc.0
0x20261  stloc.1
0x20262  ldc.i4.0
0x20263  stloc.2
0x20264  br.s     loc_202BF
0x20266  ldloc.1
0x20267  ldloc.2
0x20268  ldelem.ref
0x20269  stloc.3
0x2026a  ldloc.0
0x2026b  stloc.s  4
0x2026d  ldc.i4.0
0x2026e  stloc.s  5
0x20270  br.s     loc_202B3
0x20272  ldloc.s  4
0x20274  ldloc.s  5
0x20276  ldelem.ref
0x20277  stloc.s  6
0x20279  ldloc.s  6
0x2027b  callvirt instance class [mscorlib]System.Reflection.Module [mscorlib]System.Reflection.Assembly::get_ManifestModule()
0x20280  callvirt instance string [mscorlib]System.Reflection.Module::get_Name()
0x20285  ldloc.3
0x20286  ldc.i4.5
0x20287  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2028c  brfalse.s loc_202AD
0x2028e  ldloc.s  6
0x20290  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x20295  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x2029a  stsfld   class [System]System.Diagnostics.FileVersionInfo Microsoft.Crm.CrmTrace::_tracedllVersion
0x2029f  ldsfld   class [System]System.Diagnostics.FileVersionInfo Microsoft.Crm.CrmTrace::_tracedllVersion
0x202a4  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x202a9  stloc.s  7
0x202ab  leave.s  loc_202DF
0x202ad  ldloc.s  5
0x202af  ldc.i4.1
0x202b0  add
0x202b1  stloc.s  5
0x202b3  ldloc.s  5
0x202b5  ldloc.s  4
0x202b7  ldlen
0x202b8  conv.i4
0x202b9  blt.s    loc_20272
0x202bb  ldloc.2
0x202bc  ldc.i4.1
0x202bd  add
0x202be  stloc.2
0x202bf  ldloc.2
0x202c0  ldloc.1
0x202c1  ldlen
0x202c2  conv.i4
0x202c3  blt.s    loc_20266
0x202c5  leave.s  loc_202D9
0x202c7  ldc.i4.0
0x202c8  stsfld   bool Microsoft.Crm.CrmTrace::_checkNotComplete
0x202cd  endfinally
0x202ce  ldsfld   class [System]System.Diagnostics.FileVersionInfo Microsoft.Crm.CrmTrace::_tracedllVersion
0x202d3  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x202d8  ret
0x202d9  call     string Microsoft.Crm.ProductVersion::get_FileVersion()
0x202de  ret
0x202df  ldloc.s  7
0x202e1  ret
```
