# _DataStoreServer::SetTemplates_::_1_::dtor$45

- ea: `0x18000ed43`
- end: `0x18000ed4f`
- name: `_DataStoreServer::SetTemplates_::_1_::dtor$45`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::SetTemplates_::_1_::dtor_45(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t(*(_bstr_t **)(a2 + 152));
}

```

## disassembly

```asm
0x18000ed43  mov     rcx, [rdx+98h]; this
0x18000ed4a  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
