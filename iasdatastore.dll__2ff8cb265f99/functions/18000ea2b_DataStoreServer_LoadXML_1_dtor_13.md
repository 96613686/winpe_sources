# _DataStoreServer::LoadXML_::_1_::dtor$13

- ea: `0x18000ea2b`
- end: `0x18000ea37`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$13`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000774c`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 168));
}

```

## disassembly

```asm
0x18000ea2b  lea     rcx, [rdx+0A8h]; this
0x18000ea32  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
