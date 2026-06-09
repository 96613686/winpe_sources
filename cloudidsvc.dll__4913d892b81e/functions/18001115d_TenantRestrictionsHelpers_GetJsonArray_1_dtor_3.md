# _TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor$3

- ea: `0x18001115d`
- end: `0x180011169`
- name: `_TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ded0`

## pseudocode

```c
void __fastcall TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 64));
}

```

## disassembly

```asm
0x18001115d  lea     rcx, [rdx+40h]; this
0x180011164  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
