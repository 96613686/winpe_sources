# _DataStoreServer::LoadXML_::_1_::dtor$18

- ea: `0x18000ea61`
- end: `0x18000ea6d`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$18`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_18(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t(*(_bstr_t **)(a2 + 120));
}

```

## disassembly

```asm
0x18000ea61  mov     rcx, [rdx+78h]; this
0x18000ea68  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
