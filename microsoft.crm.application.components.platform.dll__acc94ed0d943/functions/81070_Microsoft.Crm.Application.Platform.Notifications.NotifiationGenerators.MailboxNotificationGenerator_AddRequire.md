# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::AddRequiredColumns

- ea: `0x81070`
- end: `0x81105`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::AddRequiredColumns`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x810e7`: `emailrouteraccessapproval`
- `0x81082`: `incomingemaildeliverymethod`
- `0x810b2`: `testemailconfigurationscheduled`
- `0x810c3`: `enabledforincomingemail`

## pseudocode

```c

```

## disassembly

```asm
0x81070  ldarg.2
0x81071  ldc.i4.s 0x10
0x81073  newarr   [mscorlib]System.String
0x81078  dup
0x81079  ldc.i4.0
0x8107a  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x8107f  stelem.ref
0x81080  dup
0x81081  ldc.i4.1
0x81082  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x81087  stelem.ref
0x81088  dup
0x81089  ldc.i4.2
0x8108a  ldstr    aActdeliverymet// "actdeliverymethod"
0x8108f  stelem.ref
0x81090  dup
0x81091  ldc.i4.3
0x81092  ldstr    aEmailserverpro// "emailserverprofile"
0x81097  stelem.ref
0x81098  dup
0x81099  ldc.i4.4
0x8109a  ldstr    aAllowemailconn// "allowemailconnectortousecredentials"
0x8109f  stelem.ref
0x810a0  dup
0x810a1  ldc.i4.5
0x810a2  ldstr    aUsername// "username"
0x810a7  stelem.ref
0x810a8  dup
0x810a9  ldc.i4.6
0x810aa  ldstr    aPassword// "password"
0x810af  stelem.ref
0x810b0  dup
0x810b1  ldc.i4.7
0x810b2  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x810b7  stelem.ref
0x810b8  dup
0x810b9  ldc.i4.8
0x810ba  ldstr    aHostid// "hostid"
0x810bf  stelem.ref
0x810c0  dup
0x810c1  ldc.i4.s 9
0x810c3  ldstr    aEnabledforinco// "enabledforincomingemail"
0x810c8  stelem.ref
0x810c9  dup
0x810ca  ldc.i4.s 0xA
0x810cc  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x810d1  stelem.ref
0x810d2  dup
0x810d3  ldc.i4.s 0xB
0x810d5  ldstr    aIsforwardmailb// "isforwardmailbox"
0x810da  stelem.ref
0x810db  dup
0x810dc  ldc.i4.s 0xC
0x810de  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x810e3  stelem.ref
0x810e4  dup
0x810e5  ldc.i4.s 0xD
0x810e7  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x810ec  stelem.ref
0x810ed  dup
0x810ee  ldc.i4.s 0xE
0x810f0  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x810f5  stelem.ref
0x810f6  dup
0x810f7  ldc.i4.s 0xF
0x810f9  ldstr    aTransientfailu// "transientfailurecount"
0x810fe  stelem.ref
0x810ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x81104  ret
```
