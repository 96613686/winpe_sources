# <>c__DisplayClass5_0::<Execute>b__0

- ea: `0x14150`
- end: `0x14474`
- name: `<>c__DisplayClass5_0::<Execute>b__0`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callees

- `0x1030`
- `0x1480`
- `0x3bc0`
- `0x3be0`
- `0x4870`
- `0x6940`
- `0x6b70`
- `0x6b90`
- `0x6bb0`
- `0x6be0`
- `0x7780`
- `0x78e0`
- `0x8090`
- `0xc2e0`
- `0xc360`
- `0xf930`
- `0x14150`

## string_xrefs

- `0x143f0`: `AuthenticationEngine.Execute(), ExceptionHandlerAction.Redirect, Sku != ConfigSku.Live`

## pseudocode

```c

```

## disassembly

```asm
0x14150  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsOwinEnabled()
0x14155  brfalse.s loc_1415C
0x14157  leave    loc_14473
0x1415c  ldc.i4.1
0x1415d  stloc.0
0x1415e  ldc.i4.0
0x1415f  stloc.1
0x14160  ldc.i4.0
0x14161  stloc.2
0x14162  ldc.i4.0
0x14163  stloc.3
0x14164  ldarg.0
0x14165  ldfld    object <>c__DisplayClass5_0::sender
0x1416a  castclass [System.Web]System.Web.HttpApplication
0x1416f  stloc.s  4
0x14171  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x14176  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1417b  ldc.i4.2
0x1417c  bne.un.s loc_1418C
0x1417e  ldloc.s  4
0x14180  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsRequestForTestPage(class [System.Web]System.Web.HttpApplication application)
0x14185  brfalse.s loc_1418C
0x14187  leave    loc_14473
0x1418c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x14191  brfalse.s loc_141C5
0x14193  ldstr    aAuthengineBegi// "AuthEngine_BEGIN_EXECUTE"
0x14198  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x1419d  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x141a2  ldc.i4.3
0x141a3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x141a8  ldloc.s  4
0x141aa  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x141af  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x141b4  ldloc.s  4
0x141b6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x141bb  callvirt instance int32 [System.Web]System.Web.HttpRequest::get_TotalBytes()
0x141c0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnBeginRequest(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceTraceType, valuetype [mscorlib]System.Guid, string, int32)
0x141c5  nop
0x141c6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x141cb  ldc.i4.s 0x16
0x141cd  ldstr    aAuthRequest01F// "AUTH: Request [{0} {1}] from [{2}] ente"...
0x141d2  ldc.i4.3
0x141d3  newarr   [mscorlib]System.Object
0x141d8  dup
0x141d9  ldc.i4.0
0x141da  ldloc.s  4
0x141dc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x141e1  callvirt instance string [System.Web]System.Web.HttpRequest::get_HttpMethod()
0x141e6  stelem.ref
0x141e7  dup
0x141e8  ldc.i4.1
0x141e9  ldloc.s  4
0x141eb  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x141f0  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x141f5  stelem.ref
0x141f6  dup
0x141f7  ldc.i4.2
0x141f8  ldloc.s  4
0x141fa  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x141ff  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserHostAddress()
0x14204  stelem.ref
0x14205  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1420a  ldloc.s  4
0x1420c  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x14211  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x14216  ldstr    aAuthentication_13// "AuthenticationState"
0x1421b  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x14220  brfalse.s loc_1423E
0x14222  ldloc.s  4
0x14224  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x14229  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1422e  ldstr    aAuthentication_13// "AuthenticationState"
0x14233  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x14238  unbox.any Microsoft.Crm.Authentication.Engine.AuthenticationState
0x1423d  stloc.3
0x1423e  ldloc.3
0x1423f  ldc.i4.1
0x14240  sub
0x14241  switch   loc_14274, loc_14278, loc_14258, loc_14274
0x14256  br.s     loc_142B9
0x14258  ldloc.s  4
0x1425a  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x1425f  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyPageIfNotAuthenticated(class [System.Web]System.Web.HttpContext context)
0x14264  brfalse.s loc_142E0
0x14266  ldstr    aAuthentication_18// "AuthenticationEngine.Execute: ClaimsRej"...
0x1426b  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x14270  ldc.i4.1
0x14271  stloc.1
0x14272  br.s     loc_142E0
0x14274  ldc.i4.0
0x14275  stloc.0
0x14276  br.s     loc_142E0
0x14278  ldarg.0
0x14279  ldfld    class Microsoft.Crm.Authentication.AuthenticationEngine <>c__DisplayClass5_0::<>4__this
0x1427e  call     instance class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationEngine::get__claimsProvider()
0x14283  brfalse.s loc_1429D
0x14285  ldarg.0
0x14286  ldfld    class Microsoft.Crm.Authentication.AuthenticationEngine <>c__DisplayClass5_0::<>4__this
0x1428b  call     instance class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationEngine::get__claimsProvider()
0x14290  ldloc.s  4
0x14292  callvirt instance bool Microsoft.Crm.Authentication.IAuthenticationProvider::Authenticate(class [System.Web]System.Web.HttpApplication application)
0x14297  brfalse.s loc_1429D
0x14299  ldc.i4.0
0x1429a  stloc.0
0x1429b  br.s     loc_142E0
0x1429d  ldloc.s  4
0x1429f  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x142a4  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyPageIfNotAuthenticated(class [System.Web]System.Web.HttpContext context)
0x142a9  brfalse.s loc_142E0
0x142ab  ldstr    aAuthentication_19// "AuthenticationEngine.Execute: claims pr"...
0x142b0  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x142b5  ldc.i4.1
0x142b6  stloc.1
0x142b7  br.s     loc_142E0
0x142b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x142be  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x142c3  ldc.i4.2
0x142c4  bne.un.s loc_142CA
0x142c6  ldc.i4.0
0x142c7  stloc.0
0x142c8  br.s     loc_142E0
0x142ca  ldarg.0
0x142cb  ldfld    class Microsoft.Crm.Authentication.AuthenticationEngine <>c__DisplayClass5_0::<>4__this
0x142d0  call     instance class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationEngine::get__provider()
0x142d5  ldloc.s  4
0x142d7  callvirt instance bool Microsoft.Crm.Authentication.IAuthenticationProvider::Authenticate(class [System.Web]System.Web.HttpApplication application)
0x142dc  brfalse.s loc_142E0
0x142de  ldc.i4.0
0x142df  stloc.0
0x142e0  leave    loc_1440D
0x142e5  stloc.s  5
0x142e7  ldloc.s  5
0x142e9  isinst   [mscorlib]System.Threading.ThreadAbortException
0x142ee  brfalse.s loc_14303
0x142f0  ldloc.s  4
0x142f2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x142f7  callvirt instance int32 [System.Web]System.Web.HttpResponse::get_StatusCode()
0x142fc  ldc.i4   0x191
0x14301  beq.s    loc_14333
0x14303  ldloc.s  5
0x14305  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1430a  ldstr    aAuthentication_20// "AuthenticationEngine.Execute(), StatusC"...
0x1430f  ldc.i4.1
0x14310  newarr   [mscorlib]System.Object
0x14315  dup
0x14316  ldc.i4.0
0x14317  ldloc.s  4
0x14319  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1431e  callvirt instance int32 [System.Web]System.Web.HttpResponse::get_StatusCode()
0x14323  box      [mscorlib]System.Int32
0x14328  stelem.ref
0x14329  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1432e  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x14333  ldloc.s  5
0x14335  isinst   [System.Data]System.Data.SqlClient.SqlException
0x1433a  stloc.s  6
0x1433c  ldloc.s  6
0x1433e  brfalse.s loc_14348
0x14340  ldloc.s  6
0x14342  ldc.i4.1
0x14343  call     void Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::LogSqlException(class [System.Data]System.Data.SqlClient.SqlException sqlExp, valuetype [System]System.Diagnostics.EventLogEntryType errorLevel)
0x14348  ldloc.s  5
0x1434a  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x1434f  stloc.s  7
0x14351  ldloc.s  7
0x14353  brfalse  loc_14409
0x14358  call     class Microsoft.Crm.Authentication.Engine.IAuthenticationEngineExceptionHandler Microsoft.Crm.Authentication.Engine.AuthenticationEngineExceptionHandlerFactory::GetHandler()
0x1435d  ldloc.s  7
0x1435f  ldloc.s  4
0x14361  callvirt instance class Microsoft.Crm.Authentication.Engine.ExceptionHandlerResult Microsoft.Crm.Authentication.Engine.IAuthenticationEngineExceptionHandler::HandleException(class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex, class [System.Web]System.Web.HttpApplication application)
0x14366  stloc.s  8
0x14368  ldloc.s  8
0x1436a  callvirt instance valuetype Microsoft.Crm.Authentication.Engine.ExceptionHandlerAction Microsoft.Crm.Authentication.Engine.ExceptionHandlerResult::get_Action()
0x1436f  stloc.s  9
0x14371  ldloc.s  9
0x14373  switch   loc_14409, loc_14386, loc_14394
0x14384  br.s     loc_143FC
0x14386  ldloc.s  7
0x14388  ldstr    aAuthentication_21// "AuthenticationEngine.Execute(), Excepti"...
0x1438d  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x14392  rethrow
0x14394  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x14399  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1439e  ldc.i4.2
0x1439f  bne.un.s loc_143EE
0x143a1  ldloc.s  4
0x143a3  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x143a8  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyServiceIfNotAuthenticated(class [System.Web]System.Web.HttpContext context)
0x143ad  brtrue.s loc_143BD
0x143af  ldloc.s  4
0x143b1  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x143b6  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyPageIfNotAuthenticated(class [System.Web]System.Web.HttpContext context)
0x143bb  brfalse.s loc_143D9
0x143bd  ldloc.s  4
0x143bf  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x143c4  ldstr    aErrorDescripti// "error_description"
0x143c9  ldloc.s  7
0x143cb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x143d0  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse(class [System.Web]System.Web.HttpContext context, string errorCode, string errorDescription)
0x143d5  ldc.i4.1
0x143d6  stloc.2
0x143d7  br.s     loc_14409
0x143d9  ldloc.s  8
0x143db  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Engine.ExceptionHandlerResult::get_OrganizationId()
0x143e0  ldloc.s  8
0x143e2  callvirt instance string Microsoft.Crm.Authentication.Engine.ExceptionHandlerResult::get_ReasonForRedirect()
0x143e7  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectToAppPortalNotificationUrl(valuetype [mscorlib]System.Guid, string)
0x143ec  br.s     loc_14409
0x143ee  ldloc.s  7
0x143f0  ldstr    aAuthentication_22// "AuthenticationEngine.Execute(), Excepti"...
0x143f5  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x143fa  rethrow
0x143fc  ldstr    aAuthentication_23// "AuthenticationPipeline failure with unr"...
0x14401  ldloc.s  5
0x14403  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotImplementedException::.ctor(string, class [mscorlib]System.Exception)
0x14408  throw
0x14409  ldc.i4.1
0x1440a  stloc.0
0x1440b  leave.s  loc_1440D
0x1440d  ldloc.0
0x1440e  brfalse.s loc_14449
0x14410  ldloc.2
0x14411  brtrue.s loc_1443F
0x14413  ldloc.s  4
0x14415  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1441a  ldc.i4   0x194
0x1441f  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x14424  ldloc.1
0x14425  brfalse.s loc_14438
0x14427  ldloc.s  4
0x14429  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1442e  ldc.i4   0x191
0x14433  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x14438  ldloc.s  4
0x1443a  callvirt instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x1443f  ldstr    aAuthentication_24// "AuthenticationEngine.Execute: request r"...
0x14444  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x14449  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x1444e  brfalse.s loc_14465
0x14450  ldstr    aAuthengineEndE// "AuthEngine_END_EXECUTE"
0x14455  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x1445a  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x1445f  ldc.i4.1
0x14460  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool)
0x14465  leave.s  loc_14473
0x14467  ldstr    aAuthentication_25// "AuthenticationEngine.Execute()"
0x1446c  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x14471  rethrow
0x14473  ret
```
