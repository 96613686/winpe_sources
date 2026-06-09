# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$0

- ea: `0x18001f45f`
- end: `0x18001f46b`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ab5c`

## pseudocode

```c
void __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoCoInitialize::~AutoCoInitialize((AutoCoInitialize *)(a2 + 144));
}

```

## disassembly

```asm
0x18001f45f  lea     rcx, [rdx+90h]; this
0x18001f466  jmp     ??1AutoCoInitialize@@QEAA@XZ; AutoCoInitialize::~AutoCoInitialize(void)
```
