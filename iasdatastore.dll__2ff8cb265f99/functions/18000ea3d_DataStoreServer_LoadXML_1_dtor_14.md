# _DataStoreServer::LoadXML_::_1_::dtor$14

- ea: `0x18000ea3d`
- end: `0x18000ea49`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$14`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 136));
}

```

## disassembly

```asm
0x18000ea3d  lea     rcx, [rdx+88h]; this
0x18000ea44  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
