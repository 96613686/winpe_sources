# _GetSiufPayloadFromJson_::_1_::dtor$0

- ea: `0x140019b2c`
- end: `0x140019b38`
- name: `_GetSiufPayloadFromJson_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140012474`

## pseudocode

```c
void __fastcall GetSiufPayloadFromJson_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 80));
}

```

## disassembly

```asm
0x140019b2c  lea     rcx, [rdx+50h]; this
0x140019b33  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
