# _DataStoreServer::SetConfiguration_::_1_::dtor$51

- ea: `0x18000ec98`
- end: `0x18000eca4`
- name: `_DataStoreServer::SetConfiguration_::_1_::dtor$51`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall DataStoreServer::SetConfiguration_::_1_::dtor_51(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t(*(_bstr_t **)(a2 + 160));
}

```

## disassembly

```asm
0x18000ec98  mov     rcx, [rdx+0A0h]; this
0x18000ec9f  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
