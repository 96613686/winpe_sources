# _DataStoreServer::LoadXML_::_1_::dtor$11

- ea: `0x18000e818`
- end: `0x18000e824`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 144));
}

```

## disassembly

```asm
0x18000e818  lea     rcx, [rdx+90h]; this
0x18000e81f  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
