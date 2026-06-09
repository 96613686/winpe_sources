# _DataStoreServer::LoadXML_::_1_::dtor$17

- ea: `0x18000e7e2`
- end: `0x18000e7ee`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$17`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 96));
}

```

## disassembly

```asm
0x18000e7e2  lea     rcx, [rdx+60h]; this
0x18000e7e9  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
