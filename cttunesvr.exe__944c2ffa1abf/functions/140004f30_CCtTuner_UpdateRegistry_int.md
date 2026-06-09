# CCtTuner::UpdateRegistry(int)

- ea: `0x140004f30`
- end: `0x140004f3f`
- name: `?UpdateRegistry@CCtTuner@@SAJH@Z`
- size: `15`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x140004f48`

## pseudocode

```c
__int64 __fastcall CCtTuner::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x66u, (int)a1, 0);
}

```

## disassembly

```asm
0x140004f30  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x140004f33  mov     r8d, ecx; int
0x140004f36  lea     edx, [r9+66h]; unsigned int
0x140004f3a  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
