# _CreateNewResultPair_::_1_::catch$6

- ea: `0x14000c7c1`
- end: `0x14000c7e6`
- name: `_CreateNewResultPair_::_1_::catch$6`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CreateNewResultPair_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14000c7c1  mov     [rsp+arg_8], rdx
0x14000c7c6  push    rbp
0x14000c7c7  sub     rsp, 20h
0x14000c7cb  mov     rbp, rdx
0x14000c7ce  mov     dword ptr [rbp+60h], 8007000Eh
0x14000c7d5  mov     rax, 0
0x14000c7df  add     rsp, 20h
0x14000c7e3  pop     rbp
0x14000c7e4  retn
```
