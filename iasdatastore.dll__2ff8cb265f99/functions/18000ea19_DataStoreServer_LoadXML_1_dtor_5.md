# _DataStoreServer::LoadXML_::_1_::dtor$5

- ea: `0x18000ea19`
- end: `0x18000ea25`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 112));
}

```

## disassembly

```asm
0x18000ea19  lea     rcx, [rdx+70h]; this
0x18000ea20  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
