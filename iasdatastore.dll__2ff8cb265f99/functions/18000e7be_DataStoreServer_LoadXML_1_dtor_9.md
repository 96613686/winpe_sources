# _DataStoreServer::LoadXML_::_1_::dtor$9

- ea: `0x18000e7be`
- end: `0x18000e7ca`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 104));
}

```

## disassembly

```asm
0x18000e7be  lea     rcx, [rdx+68h]; this
0x18000e7c5  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
