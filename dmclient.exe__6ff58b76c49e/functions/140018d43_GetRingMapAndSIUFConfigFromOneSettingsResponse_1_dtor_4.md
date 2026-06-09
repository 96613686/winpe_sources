# _GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$4

- ea: `0x140018d43`
- end: `0x140018d4f`
- name: `_GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011be8`

## pseudocode

```c
void __fastcall GetRingMapAndSIUFConfigFromOneSettingsResponse_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 96));
}

```

## disassembly

```asm
0x140018d43  lea     rcx, [rdx+60h]; this
0x140018d4a  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
