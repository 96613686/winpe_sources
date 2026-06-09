# _ATL::AtlModuleInit_::_1_::catch$0

- ea: `0x1800cf4f8`
- end: `0x1800cf53d`
- name: `_ATL::AtlModuleInit_::_1_::catch$0`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x1800cf50c`
- `MSDART!MPDeleteCriticalSection` at `0x1800cf51f`
- `MSDART!MPDeleteCriticalSection` at `0x1800cf50c`
- `MSDART!MPDeleteCriticalSection` at `0x1800cf51f`

## pseudocode

```c
__int64 ATL::AtlModuleInit_::_1_::catch_0()
{
  MPDeleteCriticalSection(&qword_180122C98);
  MPDeleteCriticalSection(&qword_180122CA0);
  return 0;
}

```

## disassembly

```asm
0x1800cf4f8  mov     [rsp+arg_8], rdx
0x1800cf4fd  push    rbp
0x1800cf4fe  sub     rsp, 20h
0x1800cf502  mov     rbp, rdx
0x1800cf505  lea     rcx, qword_180122C98
0x1800cf50c  call    cs:__imp_MPDeleteCriticalSection
0x1800cf513  nop     dword ptr [rax+rax+00h]
0x1800cf518  lea     rcx, qword_180122CA0
0x1800cf51f  call    cs:__imp_MPDeleteCriticalSection
0x1800cf526  nop     dword ptr [rax+rax+00h]
0x1800cf52b  nop
0x1800cf52c  mov     rax, 0
0x1800cf536  add     rsp, 20h
0x1800cf53a  pop     rbp
0x1800cf53b  retn
```
