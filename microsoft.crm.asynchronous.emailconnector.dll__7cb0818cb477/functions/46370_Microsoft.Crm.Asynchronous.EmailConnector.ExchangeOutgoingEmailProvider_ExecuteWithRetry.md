# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ExecuteWithRetry

- ea: `0x46370`
- end: `0x463ef`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ExecuteWithRetry`
- size: `127`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x43dc0`
- `0x449d0`
- `0x45280`
- `0x45a50`

## callees

- `0x46370`
- `0x46e10`
- `0x4da80`
- `0x4e480`

## string_xrefs

- `0x4638f`: `ThreadPool`
- `0x463a6`: `Attempt# {0}. Not enough threads exception occurred while doing a BeginInvoke. Introducing synchronous delay of 5 seconds. Exception: {1}`
- `0x463d3`: `Server-Side Synchronization: Synchronous Delays`

## pseudocode

```c

```

## disassembly

```asm
0x46370  ldc.i4.0
0x46371  stloc.0
0x46372  nop
0x46373  ldarg.1
0x46374  callvirt instance void [mscorlib]System.Action::Invoke()
0x46379  leave.s  loc_463EE
0x4637b  stloc.1
0x4637c  ldloc.1
0x4637d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x46382  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46387  brtrue.s loc_463EC
0x46389  ldloc.1
0x4638a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4638f  ldstr    aThreadpool// "ThreadPool"
0x46394  callvirt instance bool [mscorlib]System.String::Contains(string)
0x46399  brfalse.s loc_463EC
0x4639b  ldloc.0
0x4639c  ldc.i4.1
0x4639d  add
0x4639e  dup
0x4639f  stloc.0
0x463a0  ldc.i4.s 0x64
0x463a2  bge.s    loc_463EC
0x463a4  ldarg.0
0x463a5  ldc.i4.1
0x463a6  ldstr    aAttempt0NotEno// "Attempt# {0}. Not enough threads except"...
0x463ab  ldc.i4.2
0x463ac  newarr   [mscorlib]System.Object
0x463b1  dup
0x463b2  ldc.i4.0
0x463b3  ldloc.0
0x463b4  box      [mscorlib]System.Int32
0x463b9  stelem.ref
0x463ba  dup
0x463bb  ldc.i4.1
0x463bc  ldloc.1
0x463bd  ldarg.0
0x463be  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x463c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x463c8  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x463cd  stelem.ref
0x463ce  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x463d3  ldstr    aServerSideSync_14// "Server-Side Synchronization: Synchronou"...
0x463d8  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x463dd  ldc.i4.0
0x463de  ldc.i4.0
0x463df  ldc.i4.5
0x463e0  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x463e5  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x463ea  leave.s  loc_46372
0x463ec  rethrow
0x463ee  ret
```
