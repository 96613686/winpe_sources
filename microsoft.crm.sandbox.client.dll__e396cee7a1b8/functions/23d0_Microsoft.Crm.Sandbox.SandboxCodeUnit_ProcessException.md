# Microsoft.Crm.Sandbox.SandboxCodeUnit::ProcessException

- ea: `0x23d0`
- end: `0x2af3`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::ProcessException`
- size: `1827`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8dc0`

## callees

- `0x480`
- `0x520`
- `0x550`
- `0xc90`
- `0x2390`
- `0x23d0`
- `0x2b00`
- `0x2fe0`
- `0x2ff0`
- `0x35c0`
- `0x37c0`

## string_xrefs

- `0x262b`: `PluginTrace`
- `0x263e`: `PluginTrace`
- `0x2658`: `PluginTrace`
- `0x2441`: `SandboxPlugin.Execute: Client:{0}, OriginalException: Type: {1} ErrorCode: {2}`
- `0x2483`: `SandboxPlugin.Execute: Client:{0}, OriginalException: {1}`
- `0x26b0`: `SandboxPlugin.Execute: UNEXPECTED: exception was not converted for client:`
- `0x27bc`: `SandboxPlugin.Execute: CrmException: {0}; {1}; {2}`
- `0x2921`: `SandboxPlugin.Execute: CrmException: {0}; {1}; {2}`
- `0x28e0`: `SandboxPlugin.Execute: Not OrganizationServiceFault - discard client: {0}`
- `0x2974`: `SandboxCodeunit.Execute: Attempt {0} of {1}. Retrying. Error: {2}.`
- `0x29ca`: `SandboxPlugin.Execute: Assembly cache retry required`
- `0x29de`: `SandboxPlugin.Execute: i != 0, unexpected assembly cache retry request`
- `0x2a14`: `SandboxPlugin.Execute: The assemblyContents is null or empty, failed to load plugin assembly on retry.`
- `0x2a53`: `SandboxPlugin.Execute: Got assembly contents OK`
- `0x2a8b`: `SandboxPlugin.Execute: Sandbox Host {0} is shutting down on attempt i={1}. Max retry count: i={2}`

## pseudocode

```c

```

## disassembly

