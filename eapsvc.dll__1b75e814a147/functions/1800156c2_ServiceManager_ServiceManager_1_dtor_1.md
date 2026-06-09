# _ServiceManager::ServiceManager_::_1_::dtor$1

- ea: `0x1800156c2`
- end: `0x1800156d2`
- name: `_ServiceManager::ServiceManager_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000aac4`

## pseudocode

```c
void __fastcall ServiceManager::ServiceManager_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Event::~Event((Event *)(*(_QWORD *)(a2 + 80) + 88LL));
}

```

## disassembly

```asm
0x1800156c2  mov     rcx, [rdx+50h]
0x1800156c9  add     rcx, 58h ; 'X'; this
0x1800156cd  jmp     ??1Event@@UEAA@XZ
```
