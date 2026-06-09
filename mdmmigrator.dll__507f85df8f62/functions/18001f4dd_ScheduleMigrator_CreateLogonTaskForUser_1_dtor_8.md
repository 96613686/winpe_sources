# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$8

- ea: `0x18001f4dd`
- end: `0x18001f4e9`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008124`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>((__int64 *)(a2 + 80));
}

```

## disassembly

```asm
0x18001f4dd  lea     rcx, [rdx+50h]
0x18001f4e4  jmp     ??1?$CComPtr@UILogonTrigger@@@ATL@@QEAA@XZ; ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(void)
```
