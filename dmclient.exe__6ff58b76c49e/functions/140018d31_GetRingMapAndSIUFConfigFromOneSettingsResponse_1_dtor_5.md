# _GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$5

- ea: `0x140018d31`
- end: `0x140018d3d`
- name: `_GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004810`

## pseudocode

```c
void __fastcall GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 176));
}

```

## disassembly

```asm
0x140018d31  lea     rcx, [rdx+0B0h]; this
0x140018d38  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
