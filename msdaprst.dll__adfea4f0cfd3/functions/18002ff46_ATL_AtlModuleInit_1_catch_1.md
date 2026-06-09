# _ATL::AtlModuleInit_::_1_::catch$1

- ea: `0x18002ff46`
- end: `0x18002ff78`
- name: `_ATL::AtlModuleInit_::_1_::catch$1`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002ff5a`
- `MSDART!MPDeleteCriticalSection` at `0x18002ff5a`

## pseudocode

```c
__int64 ATL::AtlModuleInit_::_1_::catch_1()
{
  MPDeleteCriticalSection(&qword_1800464F8);
  return 0;
}

```

## disassembly

```asm
0x18002ff46  mov     [rsp+arg_8], rdx
0x18002ff4b  push    rbp
0x18002ff4c  sub     rsp, 20h
0x18002ff50  mov     rbp, rdx
0x18002ff53  lea     rcx, qword_1800464F8
0x18002ff5a  call    cs:__imp_MPDeleteCriticalSection
0x18002ff61  nop     dword ptr [rax+rax+00h]
0x18002ff66  nop
0x18002ff67  mov     rax, 0
0x18002ff71  add     rsp, 20h
0x18002ff75  pop     rbp
0x18002ff76  retn
```
