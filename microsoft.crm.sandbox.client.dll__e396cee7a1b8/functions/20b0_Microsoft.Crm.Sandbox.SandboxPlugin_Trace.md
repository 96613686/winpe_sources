# Microsoft.Crm.Sandbox.SandboxPlugin::Trace

- ea: `0x20b0`
- end: `0x212e`
- name: `Microsoft.Crm.Sandbox.SandboxPlugin::Trace`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x20b0`

## string_xrefs

- `0x20b6`: `PluginTrace`
- `0x210f`: `PluginTrace`
- `0x20d9`: `SandboxPlugin.Trace: copying PluginTrace to tracing service: {0}`
- `0x211d`: `SandboxPlugin.Trace: no PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.1
0x20b1  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x20b6  ldstr    aPlugintrace// "PluginTrace"
0x20bb  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x20c0  isinst   [mscorlib]System.String
0x20c5  stloc.0
0x20c6  ldloc.0
0x20c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20cc  brtrue.s loc_211A
0x20ce  ldarg.0
0x20cf  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Sandbox.SandboxPlugin::tracingService
0x20d4  brfalse.s loc_211A
0x20d6  ldarg.2
0x20d7  ldc.i4.s 0x21
0x20d9  ldstr    aSandboxpluginT// "SandboxPlugin.Trace: copying PluginTrac"...
0x20de  ldc.i4.1
0x20df  newarr   [mscorlib]System.Object
0x20e4  dup
0x20e5  ldc.i4.0
0x20e6  ldloc.0
0x20e7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20ec  box      [mscorlib]System.Int32
0x20f1  stelem.ref
0x20f2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20f7  ldarg.0
0x20f8  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Sandbox.SandboxPlugin::tracingService
0x20fd  ldloc.0
0x20fe  ldc.i4.0
0x20ff  newarr   [mscorlib]System.Object
0x2104  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0x2109  ldarg.1
0x210a  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x210f  ldstr    aPlugintrace// "PluginTrace"
0x2114  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x2119  ret
0x211a  ldarg.2
0x211b  ldc.i4.s 0x21
0x211d  ldstr    aSandboxpluginT_0// "SandboxPlugin.Trace: no PluginTrace"
0x2122  ldc.i4.0
0x2123  newarr   [mscorlib]System.Object
0x2128  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x212d  ret
```
