# _CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$0

- ea: `0x14001ddbe`
- end: `0x14001ddca`
- name: `_CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003194`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 184));
}

```

## disassembly

```asm
0x14001ddbe  lea     rcx, [rdx+0B8h]; this
0x14001ddc5  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
