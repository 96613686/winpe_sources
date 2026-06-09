# Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::AutoDiscoverServerUrlInternal

- ea: `0x7040`
- end: `0x70a5`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::AutoDiscoverServerUrlInternal`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x6fe0`
- `0x70e0`
- `0x7170`

## callees

- `0x6e30`
- `0x7040`
- `0x70b0`
- `0x8560`
- `0x4e480`

## string_xrefs

- `0x7051`: `Server-Side Synchronization (Exchange Auto-discover): Cache Miss`
- `0x7081`: `ExchangeAutoDiscover: Cannot find server url for mailbox id: {0} in the mailbox cache even after auto discovery`

## pseudocode

```c

```

## disassembly

```asm
0x7040  ldarg.0
0x7041  ldarg.2
0x7042  ldarg.s  5
0x7044  ldarg.s  6
0x7046  ldloca.s 0
0x7048  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::TryGetServerUrlFromMailboxCache(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoveryWindow autoDiscoverType, valuetype [mscorlib]System.DateTime discoveryStartTime, [out] class [System]System.Uri& serverUri)
0x704d  brfalse.s loc_7051
0x704f  ldloc.0
0x7050  ret
0x7051  ldstr    aServerSideSync_0// "Server-Side Synchronization (Exchange A"...
0x7056  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x705b  ldarg.0
0x705c  ldarg.1
0x705d  ldarg.2
0x705e  ldarg.3
0x705f  ldarg.s  4
0x7061  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::GetDiscoverer(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile emailServerProfile, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeVersion exchangeVersion, class Microsoft.Crm.Asynchronous.EmailConnector.ICredentialInfo credentialInfo)
0x7066  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UserSettingsDiscovererBase::Discover()
0x706b  ldarg.0
0x706c  ldarg.2
0x706d  ldarg.s  5
0x706f  ldarg.s  6
0x7071  ldloca.s 0
0x7073  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.AutoDiscoveryCacheBase::TryGetServerUrlFromMailboxCache(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAutoDiscoveryWindow autoDiscoverType, valuetype [mscorlib]System.DateTime discoveryStartTime, [out] class [System]System.Uri& serverUri)
0x7078  brfalse.s loc_707C
0x707a  ldloc.0
0x707b  ret
0x707c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7081  ldstr    aExchangeautodi_2// "ExchangeAutoDiscover: Cannot find serve"...
0x7086  ldc.i4.1
0x7087  newarr   [mscorlib]System.Object
0x708c  dup
0x708d  ldc.i4.0
0x708e  ldarg.2
0x708f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x7094  box      [mscorlib]System.Guid
0x7099  stelem.ref
0x709a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x709f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x70a4  throw
```
