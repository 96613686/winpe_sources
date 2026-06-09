# _DataStoreServer::SetTemplates_::_1_::dtor$15

- ea: `0x18000ed31`
- end: `0x18000ed3d`
- name: `_DataStoreServer::SetTemplates_::_1_::dtor$15`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000774c`

## pseudocode

```c
void __fastcall DataStoreServer::SetTemplates_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 72));
}

```

## disassembly

```asm
0x18000ed31  lea     rcx, [rdx+48h]; this
0x18000ed38  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
