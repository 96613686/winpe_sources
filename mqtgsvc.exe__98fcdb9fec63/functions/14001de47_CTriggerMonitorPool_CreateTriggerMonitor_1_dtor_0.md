# _CTriggerMonitorPool::CreateTriggerMonitor_::_1_::dtor$0

- ea: `0x14001de47`
- end: `0x14001de53`
- name: `_CTriggerMonitorPool::CreateTriggerMonitor_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140002e1c`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateTriggerMonitor_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x14001de47  mov     rcx, [rdx+40h]; void *
0x14001de4e  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
