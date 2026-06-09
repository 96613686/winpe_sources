# _IsFeedbackHubAppInstalled_::_1_::dtor$2

- ea: `0x140019c3a`
- end: `0x140019c46`
- name: `_IsFeedbackHubAppInstalled_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004870`

## pseudocode

```c
void __fastcall IsFeedbackHubAppInstalled_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 72));
}

```

## disassembly

```asm
0x140019c3a  lea     rcx, [rdx+48h]; this
0x140019c41  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
