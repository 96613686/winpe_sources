# _DataStoreServer::LoadXML_::_1_::dtor$3

- ea: `0x18000e7f4`
- end: `0x18000e800`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 160));
}

```

## disassembly

```asm
0x18000e7f4  lea     rcx, [rdx+0A0h]; this
0x18000e7fb  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
