# _ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$1

- ea: `0x180013a77`
- end: `0x180013a83`
- name: `_ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000e18c`

## pseudocode

```c
void __fastcall ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)(a2 + 48));
}

```

## disassembly

```asm
0x180013a77  lea     rcx, [rdx+30h]; this
0x180013a7e  jmp     ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
```
