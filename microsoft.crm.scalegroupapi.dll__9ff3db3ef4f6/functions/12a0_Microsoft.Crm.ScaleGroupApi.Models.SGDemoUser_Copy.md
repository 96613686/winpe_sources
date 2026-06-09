# Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::Copy

- ea: `0x12a0`
- end: `0x12d6`
- name: `Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::Copy`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1230`
- `0x1250`
- `0x1270`
- `0x1290`
- `0x12e0`

## pseudocode

```c

```

## disassembly

```asm
0x12a0  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::.ctor()
0x12a5  dup
0x12a6  ldarg.0
0x12a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_SystemUserId()
0x12ac  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::set_CrmUserId(valuetype [mscorlib]System.Guid value)
0x12b1  dup
0x12b2  ldarg.0
0x12b3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_DomainName()
0x12b8  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::set_DomainName(string value)
0x12bd  dup
0x12be  ldarg.0
0x12bf  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_Scenario()
0x12c4  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::set_Scenario(string value)
0x12c9  dup
0x12ca  ldarg.0
0x12cb  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_Number()
0x12d0  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::set_Number(int32 value)
0x12d5  ret
```
