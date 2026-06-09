# _ServiceManager_EnsureInstance_::_1_::dtor$0

- ea: `0x18000cc0f`
- end: `0x18000cc1b`
- name: `_ServiceManager_EnsureInstance_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a320`

## pseudocode

```c
void __fastcall ServiceManager_EnsureInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(a2 + 32);
}

```

## disassembly

```asm
0x18000cc0f  lea     rcx, [rdx+20h]
0x18000cc16  jmp     ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
```
