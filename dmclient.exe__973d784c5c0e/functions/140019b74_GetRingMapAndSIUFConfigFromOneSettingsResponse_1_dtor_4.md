# _GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$4

- ea: `0x140019b74`
- end: `0x140019b80`
- name: `_GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140012474`

## pseudocode

```c
void __fastcall GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 96));
}

```

## disassembly

```asm
0x140019b74  lea     rcx, [rdx+60h]; this
0x140019b7b  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
