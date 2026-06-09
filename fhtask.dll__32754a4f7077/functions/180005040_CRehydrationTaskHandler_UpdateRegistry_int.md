# CRehydrationTaskHandler::UpdateRegistry(int)

- ea: `0x180005040`
- end: `0x18000504d`
- name: `?UpdateRegistry@CRehydrationTaskHandler@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180005074`

## pseudocode

```c
__int64 __fastcall CRehydrationTaskHandler::UpdateRegistry(
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
0x180005040  mov     r8d, ecx; int
0x180005043  mov     edx, 65h ; 'e'; unsigned int
0x180005048  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
