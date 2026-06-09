# CDpSearchProtocol::UpdateRegistry(int)

- ea: `0x180006130`
- end: `0x18000613d`
- name: `?UpdateRegistry@CDpSearchProtocol@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006164`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x64u, (int)a1, a4);
}

```

## disassembly

```asm
0x180006130  mov     r8d, ecx; int
0x180006133  mov     edx, 64h ; 'd'; unsigned int
0x180006138  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
