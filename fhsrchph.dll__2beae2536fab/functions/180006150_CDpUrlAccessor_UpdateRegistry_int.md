# CDpUrlAccessor::UpdateRegistry(int)

- ea: `0x180006150`
- end: `0x18000615d`
- name: `?UpdateRegistry@CDpUrlAccessor@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006164`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x65u, (int)a1, a4);
}

```

## disassembly

```asm
0x180006150  mov     r8d, ecx; int
0x180006153  mov     edx, 65h ; 'e'; unsigned int
0x180006158  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
