# __acrt_initialize_command_line

- ea: `0x18001a720`
- end: `0x18001a745`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x18001a724`
- `KERNEL32!GetCommandLineA` at `0x18001a724`
- `KERNEL32!GetCommandLineW` at `0x18001a731`
- `KERNEL32!GetCommandLineW` at `0x18001a731`

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
0x18001a720  sub     rsp, 28h
0x18001a724  call    cs:__imp_GetCommandLineA
0x18001a72a  mov     cs:_acmdln, rax
0x18001a731  call    cs:__imp_GetCommandLineW
0x18001a737  mov     cs:_wcmdln, rax
0x18001a73e  mov     al, 1
0x18001a740  add     rsp, 28h
0x18001a744  retn
```
