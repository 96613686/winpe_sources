# _CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$4

- ea: `0x14001de06`
- end: `0x14001de12`
- name: `_CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140002e1c`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 88));
}

```

## disassembly

```asm
0x14001de06  mov     rcx, [rdx+58h]; void *
0x14001de0d  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
