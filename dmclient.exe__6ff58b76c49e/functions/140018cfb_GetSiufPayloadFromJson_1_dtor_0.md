# _GetSiufPayloadFromJson_::_1_::dtor$0

- ea: `0x140018cfb`
- end: `0x140018d07`
- name: `_GetSiufPayloadFromJson_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011be8`

## pseudocode

```c
void __fastcall GetSiufPayloadFromJson_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 80));
}

```

## disassembly

```asm
0x140018cfb  lea     rcx, [rdx+50h]; this
0x140018d02  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
