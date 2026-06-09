# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.EmailServerProfileNotificationGenerator::AddRequiredColumns

- ea: `0x81930`
- end: `0x8196d`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.EmailServerProfileNotificationGenerator::AddRequiredColumns`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x81939`: `incomingcredentialretrieval`
- `0x81949`: `incomingserverlocation`
- `0x81959`: `incomingusername`
- `0x81961`: `incomingpassword`

## pseudocode

```c

```

## disassembly

```asm
0x81930  ldarg.2
0x81931  ldc.i4.6
0x81932  newarr   [mscorlib]System.String
0x81937  dup
0x81938  ldc.i4.0
0x81939  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x8193e  stelem.ref
0x8193f  dup
0x81940  ldc.i4.1
0x81941  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x81946  stelem.ref
0x81947  dup
0x81948  ldc.i4.2
0x81949  ldstr    aIncomingserver// "incomingserverlocation"
0x8194e  stelem.ref
0x8194f  dup
0x81950  ldc.i4.3
0x81951  ldstr    aOutgoingserver// "outgoingserverlocation"
0x81956  stelem.ref
0x81957  dup
0x81958  ldc.i4.4
0x81959  ldstr    aIncominguserna// "incomingusername"
0x8195e  stelem.ref
0x8195f  dup
0x81960  ldc.i4.5
0x81961  ldstr    aIncomingpasswo// "incomingpassword"
0x81966  stelem.ref
0x81967  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x8196c  ret
```
