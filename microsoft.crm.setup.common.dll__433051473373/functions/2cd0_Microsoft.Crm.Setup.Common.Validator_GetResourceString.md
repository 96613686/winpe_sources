# Microsoft.Crm.Setup.Common.Validator::GetResourceString

- ea: `0x2cd0`
- end: `0x2cde`
- name: `Microsoft.Crm.Setup.Common.Validator::GetResourceString`
- size: `14`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ba0`
- `0x2df0`
- `0x32c0`
- `0x3630`
- `0x37b0`
- `0x3a90`
- `0x3bf0`
- `0x3d00`
- `0x4070`
- `0x4180`
- `0x4340`
- `0x4820`
- `0x48e0`

## pseudocode

```c

```

## disassembly

```asm
0x2cd0  ldarg.0
0x2cd1  ldfld    class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.Validator::resources
0x2cd6  ldarg.1
0x2cd7  ldarg.2
0x2cd8  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::GetResourceString(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager, string, object[])
0x2cdd  ret
```
