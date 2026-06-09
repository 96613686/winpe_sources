# Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::DiscoverUserSettings

- ea: `0x8670`
- end: `0x8748`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::DiscoverUserSettings`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x8560`

## callees

- `0x8400`
- `0x84c0`
- `0x84d0`
- `0x84e0`
- `0x8500`
- `0x8670`
- `0x8750`
- `0x87d0`
- `0x88a0`
- `0x91a0`
- `0x4da80`
- `0x4e480`
- `0x794b0`
- `0x79540`
- `0x79c40`

## string_xrefs

- `0x8690`: `ExchangeAutoDiscover: Successfully auto discovered user settings for mailbox: {0}. \nAutodiscoverService Trace: {1}`
- `0x86c1`: `Server-Side Synchronization (Exchange Auto-discover): Discoveries Successful`
- `0x86ce`: `Server-Side Synchronization (Exchange Auto-discover): Discoveries Failed`
- `0x86da`: `ExchangeAutoDiscover: Error auto discovering user settings for mailbox: {0}. \nError Details: {1}. \nAutodiscoverService Trace: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x8670  ldarg.0
0x8671  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::InitializeForDiscovery()
0x8676  ldarg.0
0x8677  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_TrafficMonitor()
0x867c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::RegisterConnectionOpened()
0x8681  ldarg.0
0x8682  ldc.i4.1
0x8683  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::set_IsConnectionOpen(bool value)
0x8688  ldarg.0
0x8689  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::DiscoverUserSettingsInternal()
0x868e  ldarg.0
0x868f  ldc.i4.4
0x8690  ldstr    aExchangeautodi_4// "ExchangeAutoDiscover: Successfully auto"...
0x8695  ldc.i4.2
0x8696  newarr   [mscorlib]System.Object
0x869b  dup
0x869c  ldc.i4.0
0x869d  ldarg.0
0x869e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_Mailbox()
0x86a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x86a8  box      [mscorlib]System.Guid
0x86ad  stelem.ref
0x86ae  dup
0x86af  ldc.i4.1
0x86b0  ldarg.0
0x86b1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.TraceListener Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_TraceListener()
0x86b6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.TraceListener::get_TraceMessage()
0x86bb  stelem.ref
0x86bc  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x86c1  ldstr    aServerSideSync_1// "Server-Side Synchronization (Exchange A"...
0x86c6  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x86cb  leave.s  loc_8747
0x86cd  stloc.0
0x86ce  ldstr    aServerSideSync_2// "Server-Side Synchronization (Exchange A"...
0x86d3  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x86d8  ldarg.0
0x86d9  ldc.i4.1
0x86da  ldstr    aExchangeautodi_5// "ExchangeAutoDiscover: Error auto discov"...
0x86df  ldc.i4.3
0x86e0  newarr   [mscorlib]System.Object
0x86e5  dup
0x86e6  ldc.i4.0
0x86e7  ldarg.0
0x86e8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_Mailbox()
0x86ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x86f2  box      [mscorlib]System.Guid
0x86f7  stelem.ref
0x86f8  dup
0x86f9  ldc.i4.1
0x86fa  ldloc.0
0x86fb  ldarg.0
0x86fc  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_Mailbox()
0x8701  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x8706  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x870b  stelem.ref
0x870c  dup
0x870d  ldc.i4.2
0x870e  ldarg.0
0x870f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.TraceListener Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_TraceListener()
0x8714  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.TraceListener::get_TraceMessage()
0x8719  stelem.ref
0x871a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x871f  rethrow
0x8721  ldarg.0
0x8722  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_IsConnectionOpen()
0x8727  brfalse.s loc_873B
0x8729  ldarg.0
0x872a  ldc.i4.0
0x872b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::set_IsConnectionOpen(bool value)
0x8730  ldarg.0
0x8731  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_TrafficMonitor()
0x8736  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::RegisterConnectionClosed()
0x873b  ldarg.0
0x873c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::get_TrafficMonitor()
0x8741  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor::RegisterAutoDiscoveryCompletion()
0x8746  endfinally
0x8747  ret
```
