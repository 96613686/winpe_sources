# Microsoft.Crm.ServiceBus.WebhookClient::SetServicePointLimits

- ea: `0x6590`
- end: `0x65ba`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::SetServicePointLimits`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x68c0`

## callees

- `0x5df0`
- `0x5e10`
- `0x5e30`

## pseudocode

```c

```

## disassembly

```asm
0x6590  ldarg.1
0x6591  call     class [System]System.Net.ServicePoint [System]System.Net.ServicePointManager::FindServicePoint(class [System]System.Uri)
0x6596  dup
0x6597  ldarg.2
0x6598  callvirt instance int32 Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::get_ConnectionLimit()
0x659d  callvirt instance void [System]System.Net.ServicePoint::set_ConnectionLimit(int32)
0x65a2  dup
0x65a3  ldarg.2
0x65a4  callvirt instance int32 Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::get_ConnectionLeaseTimeoutInMilliSeconds()
0x65a9  callvirt instance void [System]System.Net.ServicePoint::set_ConnectionLeaseTimeout(int32)
0x65ae  ldarg.2
0x65af  callvirt instance int32 Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::get_MaxIdleTimeInMilliSeconds()
0x65b4  callvirt instance void [System]System.Net.ServicePoint::set_MaxIdleTime(int32)
0x65b9  ret
```
