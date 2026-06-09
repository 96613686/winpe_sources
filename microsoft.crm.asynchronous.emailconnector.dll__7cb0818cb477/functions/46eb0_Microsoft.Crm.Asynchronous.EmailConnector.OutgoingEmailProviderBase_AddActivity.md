# Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::AddActivity

- ea: `0x46eb0`
- end: `0x46f56`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::AddActivity`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x43900`

## callees

- `0x421a0`
- `0x46c00`
- `0x46d50`
- `0x46eb0`
- `0x46f60`
- `0x4e480`
- `0x71ad0`

## string_xrefs

- `0x46eb0`: `Server-Side Synchronization (Outgoing): Items Processed`
- `0x46eba`: `Server-Side Synchronization (Outgoing): Items Processed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x46eb0  ldstr    aServerSideSync_17// "Server-Side Synchronization (Outgoing):"...
0x46eb5  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x46eba  ldstr    aServerSideSync_18// "Server-Side Synchronization (Outgoing):"...
0x46ebf  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x46ec4  ldarg.0
0x46ec5  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_InfoLevelPayload()
0x46eca  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailId
0x46ecf  ldarg.1
0x46ed0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x46ed5  stloc.3
0x46ed6  ldloca.s 3
0x46ed8  constrained. [mscorlib]System.Guid
0x46ede  callvirt instance string [mscorlib]System.Object::ToString()
0x46ee3  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x46ee8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x46eed  ldarg.1
0x46eee  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailActivity::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity email)
0x46ef3  stloc.0
0x46ef4  ldarg.0
0x46ef5  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_OutgoingActivities()
0x46efa  ldloc.0
0x46efb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity>::Add(var<u1>)
0x46f00  ldarg.1
0x46f01  ldstr    aSendermailboxi// "sendermailboxid"
0x46f06  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x46f0b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x46f10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x46f15  stloc.1
0x46f16  ldnull
0x46f17  stloc.2
0x46f18  ldarg.0
0x46f19  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox> Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_Mailboxes()
0x46f1e  ldloc.1
0x46f1f  ldloca.s 2
0x46f21  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::TryGetValue(var<u1>, !!T0)
0x46f26  brtrue.s loc_46F4E
0x46f28  ldloc.1
0x46f29  ldarg.0
0x46f2a  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x46f2f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x46f34  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::.ctor(valuetype [mscorlib]System.Guid mailboxId, valuetype [mscorlib]System.Guid organizationId)
0x46f39  stloc.2
0x46f3a  ldarg.0
0x46f3b  ldloc.2
0x46f3c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::GetLastSyncErrorDetailsForMailbox(class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x46f41  ldarg.0
0x46f42  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox> Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_Mailboxes()
0x46f47  ldloc.1
0x46f48  ldloc.2
0x46f49  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::set_Item(var<u1>, !!T0)
0x46f4e  ldloc.0
0x46f4f  ldloc.2
0x46f50  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::set_SenderMailbox(class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox value)
0x46f55  ret
```
