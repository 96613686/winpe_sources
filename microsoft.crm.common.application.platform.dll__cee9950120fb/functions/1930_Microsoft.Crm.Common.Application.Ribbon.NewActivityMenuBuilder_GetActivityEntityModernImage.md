# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetActivityEntityModernImage

- ea: `0x1930`
- end: `0x1984`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetActivityEntityModernImage`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17c0`

## callees

- `0x1930`

## string_xrefs

- `0x196c`: `NewTask`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.1
0x1931  ldstr    aEmail// "email"
0x1936  call     bool [mscorlib]System.String::op_Equality(string, string)
0x193b  brtrue.s loc_1966
0x193d  ldarg.1
0x193e  ldstr    aTask// "task"
0x1943  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1948  brtrue.s loc_196C
0x194a  ldarg.1
0x194b  ldstr    aPhonecall// "phonecall"
0x1950  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1955  brtrue.s loc_1972
0x1957  ldarg.1
0x1958  ldstr    aAppointment// "appointment"
0x195d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1962  brtrue.s loc_1978
0x1964  br.s     loc_197E
0x1966  ldstr    aNewemail// "NewEmail"
0x196b  ret
0x196c  ldstr    aNewtask// "NewTask"
0x1971  ret
0x1972  ldstr    aNewphonecall// "NewPhoneCall"
0x1977  ret
0x1978  ldstr    aNewappointment// "NewAppointment"
0x197d  ret
0x197e  ldstr    aCustomactivity// "CustomActivity"
0x1983  ret
```
