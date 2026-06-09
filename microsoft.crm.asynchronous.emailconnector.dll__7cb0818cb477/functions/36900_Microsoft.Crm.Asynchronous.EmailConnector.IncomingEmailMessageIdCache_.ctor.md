# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::.ctor

- ea: `0x36900`
- end: `0x3695b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::.ctor`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x36880`
- `0x368c0`

## callees

- `0x2f600`
- `0x36900`
- `0x4d8e0`
- `0x4dcf0`

## string_xrefs

- `0x36937`: `IncomingEmailMessageIdCache: Cache started for manual email.`
- `0x36950`: `IncomingEmailMessageIdCache: Cache started.`

## pseudocode

```c

```

## disassembly

```asm
0x36900  ldarg.0
0x36901  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance()
0x36906  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration::get_MessageIdCacheCapacity()
0x3690b  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance()
0x36910  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration::get_MessageIdCacheRetentionTime()
0x36915  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::.ctor(int32 capacity, valuetype [mscorlib]System.TimeSpan retentionTime)
0x3691a  ldarg.0
0x3691b  ldarg.1
0x3691c  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::_forManualEmail
0x36921  ldarg.0
0x36922  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::_forManualEmail
0x36927  brfalse.s loc_36942
0x36929  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3692e  ldnull
0x3692f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36934  ldc.i4.s 0x3D
0x36936  ldc.i4.3
0x36937  ldstr    aIncomingemailm// "IncomingEmailMessageIdCache: Cache star"...
0x3693c  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string data)
0x36941  ret
0x36942  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36947  ldnull
0x36948  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3694d  ldc.i4.s 0x3D
0x3694f  ldc.i4.3
0x36950  ldstr    aIncomingemailm_0// "IncomingEmailMessageIdCache: Cache star"...
0x36955  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string data)
0x3695a  ret
```
