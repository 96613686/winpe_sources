# CAccServerDocMgr::UpdateRegistry(int)

- ea: `0x1800122a0`
- end: `0x1800122ad`
- name: `?UpdateRegistry@CAccServerDocMgr@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180012314`

## pseudocode

```c
__int64 __fastcall CAccServerDocMgr::UpdateRegistry(
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
0x1800122a0  mov     r8d, ecx; int
0x1800122a3  mov     edx, 66h ; 'f'; unsigned int
0x1800122a8  jmp     ?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
