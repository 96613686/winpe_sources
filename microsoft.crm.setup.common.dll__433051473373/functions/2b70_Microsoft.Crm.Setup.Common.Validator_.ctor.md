# Microsoft.Crm.Setup.Common.Validator::.ctor

- ea: `0x2b70`
- end: `0x2b7e`
- name: `Microsoft.Crm.Setup.Common.Validator::.ctor`
- size: `14`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2dc0`
- `0x2de0`
- `0x3290`
- `0x32b0`
- `0x35e0`
- `0x3610`
- `0x3780`
- `0x37a0`
- `0x3a60`
- `0x3a80`
- `0x3be0`
- `0x3cf0`

## pseudocode

```c

```

## disassembly

```asm
0x2b70  ldarg.0
0x2b71  call     instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::.ctor()
0x2b76  ldarg.0
0x2b77  ldarg.1
0x2b78  stfld    class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.Validator::resources
0x2b7d  ret
```
