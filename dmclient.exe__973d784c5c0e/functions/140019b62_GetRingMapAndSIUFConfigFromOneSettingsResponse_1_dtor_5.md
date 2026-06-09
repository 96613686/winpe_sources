# _GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$5

- ea: `0x140019b62`
- end: `0x140019b6e`
- name: `_GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004870`

## pseudocode

```c
void __fastcall GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 176));
}

```

## disassembly

```asm
0x140019b62  lea     rcx, [rdx+0B0h]; this
0x140019b69  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
