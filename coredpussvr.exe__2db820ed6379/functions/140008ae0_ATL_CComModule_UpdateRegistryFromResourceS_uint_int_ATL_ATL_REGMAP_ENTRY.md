# ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140008ae0`
- end: `0x140008ae5`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@UEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `5`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140008460`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(this, a2, a3, a4);
}

```

## disassembly

```asm
0x140008ae0  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
