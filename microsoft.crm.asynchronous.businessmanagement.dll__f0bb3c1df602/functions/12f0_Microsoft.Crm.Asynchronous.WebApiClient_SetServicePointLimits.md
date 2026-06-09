# Microsoft.Crm.Asynchronous.WebApiClient::SetServicePointLimits

- ea: `0x12f0`
- end: `0x131a`
- name: `Microsoft.Crm.Asynchronous.WebApiClient::SetServicePointLimits`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x13800`

## callees

- `0x13a0`
- `0x13c0`
- `0x13e0`

## pseudocode

```c

```

## disassembly

```asm
0x12f0  ldarg.0
0x12f1  call     class [System]System.Net.ServicePoint [System]System.Net.ServicePointManager::FindServicePoint(class [System]System.Uri)
0x12f6  dup
0x12f7  ldarg.1
0x12f8  callvirt instance int32 Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::get_ConnectionLimit()
0x12fd  callvirt instance void [System]System.Net.ServicePoint::set_ConnectionLimit(int32)
0x1302  dup
0x1303  ldarg.1
0x1304  callvirt instance int32 Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::get_ConnectionLeaseTimeoutInMilliSeconds()
0x1309  callvirt instance void [System]System.Net.ServicePoint::set_ConnectionLeaseTimeout(int32)
0x130e  ldarg.1
0x130f  callvirt instance int32 Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::get_MaxIdleTimeInMilliSeconds()
0x1314  callvirt instance void [System]System.Net.ServicePoint::set_MaxIdleTime(int32)
0x1319  ret
```
