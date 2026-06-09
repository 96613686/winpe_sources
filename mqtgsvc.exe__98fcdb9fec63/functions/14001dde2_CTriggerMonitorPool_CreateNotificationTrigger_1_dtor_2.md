# _CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$2

- ea: `0x14001dde2`
- end: `0x14001ddee`
- name: `_CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003194`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 168));
}

```

## disassembly

```asm
0x14001dde2  lea     rcx, [rdx+0A8h]; this
0x14001dde9  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
