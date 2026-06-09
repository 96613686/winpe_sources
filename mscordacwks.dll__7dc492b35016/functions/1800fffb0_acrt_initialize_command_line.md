# __acrt_initialize_command_line

- ea: `0x1800fffb0`
- end: `0x1800fffd5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x1800fffb4`
- `KERNEL32!GetCommandLineA` at `0x1800fffb4`
- `KERNEL32!GetCommandLineW` at `0x1800fffc1`
- `KERNEL32!GetCommandLineW` at `0x1800fffc1`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  acmdln = GetCommandLineA();
  wcmdln = GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x1800fffb0  sub     rsp, 28h
0x1800fffb4  call    cs:__imp_GetCommandLineA
0x1800fffba  mov     cs:_acmdln, rax
0x1800fffc1  call    cs:__imp_GetCommandLineW
0x1800fffc7  mov     cs:_wcmdln, rax
0x1800fffce  mov     al, 1
0x1800fffd0  add     rsp, 28h
0x1800fffd4  retn
```
