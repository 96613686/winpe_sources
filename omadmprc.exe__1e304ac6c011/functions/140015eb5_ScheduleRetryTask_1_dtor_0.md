# _ScheduleRetryTask_::_1_::dtor$0

- ea: `0x140015eb5`
- end: `0x140015ec1`
- name: `_ScheduleRetryTask_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000edb4`

## pseudocode

```c
__int64 __fastcall ScheduleRetryTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 88);
}

```

## disassembly

```asm
0x140015eb5  lea     rcx, [rdx+58h]
0x140015ebc  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
