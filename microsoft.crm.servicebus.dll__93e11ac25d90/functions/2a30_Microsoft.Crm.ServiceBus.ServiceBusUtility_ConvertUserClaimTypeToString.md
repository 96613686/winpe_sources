# Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertUserClaimTypeToString

- ea: `0x2a30`
- end: `0x2a64`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertUserClaimTypeToString`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x2a30`

## pseudocode

```c

```

## disassembly

```asm
0x2a30  ldarg.0
0x2a31  ldc.i4.1
0x2a32  sub
0x2a33  switch   loc_2A46, loc_2A4C, loc_2A52
0x2a44  br.s     loc_2A58
0x2a46  ldstr    aNone// "None"
0x2a4b  ret
0x2a4c  ldstr    aUserid// "UserId"
0x2a51  ret
0x2a52  ldstr    aUserinfo// "UserInfo"
0x2a57  ret
0x2a58  ldarg.0
0x2a59  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a5e  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x2a63  ret
```
