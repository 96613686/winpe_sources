# Microsoft.Crm.Sandbox.SandboxAppDomain::GetNewHelper

- ea: `0xef0`
- end: `0xf9c`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::GetNewHelper`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1b30`

## callees

- `0xef0`
- `0x1750`
- `0x4820`

## string_xrefs

- `0xf59`: `{0}-{1}.dll`

## pseudocode

```c

```

## disassembly

```asm
0xef0  ldarg.0
0xef1  ldfld    class [mscorlib]System.AppDomain Microsoft.Crm.Sandbox.SandboxAppDomain::_restrictedAppDomain
0xef6  call     class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper Microsoft.Crm.Sandbox.SandboxAppDomain::CreateHelperInPartialTrustAppDomain(class [mscorlib]System.AppDomain sandboxAppDomain)
0xefb  stloc.0
0xefc  ldarg.0
0xefd  ldfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_crashFile
0xf02  brtrue.s loc_F4E
0xf04  ldarg.0
0xf05  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::get_WorkerProcessGuid()
0xf0a  ldnull
0xf0b  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::CrashFileName(valuetype [mscorlib]System.Guid, string)
0xf10  stfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_crashFile
0xf15  ldarg.0
0xf16  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0xf1b  ldc.i4.s 0x26
0xf1d  ldstr    aSandboxappdoma// "SandboxAppDomain.GetNewHelper: crashFil"...
0xf22  ldc.i4.1
0xf23  newarr   [mscorlib]System.Object
0xf28  dup
0xf29  ldc.i4.0
0xf2a  ldarg.0
0xf2b  ldfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_crashFile
0xf30  stelem.ref
0xf31  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf36  ldloc.0
0xf37  ldarg.1
0xf38  ldarg.0
0xf39  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0xf3e  ldarg.0
0xf3f  ldfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_crashFile
0xf44  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceProvider [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceProvider::get_Instance()
0xf49  callvirt instance void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Initialize(bool, valuetype [mscorlib]System.Guid, string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService)
0xf4e  ldarg.0
0xf4f  ldfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_pluginAssemblyBase
0xf54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf59  ldstr    a01Dll// "{0}-{1}.dll"
0xf5e  ldc.i4.2
0xf5f  newarr   [mscorlib]System.Object
0xf64  dup
0xf65  ldc.i4.0
0xf66  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf6b  stloc.2
0xf6c  ldloca.s 2
0xf6e  ldstr    aB// "B"
0xf73  call     instance string [mscorlib]System.Guid::ToString(string)
0xf78  stelem.ref
0xf79  dup
0xf7a  ldc.i4.1
0xf7b  ldc.i4.0
0xf7c  box      [mscorlib]System.Int32
0xf81  stelem.ref
0xf82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf87  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf8c  stloc.1
0xf8d  ldarg.0
0xf8e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper> Microsoft.Crm.Sandbox.SandboxAppDomain::_helperLookUp
0xf93  ldloc.1
0xf94  ldloc.0
0xf95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper>::Add(var<u1>, !!T0)
0xf9a  ldloc.0
0xf9b  ret
```
