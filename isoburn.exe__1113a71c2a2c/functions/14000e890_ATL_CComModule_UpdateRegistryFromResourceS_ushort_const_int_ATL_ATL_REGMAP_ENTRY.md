# ATL::CComModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000e890`
- end: `0x14000e895`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@UEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `5`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000e534`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(this, a2, a3, a4);
}

```

## disassembly

```asm
0x14000e890  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)
```
