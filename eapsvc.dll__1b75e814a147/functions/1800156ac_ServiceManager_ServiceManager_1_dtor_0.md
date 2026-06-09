# _ServiceManager::ServiceManager_::_1_::dtor$0

- ea: `0x1800156ac`
- end: `0x1800156bc`
- name: `_ServiceManager::ServiceManager_::_1_::dtor$0`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000e17c`

## pseudocode

```c
__int64 __fastcall ServiceManager::ServiceManager_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Serializable<CriticalSection>::~Serializable<CriticalSection>(*(_QWORD *)(a2 + 80) + 8LL);
}

```

## disassembly

```asm
0x1800156ac  mov     rcx, [rdx+50h]
0x1800156b3  add     rcx, 8
0x1800156b7  jmp     ??1?$Serializable@VCriticalSection@@@@QEAA@XZ
```
