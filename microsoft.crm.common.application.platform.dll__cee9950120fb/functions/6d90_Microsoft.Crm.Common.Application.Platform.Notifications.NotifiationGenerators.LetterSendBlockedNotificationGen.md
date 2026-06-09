# Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.LetterSendBlockedNotificationGenerator::AddRequiredColumns

- ea: `0x6d90`
- end: `0x6d9f`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.LetterSendBlockedNotificationGenerator::AddRequiredColumns`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x6d90  ldarg.1
0x6d91  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.Common.Application.Platform.ActivityBase::GetPartyListProperties(string entityName)
0x6d96  stloc.0
0x6d97  ldarg.2
0x6d98  ldloc.0
0x6d99  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6d9e  ret
```
