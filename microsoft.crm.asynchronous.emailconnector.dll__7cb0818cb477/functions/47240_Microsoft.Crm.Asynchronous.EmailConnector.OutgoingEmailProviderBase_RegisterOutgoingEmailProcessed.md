# Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::RegisterOutgoingEmailProcessed

- ea: `0x47240`
- end: `0x47379`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::RegisterOutgoingEmailProcessed`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x471f0`

## callees

- `0x42150`
- `0x42190`
- `0x46d50`
- `0x47240`
- `0x4e480`
- `0x71c40`
- `0x71dd0`

## string_xrefs

- `0x472fe`: `Server-Side Synchronization (Outgoing): Items Failed`
- `0x47308`: `Server-Side Synchronization (Outgoing): Items Failed Throughput`
- `0x4725e`: `Server-Side Synchronization (Outgoing): Items Delivered`
- `0x47268`: `Server-Side Synchronization (Outgoing): Items Delivered Throughput`
- `0x47314`: `Server-Side Synchronization (Outgoing): Transient Errors`
- `0x4731e`: `Server-Side Synchronization (Outgoing): Transient Errors Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x47240  ldarg.1
0x47241  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_FinalStatusCode()
0x47246  stloc.0
0x47247  ldloc.0
0x47248  ldc.i4.3
0x47249  beq.s    loc_4725E
0x4724b  ldloc.0
0x4724c  ldc.i4.6
0x4724d  beq      loc_47314
0x47252  ldloc.0
0x47253  ldc.i4.8
0x47254  beq      loc_472FE
0x47259  br       loc_47328
0x4725e  ldstr    aServerSideSync_19// "Server-Side Synchronization (Outgoing):"...
0x47263  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x47268  ldstr    aServerSideSync_20// "Server-Side Synchronization (Outgoing):"...
0x4726d  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x47272  ldarg.0
0x47273  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x47278  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsSent
0x4727d  ldarg.0
0x4727e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x47283  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsSent
0x47288  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x4728d  brtrue.s loc_47297
0x4728f  ldc.i4.1
0x47290  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x47295  br.s     loc_472BD
0x47297  ldarg.0
0x47298  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x4729d  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsSent
0x472a2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::get_Item(void)
0x472a7  callvirt instance string [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat::ToString()
0x472ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x472b1  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x472b6  ldc.i4.1
0x472b7  add
0x472b8  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x472bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x472c2  ldarg.1
0x472c3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::get_SenderMailbox()
0x472c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetMailboxData()
0x472cd  stloc.1
0x472ce  ldarg.0
0x472cf  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox> Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_Mailboxes()
0x472d4  ldloc.1
0x472d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x472da  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::ContainsKey(var<u1>)
0x472df  brfalse.s loc_47328
0x472e1  ldarg.0
0x472e2  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox> Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_Mailboxes()
0x472e7  ldloc.1
0x472e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x472ed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Item(void)
0x472f2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x472f7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_OutgoingEmailProcessCompleted(valuetype [mscorlib]System.DateTime value)
0x472fc  br.s     loc_47328
0x472fe  ldstr    aServerSideSync_15// "Server-Side Synchronization (Outgoing):"...
0x47303  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x47308  ldstr    aServerSideSync_16// "Server-Side Synchronization (Outgoing):"...
0x4730d  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x47312  br.s     loc_47328
0x47314  ldstr    aServerSideSync_21// "Server-Side Synchronization (Outgoing):"...
0x47319  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x4731e  ldstr    aServerSideSync_22// "Server-Side Synchronization (Outgoing):"...
0x47323  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x47328  ldarg.0
0x47329  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x4732e  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsProcessed
0x47333  ldarg.0
0x47334  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x47339  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsProcessed
0x4733e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x47343  brtrue.s loc_4734D
0x47345  ldc.i4.1
0x47346  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x4734b  br.s     loc_47373
0x4734d  ldarg.0
0x4734e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x47353  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsProcessed
0x47358  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::get_Item(void)
0x4735d  callvirt instance string [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat::ToString()
0x47362  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47367  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x4736c  ldc.i4.1
0x4736d  add
0x4736e  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x47373  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x47378  ret
```
