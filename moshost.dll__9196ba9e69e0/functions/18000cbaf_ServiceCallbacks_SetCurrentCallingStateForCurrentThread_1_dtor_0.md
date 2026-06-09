# _ServiceCallbacks::SetCurrentCallingStateForCurrentThread_::_1_::dtor$0

- ea: `0x18000cbaf`
- end: `0x18000cbbb`
- name: `_ServiceCallbacks::SetCurrentCallingStateForCurrentThread_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094cc`

## pseudocode

```c
void __fastcall ServiceCallbacks::SetCurrentCallingStateForCurrentThread_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)(a2 + 144));
}

```

## disassembly

```asm
0x18000cbaf  lea     rcx, [rdx+90h]; this
0x18000cbb6  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
