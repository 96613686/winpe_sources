# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::GetXrmSdkAssemblyFileVersion

- ea: `0x1a4f0`
- end: `0x1a576`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::GetXrmSdkAssemblyFileVersion`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x198c0`
- `0x1a070`

## callees

- `0x1a4f0`

## string_xrefs

- `0x1a504`: `Microsoft.Xrm.Sdk.dll`

## pseudocode

```c

```

## disassembly

```asm
0x1a4f0  ldsfld   string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::_xrmSdkAssemblyFileVersion
0x1a4f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a4fa  brfalse.s loc_1A570
0x1a4fc  ldc.i4.1
0x1a4fd  newarr   [mscorlib]System.String
0x1a502  dup
0x1a503  ldc.i4.0
0x1a504  ldstr    aMicrosoftXrmSd// "Microsoft.Xrm.Sdk.dll"
0x1a509  stelem.ref
0x1a50a  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1a50f  callvirt instance class [mscorlib]System.Reflection.Assembly[] [mscorlib]System.AppDomain::GetAssemblies()
0x1a514  stloc.0
0x1a515  stloc.1
0x1a516  ldc.i4.0
0x1a517  stloc.2
0x1a518  br.s     loc_1A56A
0x1a51a  ldloc.1
0x1a51b  ldloc.2
0x1a51c  ldelem.ref
0x1a51d  stloc.3
0x1a51e  ldloc.0
0x1a51f  stloc.s  4
0x1a521  ldc.i4.0
0x1a522  stloc.s  5
0x1a524  br.s     loc_1A55E
0x1a526  ldloc.s  4
0x1a528  ldloc.s  5
0x1a52a  ldelem.ref
0x1a52b  stloc.s  6
0x1a52d  ldloc.s  6
0x1a52f  callvirt instance class [mscorlib]System.Reflection.Module [mscorlib]System.Reflection.Assembly::get_ManifestModule()
0x1a534  callvirt instance string [mscorlib]System.Reflection.Module::get_Name()
0x1a539  ldloc.3
0x1a53a  ldc.i4.5
0x1a53b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1a540  brfalse.s loc_1A558
0x1a542  ldloc.s  6
0x1a544  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x1a549  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x1a54e  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x1a553  stsfld   string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::_xrmSdkAssemblyFileVersion
0x1a558  ldloc.s  5
0x1a55a  ldc.i4.1
0x1a55b  add
0x1a55c  stloc.s  5
0x1a55e  ldloc.s  5
0x1a560  ldloc.s  4
0x1a562  ldlen
0x1a563  conv.i4
0x1a564  blt.s    loc_1A526
0x1a566  ldloc.2
0x1a567  ldc.i4.1
0x1a568  add
0x1a569  stloc.2
0x1a56a  ldloc.2
0x1a56b  ldloc.1
0x1a56c  ldlen
0x1a56d  conv.i4
0x1a56e  blt.s    loc_1A51A
0x1a570  ldsfld   string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::_xrmSdkAssemblyFileVersion
0x1a575  ret
```
