# _ScheduleBackOffRetryTask_::_1_::dtor$0

- ea: `0x140015e7f`
- end: `0x140015e8b`
- name: `_ScheduleBackOffRetryTask_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000edb4`

## pseudocode

```c
__int64 __fastcall ScheduleBackOffRetryTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 184);
}

```

## disassembly

```asm
0x140015e7f  lea     rcx, [rdx+0B8h]
0x140015e86  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
