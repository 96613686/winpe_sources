# _DataStoreServer::LoadXML_::_1_::dtor$2

- ea: `0x18000ea07`
- end: `0x18000ea13`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 120));
}

```

## disassembly

```asm
0x18000ea07  lea     rcx, [rdx+78h]; this
0x18000ea0e  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
