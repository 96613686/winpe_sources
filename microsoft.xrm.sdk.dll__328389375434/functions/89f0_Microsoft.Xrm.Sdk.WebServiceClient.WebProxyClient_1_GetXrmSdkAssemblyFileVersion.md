# Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1::GetXrmSdkAssemblyFileVersion

- ea: `0x89f0`
- end: `0x8a79`
- name: `Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1::GetXrmSdkAssemblyFileVersion`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x89f0`

## string_xrefs

- `0x8a05`: `Microsoft.Xrm.Sdk.dll`

## pseudocode

```c

```

## disassembly

```asm
0x89f0  ldarg.0
0x89f1  ldfld    string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::_xrmSdkAssemblyFileVersion
0x89f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x89fb  brfalse.s loc_8A72
0x89fd  ldc.i4.1
0x89fe  newarr   [mscorlib]System.String
0x8a03  dup
0x8a04  ldc.i4.0
0x8a05  ldstr    aMicrosoftXrmSd// "Microsoft.Xrm.Sdk.dll"
0x8a0a  stelem.ref
0x8a0b  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x8a10  callvirt instance class [mscorlib]System.Reflection.Assembly[] [mscorlib]System.AppDomain::GetAssemblies()
0x8a15  stloc.0
0x8a16  stloc.1
0x8a17  ldc.i4.0
0x8a18  stloc.2
0x8a19  br.s     loc_8A6C
0x8a1b  ldloc.1
0x8a1c  ldloc.2
0x8a1d  ldelem.ref
0x8a1e  stloc.3
0x8a1f  ldloc.0
0x8a20  stloc.s  4
0x8a22  ldc.i4.0
0x8a23  stloc.s  5
0x8a25  br.s     loc_8A60
0x8a27  ldloc.s  4
0x8a29  ldloc.s  5
0x8a2b  ldelem.ref
0x8a2c  stloc.s  6
0x8a2e  ldloc.s  6
0x8a30  callvirt instance class [mscorlib]System.Reflection.Module [mscorlib]System.Reflection.Assembly::get_ManifestModule()
0x8a35  callvirt instance string [mscorlib]System.Reflection.Module::get_Name()
0x8a3a  ldloc.3
0x8a3b  ldc.i4.5
0x8a3c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8a41  brfalse.s loc_8A5A
0x8a43  ldarg.0
0x8a44  ldloc.s  6
0x8a46  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x8a4b  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x8a50  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x8a55  stfld    string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::_xrmSdkAssemblyFileVersion
0x8a5a  ldloc.s  5
0x8a5c  ldc.i4.1
0x8a5d  add
0x8a5e  stloc.s  5
0x8a60  ldloc.s  5
0x8a62  ldloc.s  4
0x8a64  ldlen
0x8a65  conv.i4
0x8a66  blt.s    loc_8A27
0x8a68  ldloc.2
0x8a69  ldc.i4.1
0x8a6a  add
0x8a6b  stloc.2
0x8a6c  ldloc.2
0x8a6d  ldloc.1
0x8a6e  ldlen
0x8a6f  conv.i4
0x8a70  blt.s    loc_8A1B
0x8a72  ldarg.0
0x8a73  ldfld    string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::_xrmSdkAssemblyFileVersion
0x8a78  ret
```
