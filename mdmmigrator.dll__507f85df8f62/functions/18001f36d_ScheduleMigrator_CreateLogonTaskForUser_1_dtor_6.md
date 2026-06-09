# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$6

- ea: `0x18001f36d`
- end: `0x18001f379`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008124`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x18001f36d  lea     rcx, [rdx+58h]
0x18001f374  jmp     ??1?$CComPtr@UILogonTrigger@@@ATL@@QEAA@XZ; ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(void)
```
