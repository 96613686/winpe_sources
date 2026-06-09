# Microsoft.Crm.ScaleGroupApi.Controllers.DemoUserController::RetrieveUserInfo

- ea: `0x2c30`
- end: `0x2c52`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.DemoUserController::RetrieveUserInfo`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2b50`
- `0x2b60`

## pseudocode

```c

```

## disassembly

```asm
0x2c30  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::.ctor()
0x2c35  ldarg.0
0x2c36  call     instance class [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo[] [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::GetAllDemoUsers(valuetype [mscorlib]System.Guid)
0x2c3b  ldnull
0x2c3c  ldftn    class Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser::Copy(class [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo userInfo)
0x2c42  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo, class Microsoft.Crm.ScaleGroupApi.Models.SGDemoUser>::.ctor(object, native int)
0x2c47  call     T0x2B000010
0x2c4c  call     T0x2B000011
0x2c51  ret
```
