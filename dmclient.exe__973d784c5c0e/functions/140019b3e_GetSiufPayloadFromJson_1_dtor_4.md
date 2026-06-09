# _GetSiufPayloadFromJson_::_1_::dtor$4

- ea: `0x140019b3e`
- end: `0x140019b4a`
- name: `_GetSiufPayloadFromJson_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004870`

## pseudocode

```c
void __fastcall GetSiufPayloadFromJson_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 128));
}

```

## disassembly

```asm
0x140019b3e  lea     rcx, [rdx+80h]; this
0x140019b45  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
