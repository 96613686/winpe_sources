# __acrt_initialize_command_line

- ea: `0x140151ba0`
- end: `0x140151bc5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x140151ba4`
- `KERNEL32!GetCommandLineA` at `0x140151ba4`
- `KERNEL32!GetCommandLineW` at `0x140151bb1`
- `KERNEL32!GetCommandLineW` at `0x140151bb1`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  qword_14038C9F8 = (__int64)GetCommandLineA();
  qword_14038CA00 = (__int64)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x140151ba0  sub     rsp, 28h
0x140151ba4  call    cs:GetCommandLineA
0x140151baa  mov     cs:qword_14038C9F8, rax
0x140151bb1  call    cs:GetCommandLineW
0x140151bb7  mov     cs:qword_14038CA00, rax
0x140151bbe  mov     al, 1
0x140151bc0  add     rsp, 28h
0x140151bc4  retn
```
