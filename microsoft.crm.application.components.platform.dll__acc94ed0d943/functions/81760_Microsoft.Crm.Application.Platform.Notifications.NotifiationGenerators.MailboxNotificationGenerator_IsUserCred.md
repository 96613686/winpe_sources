# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::IsUserCredentialRequired

- ea: `0x81760`
- end: `0x817f0`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::IsUserCredentialRequired`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x813e0`

## callees

- `0x5be20`
- `0x81760`

## string_xrefs

- `0x81761`: `incomingemaildeliverymethod`
- `0x8176e`: `incomingemaildeliverymethod`
- `0x817aa`: `incomingcredentialretrieval`
- `0x817b7`: `incomingcredentialretrieval`

## pseudocode

```c

```

## disassembly

```asm
0x81760  ldarg.1
0x81761  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x81766  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8176b  brfalse.s loc_81782
0x8176d  ldarg.1
0x8176e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x81773  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81778  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x8177d  ldc.i4.2
0x8177e  ceq
0x81780  br.s     loc_81783
0x81782  ldc.i4.0
0x81783  stloc.0
0x81784  ldarg.1
0x81785  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x8178a  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8178f  brfalse.s loc_817A6
0x81791  ldarg.1
0x81792  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x81797  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8179c  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x817a1  ldc.i4.2
0x817a2  ceq
0x817a4  br.s     loc_817A7
0x817a6  ldc.i4.0
0x817a7  brfalse.s loc_817CA
0x817a9  ldarg.2
0x817aa  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x817af  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x817b4  brfalse.s loc_817CA
0x817b6  ldarg.2
0x817b7  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x817bc  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x817c1  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod
0x817c6  brtrue.s loc_817CA
0x817c8  ldc.i4.1
0x817c9  ret
0x817ca  ldloc.0
0x817cb  brfalse.s loc_817EE
0x817cd  ldarg.2
0x817ce  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x817d3  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x817d8  brfalse.s loc_817EE
0x817da  ldarg.2
0x817db  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x817e0  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x817e5  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod
0x817ea  brtrue.s loc_817EE
0x817ec  ldc.i4.1
0x817ed  ret
0x817ee  ldc.i4.0
0x817ef  ret
```
