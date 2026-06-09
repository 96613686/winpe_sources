# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::ExecuteWithRetry

- ea: `0x3abc0`
- end: `0x3ac3f`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::ExecuteWithRetry`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3a170`

## callees

- `0x3ab40`
- `0x3abc0`
- `0x4da80`
- `0x4e480`

## string_xrefs

- `0x3abdf`: `ThreadPool`
- `0x3abf6`: `Attempt# {0}. Not enough threads exception occurred while doing a BeginInvoke. Introducing synchronous delay of 5 seconds. Exception: {1}`
- `0x3ac23`: `Server-Side Synchronization: Synchronous Delays`

## pseudocode

```c

```

## disassembly

```asm
0x3abc0  ldc.i4.0
0x3abc1  stloc.0
0x3abc2  nop
0x3abc3  ldarg.1
0x3abc4  callvirt instance void [mscorlib]System.Action::Invoke()
0x3abc9  leave.s  loc_3AC3E
0x3abcb  stloc.1
0x3abcc  ldloc.1
0x3abcd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3abd2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3abd7  brtrue.s loc_3AC3C
0x3abd9  ldloc.1
0x3abda  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3abdf  ldstr    aThreadpool// "ThreadPool"
0x3abe4  callvirt instance bool [mscorlib]System.String::Contains(string)
0x3abe9  brfalse.s loc_3AC3C
0x3abeb  ldloc.0
0x3abec  ldc.i4.1
0x3abed  add
0x3abee  dup
0x3abef  stloc.0
0x3abf0  ldc.i4.s 0x64
0x3abf2  bge.s    loc_3AC3C
0x3abf4  ldarg.0
0x3abf5  ldc.i4.1
0x3abf6  ldstr    aAttempt0NotEno// "Attempt# {0}. Not enough threads except"...
0x3abfb  ldc.i4.2
0x3abfc  newarr   [mscorlib]System.Object
0x3ac01  dup
0x3ac02  ldc.i4.0
0x3ac03  ldloc.0
0x3ac04  box      [mscorlib]System.Int32
0x3ac09  stelem.ref
0x3ac0a  dup
0x3ac0b  ldc.i4.1
0x3ac0c  ldloc.1
0x3ac0d  ldarg.0
0x3ac0e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3ac13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3ac18  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3ac1d  stelem.ref
0x3ac1e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3ac23  ldstr    aServerSideSync_14// "Server-Side Synchronization: Synchronou"...
0x3ac28  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3ac2d  ldc.i4.0
0x3ac2e  ldc.i4.0
0x3ac2f  ldc.i4.5
0x3ac30  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3ac35  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x3ac3a  leave.s  loc_3ABC2
0x3ac3c  rethrow
0x3ac3e  ret
```
