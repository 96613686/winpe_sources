# _ScheduleMigrator::DeleteSchedule_::_1_::dtor$4

- ea: `0x18001f5d3`
- end: `0x18001f5df`
- name: `_ScheduleMigrator::DeleteSchedule_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ab04`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::DeleteSchedule_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::array<std::wstring,2>::~array<std::wstring,2>(a2 + 80);
}

```

## disassembly

```asm
0x18001f5d3  lea     rcx, [rdx+50h]
0x18001f5da  jmp     ??1?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$01@std@@QEAA@XZ; std::array<std::wstring,2>::~array<std::wstring,2>(void)
```