```asm
0x23d0  ldarg.2
0x23d1  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x23d6  stloc.0
0x23d7  ldarg.2
0x23d8  brtrue.s loc_23E1
0x23da  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23df  br.s     loc_23E7
0x23e1  ldarg.2
0x23e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x23e7  stloc.1
0x23e8  ldarg.2
0x23e9  brfalse.s loc_23FC
0x23eb  ldarg.2
0x23ec  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x23f1  stloc.s  0x13
0x23f3  ldloca.s 0x13
0x23f5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x23fa  brtrue.s loc_2403
0x23fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2401  br.s     loc_2412
0x2403  ldarg.2
0x2404  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x2409  stloc.s  0x13
0x240b  ldloca.s 0x13
0x240d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2412  stloc.2
0x2413  ldarg.2
0x2414  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x2419  stloc.3
0x241a  ldarg.2
0x241b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2420  stloc.s  4
0x2422  ldarg.1
0x2423  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x2428  stloc.s  5
0x242a  ldsfld   string [mscorlib]System.String::Empty
0x242f  stloc.s  6
0x2431  ldnull
0x2432  stloc.s  7
0x2434  ldloc.s  5
0x2436  brfalse.s loc_2483
0x2438  ldloc.s  5
0x243a  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ShouldSkipFaultExceptionDetails(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>)
0x243f  brfalse.s loc_2483
0x2441  ldstr    aSandboxpluginE// "SandboxPlugin.Execute: Client:{0}, Orig"...
0x2446  stloc.s  6
0x2448  ldc.i4.3
0x2449  newarr   [mscorlib]System.Object
0x244e  dup
0x244f  ldc.i4.0
0x2450  ldarg.3
0x2451  brtrue.s loc_245A
0x2453  ldstr    aUnknown// "Unknown"
0x2458  br.s     loc_2460
0x245a  ldarg.3
0x245b  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::get_ClientId()
0x2460  stelem.ref
0x2461  dup
0x2462  ldc.i4.1
0x2463  ldloc.s  5
0x2465  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x246a  stelem.ref
0x246b  dup
0x246c  ldc.i4.2
0x246d  ldloc.s  5
0x246f  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x2474  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x2479  box      [mscorlib]System.Int32
0x247e  stelem.ref
0x247f  stloc.s  7
0x2481  br.s     loc_24A9
0x2483  ldstr    aSandboxpluginE_0// "SandboxPlugin.Execute: Client:{0}, Orig"...
0x2488  stloc.s  6
0x248a  ldc.i4.2
0x248b  newarr   [mscorlib]System.Object
0x2490  dup
0x2491  ldc.i4.0
0x2492  ldarg.3
0x2493  brtrue.s loc_249C
0x2495  ldstr    aUnknown// "Unknown"
0x249a  br.s     loc_24A2
0x249c  ldarg.3
0x249d  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::get_ClientId()
0x24a2  stelem.ref
0x24a3  dup
0x24a4  ldc.i4.1
0x24a5  ldarg.1
0x24a6  stelem.ref
0x24a7  stloc.s  7
0x24a9  ldarg.1
0x24aa  ldloc.s  4
0x24ac  ldc.i4.s 0x21
0x24ae  ldloc.s  6
0x24b0  ldloc.s  7
0x24b2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24b7  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x24bc  brfalse.s loc_24C9
0x24be  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x24c3  ldc.i4.0
0x24c4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool)
0x24c9  ldarg.s  9
0x24cb  ldnull
0x24cc  stind.ref
0x24cd  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.Sandbox.SandboxCodeUnit::_exceptionConverter
0x24d2  ldarg.1
0x24d3  ldarg.s  9
0x24d5  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToCrmException(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException&)
0x24da  stloc.s  8
0x24dc  leave.s  loc_250B
0x24de  stloc.s  0x14
0x24e0  ldloc.s  0x14
0x24e2  ldloc.s  4
0x24e4  ldc.i4.s 0x21
0x24e6  ldstr    aSandboxcodeuni// "SandboxCodeunit.Execute.Exception: UNEX"...
0x24eb  ldc.i4.2
0x24ec  newarr   [mscorlib]System.Object
0x24f1  dup
0x24f2  ldc.i4.0
0x24f3  ldarg.1
0x24f4  callvirt instance string [mscorlib]System.Object::ToString()
0x24f9  stelem.ref
0x24fa  dup
0x24fb  ldc.i4.1
0x24fc  ldloc.s  0x14
0x24fe  callvirt instance string [mscorlib]System.Object::ToString()
0x2503  stelem.ref
0x2504  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2509  rethrow
0x250b  ldarg.s  4
0x250d  brtrue.s loc_251A
0x250f  ldc.r8   0.0
0x2518  br.s     loc_252F
0x251a  ldarg.s  4
0x251c  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2521  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ExecutionTime()
0x2526  stloc.s  0x15
0x2528  ldloca.s 0x15
0x252a  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x252f  stloc.s  9
0x2531  ldloc.s  8
0x2533  brtrue.s loc_2538
0x2535  ldarg.1
0x2536  br.s     loc_253B
0x2538  ldarg.s  9
0x253a  ldind.ref
0x253b  stloc.s  0xA
0x253d  ldarg.1
0x253e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2543  stloc.s  0xB
0x2545  ldloc.s  4
0x2547  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTraceLogSettingType Microsoft.Crm.Sandbox.SandboxPluginHelper::GetPluginTraceLogSetting(valuetype [mscorlib]System.Guid organizationId)
0x254c  ldc.i4.0
0x254d  cgt.un
0x254f  stloc.s  0xC
0x2551  ldsfld   string [mscorlib]System.String::Empty
0x2556  stloc.s  0xD
0x2558  ldsfld   string [mscorlib]System.String::Empty
0x255d  stloc.s  0xE
0x255f  ldloc.s  8
0x2561  brfalse.s loc_25B4
0x2563  ldloc.s  5
0x2565  brfalse.s loc_25B4
0x2567  ldloc.s  5
0x2569  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x256e  brfalse.s loc_25B4
0x2570  ldloc.s  5
0x2572  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x2577  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x257c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2581  brtrue.s loc_25B4
0x2583  ldloc.s  5
0x2585  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x258a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x258f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2594  brtrue.s loc_25B4
0x2596  ldloc.s  5
0x2598  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x259d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x25a2  stloc.s  0xE
0x25a4  ldloc.s  5
0x25a6  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x25ab  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x25b0  stloc.s  0xD
0x25b2  br.s     loc_25CF
0x25b4  ldarg.1
0x25b5  callvirt instance string [mscorlib]System.Object::ToString()
0x25ba  stloc.s  0xE
0x25bc  ldc.i4.s 9
0x25be  stloc.s  0x16
0x25c0  ldloca.s 0x16
0x25c2  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x25c8  callvirt instance string [mscorlib]System.Object::ToString()
0x25cd  stloc.s  0xD
0x25cf  ldloc.s  8
0x25d1  brfalse.s loc_25EA
0x25d3  ldarg.0
0x25d4  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_attemptNumber
0x25d9  brtrue.s loc_25EA
0x25db  ldarg.s  9
0x25dd  ldind.ref
0x25de  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x25e3  ldc.i4   0x80044191
0x25e8  beq.s    loc_260C
0x25ea  ldarg.0
0x25eb  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_attemptNumber
0x25f0  ldarg.0
0x25f1  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_maxAttempts
0x25f6  ldc.i4.1
0x25f7  sub
0x25f8  bge.s    loc_2609
0x25fa  ldarg.s  5
0x25fc  brtrue.s loc_2606
0x25fe  ldarg.1
0x25ff  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsSafeToRetry(class [mscorlib]System.Exception)
0x2604  br.s     loc_260D
0x2606  ldc.i4.1
0x2607  br.s     loc_260D
0x2609  ldc.i4.0
0x260a  br.s     loc_260D
0x260c  ldc.i4.1
0x260d  stloc.s  0xF
0x260f  ldloc.s  0xC
0x2611  brfalse.s loc_2682
0x2613  ldloc.s  0xF
0x2615  brtrue.s loc_2682
0x2617  ldloc.s  0xA
0x2619  brfalse.s loc_264A
0x261b  ldloc.s  0xA
0x261d  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x2622  brfalse.s loc_264A
0x2624  ldloc.s  0xA
0x2626  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x262b  ldstr    aPlugintrace// "PluginTrace"
0x2630  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2635  brfalse.s loc_264A
0x2637  ldloc.s  0xA
0x2639  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x263e  ldstr    aPlugintrace// "PluginTrace"
0x2643  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2648  brtrue.s loc_2651
0x264a  ldsfld   string [mscorlib]System.String::Empty
0x264f  br.s     loc_2667
0x2651  ldloc.s  0xA
0x2653  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x2658  ldstr    aPlugintrace// "PluginTrace"
0x265d  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2662  callvirt instance string [mscorlib]System.Object::ToString()
0x2667  stloc.s  0x17
0x2669  ldarg.0
0x266a  ldarg.2
0x266b  ldarg.s  6
0x266d  ldloc.s  0x17
0x266f  ldarg.0
0x2670  ldloc.s  0xB
0x2672  ldarg.3
0x2673  callvirt instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x2678  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::RemoveSensitiveInformationFromExceptionMessage(string exceptionMessage, string textToRemove)
0x267d  call     instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::CreatePluginTraceLogRecord(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, valuetype [mscorlib]System.DateTime performanceExecutionStartTime, string traceText, string exceptionDetails)
0x2682  ldarg.0
0x2683  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_attemptNumber
0x2688  ldarg.0
0x2689  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_maxAttempts
0x268e  ldc.i4.1
0x268f  sub
0x2690  bge.s    loc_26A1
0x2692  ldarg.s  5
0x2694  brtrue.s loc_269E
0x2696  ldarg.1
0x2697  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsSafeToRetry(class [mscorlib]System.Exception)
0x269c  br.s     loc_26A2
0x269e  ldc.i4.1
0x269f  br.s     loc_26A2
0x26a1  ldc.i4.0
0x26a2  stloc.s  0x11
0x26a4  ldloc.s  8
0x26a6  brtrue   loc_2794
0x26ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26b0  ldstr    aSandboxpluginE_1// "SandboxPlugin.Execute: UNEXPECTED: exce"...
0x26b5  ldarg.3
0x26b6  call     string [mscorlib]System.String::Concat(object, object)
0x26bb  brtrue.s loc_26C4
0x26bd  ldstr    aUnknown// "Unknown"
0x26c2  br.s     loc_26CA
0x26c4  ldarg.3
0x26c5  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::get_ClientId()
0x26ca  ldc.i4.0
0x26cb  newarr   [mscorlib]System.Object
0x26d0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26d5  stloc.s  0x10
0x26d7  ldarg.1
0x26d8  ldloc.s  4
0x26da  ldc.i4.s 0x21
0x26dc  ldloc.s  0x10
0x26de  ldc.i4.0
0x26df  newarr   [mscorlib]System.Object
0x26e4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26e9  ldarg.0
0x26ea  ldloc.s  4
0x26ec  ldstr    aSandboxClient// "Sandbox Client"
0x26f1  ldc.i4.0
  ... truncated ...
```
