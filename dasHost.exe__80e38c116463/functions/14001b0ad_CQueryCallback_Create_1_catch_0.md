# _CQueryCallback::Create_::_1_::catch$0

- ea: `0x14001b0ad`
- end: `0x14001b0d2`
- name: `_CQueryCallback::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CQueryCallback::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 120) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001b0ad  mov     [rsp+arg_8], rdx
0x14001b0b2  push    rbp
0x14001b0b3  sub     rsp, 20h
0x14001b0b7  mov     rbp, rdx
0x14001b0ba  mov     dword ptr [rbp+78h], 8007000Eh
0x14001b0c1  mov     rax, 0
0x14001b0cb  add     rsp, 20h
0x14001b0cf  pop     rbp
0x14001b0d0  retn
```
