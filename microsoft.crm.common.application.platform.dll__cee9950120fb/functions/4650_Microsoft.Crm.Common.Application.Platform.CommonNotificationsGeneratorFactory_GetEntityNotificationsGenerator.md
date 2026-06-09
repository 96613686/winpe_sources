# Microsoft.Crm.Common.Application.Platform.CommonNotificationsGeneratorFactory::GetEntityNotificationsGenerator

- ea: `0x4650`
- end: `0x468d`
- name: `Microsoft.Crm.Common.Application.Platform.CommonNotificationsGeneratorFactory::GetEntityNotificationsGenerator`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x4650`
- `0x6e10`
- `0x6e50`

## pseudocode

```c

```

## disassembly

```asm
0x4650  ldarg.0
0x4651  ldstr    aFax// "fax"
0x4656  call     bool [mscorlib]System.String::op_Equality(string, string)
0x465b  brtrue.s loc_4679
0x465d  ldarg.0
0x465e  ldstr    aLetter// "letter"
0x4663  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4668  brtrue.s loc_467F
0x466a  ldarg.0
0x466b  ldstr    aQueue// "queue"
0x4670  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4675  brtrue.s loc_4685
0x4677  br.s     loc_468B
0x4679  newobj   instance void Microsoft.Crm.Common.Application.Platform.Notifications.Entities.FaxNotificationsGenerator::.ctor()
0x467e  ret
0x467f  newobj   instance void Microsoft.Crm.Common.Application.Platform.Notifications.Entities.LetterNotificationsGenerator::.ctor()
0x4684  ret
0x4685  newobj   instance void Microsoft.Crm.Common.Application.Platform.Notifications.Entities.LetterNotificationsGenerator::.ctor()
0x468a  ret
0x468b  ldnull
0x468c  ret
```
