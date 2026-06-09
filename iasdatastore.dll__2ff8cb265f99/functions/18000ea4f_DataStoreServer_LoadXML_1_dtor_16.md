# _DataStoreServer::LoadXML_::_1_::dtor$16

- ea: `0x18000ea4f`
- end: `0x18000ea5b`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$16`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 128));
}

```

## disassembly

```asm
0x18000ea4f  lea     rcx, [rdx+80h]; this
0x18000ea56  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
