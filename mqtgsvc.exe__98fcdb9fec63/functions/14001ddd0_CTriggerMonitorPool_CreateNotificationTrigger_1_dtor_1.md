# _CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$1

- ea: `0x14001ddd0`
- end: `0x14001dddc`
- name: `_CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003194`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 88));
}

```

## disassembly

```asm
0x14001ddd0  lea     rcx, [rdx+58h]; this
0x14001ddd7  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
