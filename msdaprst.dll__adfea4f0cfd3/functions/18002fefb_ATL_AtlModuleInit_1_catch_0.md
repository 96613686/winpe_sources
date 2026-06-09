# _ATL::AtlModuleInit_::_1_::catch$0

- ea: `0x18002fefb`
- end: `0x18002ff40`
- name: `_ATL::AtlModuleInit_::_1_::catch$0`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002ff0f`
- `MSDART!MPDeleteCriticalSection` at `0x18002ff22`
- `MSDART!MPDeleteCriticalSection` at `0x18002ff0f`
- `MSDART!MPDeleteCriticalSection` at `0x18002ff22`

## pseudocode

```c
__int64 ATL::AtlModuleInit_::_1_::catch_0()
{
  MPDeleteCriticalSection(&qword_1800464F8);
  MPDeleteCriticalSection(&qword_180046500);
  return 0;
}

```

## disassembly

```asm
0x18002fefb  mov     [rsp+arg_8], rdx
0x18002ff00  push    rbp
0x18002ff01  sub     rsp, 20h
0x18002ff05  mov     rbp, rdx
0x18002ff08  lea     rcx, qword_1800464F8
0x18002ff0f  call    cs:__imp_MPDeleteCriticalSection
0x18002ff16  nop     dword ptr [rax+rax+00h]
0x18002ff1b  lea     rcx, qword_180046500
0x18002ff22  call    cs:__imp_MPDeleteCriticalSection
0x18002ff29  nop     dword ptr [rax+rax+00h]
0x18002ff2e  nop
0x18002ff2f  mov     rax, 0
0x18002ff39  add     rsp, 20h
0x18002ff3d  pop     rbp
0x18002ff3e  retn
```
