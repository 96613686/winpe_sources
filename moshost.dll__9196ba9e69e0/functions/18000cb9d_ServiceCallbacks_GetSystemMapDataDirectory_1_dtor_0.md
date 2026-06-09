# _ServiceCallbacks::GetSystemMapDataDirectory_::_1_::dtor$0

- ea: `0x18000cb9d`
- end: `0x18000cba9`
- name: `_ServiceCallbacks::GetSystemMapDataDirectory_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094a4`

## pseudocode

```c
void __fastcall ServiceCallbacks::GetSystemMapDataDirectory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 32));
}

```

## disassembly

```asm
0x18000cb9d  lea     rcx, [rdx+20h]; this
0x18000cba4  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
