# _CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$3

- ea: `0x14001ddf4`
- end: `0x14001de00`
- name: `_CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003194`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 176));
}

```

## disassembly

```asm
0x14001ddf4  lea     rcx, [rdx+0B0h]; this
0x14001ddfb  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
