# _CFaxCommon::UpdateRegistry_::_1_::dtor$1

- ea: `0x180016205`
- end: `0x180016211`
- name: `_CFaxCommon::UpdateRegistry_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002058`

## pseudocode

```c
void __fastcall CFaxCommon::UpdateRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)(a2 + 48));
}

```

## disassembly

```asm
0x180016205  lea     rcx, [rdx+30h]; this
0x18001620c  jmp     ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
```
