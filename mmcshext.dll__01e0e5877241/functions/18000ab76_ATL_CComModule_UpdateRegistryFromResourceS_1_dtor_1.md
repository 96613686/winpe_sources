# _ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$1

- ea: `0x18000ab76`
- end: `0x18000ab82`
- name: `_ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002d4c`

## pseudocode

```c
void __fastcall ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)(a2 + 48));
}

```

## disassembly

```asm
0x18000ab76  lea     rcx, [rdx+30h]; this
0x18000ab7d  jmp     ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
```
