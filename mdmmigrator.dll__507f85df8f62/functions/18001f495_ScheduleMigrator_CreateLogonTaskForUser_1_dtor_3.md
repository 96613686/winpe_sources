# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$3

- ea: `0x18001f495`
- end: `0x18001f4a1`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008124`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x18001f495  lea     rcx, [rdx+80h]
0x18001f49c  jmp     ??1?$CComPtr@UILogonTrigger@@@ATL@@QEAA@XZ; ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(void)
```
