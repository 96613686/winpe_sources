# Microsoft.Crm.Setup.Common.Validator::.ctor_0

- ea: `0x2b80`
- end: `0x2b92`
- name: `Microsoft.Crm.Setup.Common.Validator::.ctor_0`
- size: `18`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2da0`
- `0x3ed0`
- `0x3ee0`
- `0x4010`
- `0x4030`
- `0x4320`
- `0x48c0`
- `0x4960`

## callees

- `0x1000`

## pseudocode

```c

```

## disassembly

```asm
0x2b80  ldarg.0
0x2b81  call     instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::.ctor()
0x2b86  ldarg.0
0x2b87  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.CommonResource::get_ResourceManager()
0x2b8c  stfld    class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.Validator::resources
0x2b91  ret
```
