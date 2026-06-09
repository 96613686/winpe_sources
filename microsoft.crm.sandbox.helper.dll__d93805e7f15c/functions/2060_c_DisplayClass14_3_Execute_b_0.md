# <>c__DisplayClass14_3::<Execute>b__0

- ea: `0x2060`
- end: `0x2109`
- name: `<>c__DisplayClass14_3::<Execute>b__0`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18d0`
- `0x1930`
- `0x1990`
- `0x2060`

## string_xrefs

- `0x2076`: `SandboxAppDomainHelper.IPlugin.Execute`
- `0x20ad`: `SandboxAppDomainHelper.Execute: Calling pluginInterface.Execute`

## pseudocode

```c

```

## disassembly

```asm
0x2060  ldarg.0
0x2061  ldfld    object <>c__DisplayClass14_3::traceParameters
0x2066  stsfld   object Microsoft.Crm.Sandbox.SandboxTraceContextHelper::TraceParameters
0x206b  ldarg.0
0x206c  ldfld    class Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper <>c__DisplayClass14_3::timeToStartThread
0x2071  callvirt instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::Dispose()
0x2076  ldstr    aSandboxappdoma_41// "SandboxAppDomainHelper.IPlugin.Execute"
0x207b  ldc.i4.3
0x207c  ldarg.0
0x207d  ldfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_3::CS$<>8__locals3
0x2082  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x2087  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x208c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x2091  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x2096  stloc.0
0x2097  ldarg.0
0x2098  ldfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_3::CS$<>8__locals3
0x209d  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x20a2  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x20a7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x20ac  ldc.i4.3
0x20ad  ldstr    aSandboxappdoma_42// "SandboxAppDomainHelper.Execute: Calling"...
0x20b2  ldnull
0x20b3  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x20b8  ldarg.0
0x20b9  ldfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_3::CS$<>8__locals3
0x20be  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin <>c__DisplayClass14_2::pluginInterface
0x20c3  ldarg.0
0x20c4  ldfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_3::CS$<>8__locals3
0x20c9  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x20ce  ldfld    class Microsoft.Crm.Sandbox.SandboxServiceProvider <>c__DisplayClass14_1::serviceProvider
0x20d3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin::Execute(class [mscorlib]System.IServiceProvider)
0x20d8  ldarg.0
0x20d9  ldfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass14_3::ExecuteComplete
0x20de  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x20e3  pop
0x20e4  leave.s  loc_20F0
0x20e6  ldloc.0
0x20e7  brfalse.s loc_20EF
0x20e9  ldloc.0
0x20ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20ef  endfinally
0x20f0  leave.s  loc_2108
0x20f2  stloc.1
0x20f3  ldarg.0
0x20f4  ldloc.1
0x20f5  stfld    class [mscorlib]System.Exception <>c__DisplayClass14_3::executeException
0x20fa  ldarg.0
0x20fb  ldfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass14_3::ExecuteComplete
0x2100  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x2105  pop
0x2106  leave.s  loc_2108
0x2108  ret
```
