# Microsoft.Crm.Transformations.ResourceProvider::GetString

- ea: `0x2740`
- end: `0x2751`
- name: `Microsoft.Crm.Transformations.ResourceProvider::GetString`
- size: `17`
- prototype: ``
- caller_count: `63`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10`
- `0x20`
- `0x60`
- `0x200`
- `0x240`
- `0x280`
- `0x2d0`
- `0x3c0`
- `0x420`
- `0x430`
- `0x490`
- `0x920`
- `0x960`
- `0x9a0`
- `0x9e0`
- `0xa20`
- `0xa60`
- `0xaa0`
- `0xaf0`
- `0xcf0`
- `0xd00`
- `0xd50`
- `0x10a0`
- `0x10e0`
- `0x1120`
- `0x1160`
- `0x11a0`
- `0x11e0`
- `0x1240`
- `0x1250`
- `0x12c0`
- `0x1960`
- `0x19a0`
- `0x19f0`
- `0x1a30`
- `0x1a80`
- `0x1ac0`
- `0x1b10`
- `0x1b50`
- `0x1b90`
- `0x1bd0`
- `0x1c80`
- `0x1c90`
- `0x1ca0`
- `0x1ce0`
- `0x1db0`
- `0x1dc0`
- `0x1e00`
- `0x1f80`
- `0x1fc0`

## callees

- `0x2730`

## pseudocode

```c

```

## disassembly

```asm
0x2740  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Transformations.ResourceProvider::GetResourceManager()
0x2745  ldarg.0
0x2746  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x274b  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2750  ret
```
