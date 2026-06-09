# ATL::CComModule::UpdateRegistryFromResourceD(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000ffe0`
- end: `0x18000ffe6`
- name: `?UpdateRegistryFromResourceD@CComModule@ATL@@UEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `6`
- prototype: `__int64 __fastcall(ATL::CComModule *this, const wchar_t *, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceD(
        ATL::CComModule *this,
        const wchar_t *a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000ffe0  mov     eax, 80004005h
0x18000ffe5  retn
```
