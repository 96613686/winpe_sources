# _ScheduleMigrator::DeleteSchedule_::_1_::dtor$0

- ea: `0x18001f5af`
- end: `0x18001f5bb`
- name: `_ScheduleMigrator::DeleteSchedule_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ab5c`

## pseudocode

```c
void __fastcall ScheduleMigrator::DeleteSchedule_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoCoInitialize::~AutoCoInitialize((AutoCoInitialize *)(a2 + 56));
}

```

## disassembly

```asm
0x18001f5af  lea     rcx, [rdx+38h]; this
0x18001f5b6  jmp     ??1AutoCoInitialize@@QEAA@XZ; AutoCoInitialize::~AutoCoInitialize(void)
```
