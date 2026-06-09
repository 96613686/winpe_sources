# Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::TryGetServerUrlFromMailboxCache

- ea: `0x6e30`
- end: `0x6fd4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::TryGetServerUrlFromMailboxCache`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x6d40`
- `0x7040`

## callees

- `0x6e30`
- `0x4d8c0`
- `0x4dcf0`
- `0x4e480`

## string_xrefs

- `0x6e55`: `Mailbox with id: {0} was not found in the cache.`
- `0x6e8a`: `Server-Side Synchronization (Exchange Auto-discover): Cache Hit`
- `0x6f0e`: `Server-Side Synchronization (Exchange Auto-discover): Cache Hit`
- `0x6f7a`: `Server-Side Synchronization (Exchange Auto-discover): Cache Hit`
- `0x6f27`: `ExchangeAutoDiscover: Returning already auto discovered url for mailbox id: {0}.`
- `0x6f93`: `ExchangeAutoDiscover: Returning already auto discovered url in last 5 minutes for mailbox id: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6e30  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache::Instance()
0x6e35  ldarg.1
0x6e36  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x6e3b  ldarg.1
0x6e3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x6e41  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6e46  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData>::LookupEntry(void, var<u1>)
0x6e4b  stloc.0
0x6e4c  ldloc.0
0x6e4d  ldnull
0x6e4e  cgt.un
0x6e50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e55  ldstr    aMailboxWithId0// "Mailbox with id: {0} was not found in t"...
0x6e5a  ldc.i4.1
0x6e5b  newarr   [mscorlib]System.Object
0x6e60  dup
0x6e61  ldc.i4.0
0x6e62  ldarg.1
0x6e63  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x6e68  box      [mscorlib]System.Guid
0x6e6d  stelem.ref
0x6e6e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6e78  ldc.i4.0
0x6e79  stloc.1
0x6e7a  ldloc.0
0x6e7b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_LastAutoDiscoveredOn()
0x6e80  ldarg.3
0x6e81  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6e86  brfalse.s loc_6ED8
0x6e88  ldc.i4.1
0x6e89  stloc.1
0x6e8a  ldstr    aServerSideSync// "Server-Side Synchronization (Exchange A"...
0x6e8f  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x6e94  ldloc.0
0x6e95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x6e9a  ldloc.0
0x6e9b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ea0  ldc.i4.s 0x3D
0x6ea2  ldc.i4.3
0x6ea3  ldstr    aExchangeautodi// "ExchangeAutoDiscover: Returning auto di"...
0x6ea8  ldc.i4.3
0x6ea9  newarr   [mscorlib]System.Object
0x6eae  dup
0x6eaf  ldc.i4.0
0x6eb0  ldloc.0
0x6eb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x6eb6  box      [mscorlib]System.Guid
0x6ebb  stelem.ref
0x6ebc  dup
0x6ebd  ldc.i4.1
0x6ebe  ldloc.0
0x6ebf  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_LastAutoDiscoveredOn()
0x6ec4  box      [mscorlib]System.DateTime
0x6ec9  stelem.ref
0x6eca  dup
0x6ecb  ldc.i4.2
0x6ecc  ldarg.3
0x6ecd  box      [mscorlib]System.DateTime
0x6ed2  stelem.ref
0x6ed3  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6ed8  ldarg.2
0x6ed9  brtrue.s loc_6F45
0x6edb  ldloc.0
0x6edc  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_LastAutoDiscoveredOn()
0x6ee1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6ee6  stloc.2
0x6ee7  ldloca.s 2
0x6ee9  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance()
0x6eee  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration::get_ExchangeAutoDiscoverForceRefreshInterval()
0x6ef3  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x6ef8  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6efd  brfalse.s loc_6F45
0x6eff  ldloc.0
0x6f00  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EwsUrl()
0x6f05  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f0a  brtrue.s loc_6F45
0x6f0c  ldc.i4.1
0x6f0d  stloc.1
0x6f0e  ldstr    aServerSideSync// "Server-Side Synchronization (Exchange A"...
0x6f13  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x6f18  ldloc.0
0x6f19  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x6f1e  ldloc.0
0x6f1f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6f24  ldc.i4.s 0x3D
0x6f26  ldc.i4.3
0x6f27  ldstr    aExchangeautodi_0// "ExchangeAutoDiscover: Returning already"...
0x6f2c  ldc.i4.1
0x6f2d  newarr   [mscorlib]System.Object
0x6f32  dup
0x6f33  ldc.i4.0
0x6f34  ldloc.0
0x6f35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x6f3a  box      [mscorlib]System.Guid
0x6f3f  stelem.ref
0x6f40  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6f45  ldarg.2
0x6f46  ldc.i4.1
0x6f47  bne.un.s loc_6FB1
0x6f49  ldloc.0
0x6f4a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_LastAutoDiscoveredOn()
0x6f4f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6f54  stloc.2
0x6f55  ldloca.s 2
0x6f57  ldc.i4.0
0x6f58  ldc.i4.5
0x6f59  ldc.i4.0
0x6f5a  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x6f5f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x6f64  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6f69  brfalse.s loc_6FB1
0x6f6b  ldloc.0
0x6f6c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EwsUrl()
0x6f71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f76  brtrue.s loc_6FB1
0x6f78  ldc.i4.1
0x6f79  stloc.1
0x6f7a  ldstr    aServerSideSync// "Server-Side Synchronization (Exchange A"...
0x6f7f  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x6f84  ldloc.0
0x6f85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x6f8a  ldloc.0
0x6f8b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6f90  ldc.i4.s 0x3D
0x6f92  ldc.i4.3
0x6f93  ldstr    aExchangeautodi_1// "ExchangeAutoDiscover: Returning already"...
0x6f98  ldc.i4.1
0x6f99  newarr   [mscorlib]System.Object
0x6f9e  dup
0x6f9f  ldc.i4.0
0x6fa0  ldloc.0
0x6fa1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x6fa6  box      [mscorlib]System.Guid
0x6fab  stelem.ref
0x6fac  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6fb1  ldarg.s  4
0x6fb3  ldloc.1
0x6fb4  brfalse.s loc_6FC3
0x6fb6  ldloc.0
0x6fb7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EwsUrl()
0x6fbc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6fc1  brfalse.s loc_6FC6
0x6fc3  ldnull
0x6fc4  br.s     loc_6FD1
0x6fc6  ldloc.0
0x6fc7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EwsUrl()
0x6fcc  newobj   instance void [System]System.Uri::.ctor(string)
0x6fd1  stind.ref
0x6fd2  ldloc.1
0x6fd3  ret
```
