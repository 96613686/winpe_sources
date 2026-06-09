# _DataStoreServer::SetConfiguration_::_1_::dtor$17

- ea: `0x18000e70a`
- end: `0x18000e716`
- name: `_DataStoreServer::SetConfiguration_::_1_::dtor$17`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000774c`

## pseudocode

```c
void __fastcall DataStoreServer::SetConfiguration_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 64));
}

```

## disassembly

```asm
0x18000e70a  lea     rcx, [rdx+40h]; this
0x18000e711  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
