# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$2

- ea: `0x18001f483`
- end: `0x18001f48f`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008124`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18001f483  lea     rcx, [rdx+60h]
0x18001f48a  jmp     ??1?$CComPtr@UILogonTrigger@@@ATL@@QEAA@XZ; ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(void)
```
