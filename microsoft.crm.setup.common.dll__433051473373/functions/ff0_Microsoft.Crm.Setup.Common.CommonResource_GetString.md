# Microsoft.Crm.Setup.Common.CommonResource::GetString

- ea: `0xff0`
- end: `0xffd`
- name: `Microsoft.Crm.Setup.Common.CommonResource::GetString`
- size: `13`
- prototype: ``
- caller_count: `30`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1540`
- `0x1780`
- `0x17c0`
- `0x17f0`
- `0x19b0`
- `0x1a20`
- `0x1ae0`
- `0x1b30`
- `0x1c90`
- `0x1f10`
- `0x2740`
- `0x2850`
- `0x2d40`
- `0x5330`
- `0x5790`
- `0x6c30`
- `0x80a0`
- `0x84c0`
- `0x99c0`
- `0x9ae0`
- `0x9c70`
- `0xb210`
- `0xbdb0`
- `0xbdf0`
- `0xc3e0`
- `0xfe20`
- `0x11900`
- `0x11ce0`
- `0x12ec0`
- `0x12f20`

## pseudocode

```c

```

## disassembly

```asm
0xff0  ldsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.CommonResource::resourceManager
0xff5  ldarg.0
0xff6  ldarg.1
0xff7  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::GetResourceString(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager, string, object[])
0xffc  ret
```
