# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor::RegisterAutoDiscoveryCompletion

- ea: `0x79c40`
- end: `0x79c6d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor::RegisterAutoDiscoveryCompletion`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x8670`

## callees

- `0x797c0`
- `0x797e0`

## string_xrefs

- `0x79c4c`: `Server-Side Synchronization (Exchange Auto-discover): Average time taken for auto-discovery`
- `0x79c62`: `Server-Side Synchronization (Exchange Auto-discover): Average time taken for auto-discovery base`

## pseudocode

```c

```

## disassembly

```asm
0x79c40  ldarg.0
0x79c41  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor::_stopWatch
0x79c46  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x79c4b  ldarg.0
0x79c4c  ldstr    aServerSideSync_46// "Server-Side Synchronization (Exchange A"...
0x79c51  ldarg.0
0x79c52  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoverTrafficMonitor::_stopWatch
0x79c57  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedTicks()
0x79c5c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::IncrementCounter(string counterName, int64 increment)
0x79c61  ldarg.0
0x79c62  ldstr    aServerSideSync_47// "Server-Side Synchronization (Exchange A"...
0x79c67  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::IncrementCounter(string counterName)
0x79c6c  ret
```
