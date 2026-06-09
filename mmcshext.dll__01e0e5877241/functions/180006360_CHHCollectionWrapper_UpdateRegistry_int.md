# CHHCollectionWrapper::UpdateRegistry(int)

- ea: `0x180006360`
- end: `0x18000636d`
- name: `?UpdateRegistry@CHHCollectionWrapper@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006374`

## pseudocode

```c
__int64 __fastcall CHHCollectionWrapper::UpdateRegistry(
        ATL::CComModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CComModule::UpdateRegistryFromResourceS(a1, 0x66u, (int)a1, a4);
}

```

## disassembly

```asm
0x180006360  mov     r8d, ecx; int
0x180006363  mov     edx, 66h ; 'f'; unsigned int
0x180006368  jmp     ?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
