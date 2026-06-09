# Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertContractTypeToString

- ea: `0x2a70`
- end: `0x2ade`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertContractTypeToString`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x2a70`

## pseudocode

```c

```

## disassembly

```asm
0x2a70  ldarg.0
0x2a71  switch   loc_2A9C, loc_2AA2, loc_2AA8, loc_2AAE, loc_2AB4, loc_2ABA, loc_2AC0, loc_2AC6, loc_2ACC
0x2a9a  br.s     loc_2AD2
0x2a9c  ldstr    aNone// "None"
0x2aa1  ret
0x2aa2  ldstr    aOneway// "OneWay"
0x2aa7  ret
0x2aa8  ldstr    aQueue// "Queue"
0x2aad  ret
0x2aae  ldstr    aRest// "Rest"
0x2ab3  ret
0x2ab4  ldstr    aTwoway// "TwoWay"
0x2ab9  ret
0x2aba  ldstr    aTopic// "Topic"
0x2abf  ret
0x2ac0  ldstr    aPersistentqueu// "PersistentQueue"
0x2ac5  ret
0x2ac6  ldstr    aEventhub// "EventHub"
0x2acb  ret
0x2acc  ldstr    aWebhook// "Webhook"
0x2ad1  ret
0x2ad2  ldarg.0
0x2ad3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ad8  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x2add  ret
```
