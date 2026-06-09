# _CAssociationReadCallback::Create_::_1_::catch$0

- ea: `0x14001b082`
- end: `0x14001b0a7`
- name: `_CAssociationReadCallback::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CAssociationReadCallback::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 88) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001b082  mov     [rsp+arg_8], rdx
0x14001b087  push    rbp
0x14001b088  sub     rsp, 20h
0x14001b08c  mov     rbp, rdx
0x14001b08f  mov     dword ptr [rbp+58h], 8007000Eh
0x14001b096  mov     rax, 0
0x14001b0a0  add     rsp, 20h
0x14001b0a4  pop     rbp
0x14001b0a5  retn
```
