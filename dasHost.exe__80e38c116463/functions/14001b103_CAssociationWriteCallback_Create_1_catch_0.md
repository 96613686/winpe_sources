# _CAssociationWriteCallback::Create_::_1_::catch$0

- ea: `0x14001b103`
- end: `0x14001b128`
- name: `_CAssociationWriteCallback::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CAssociationWriteCallback::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 88) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x14001b103  mov     [rsp+arg_8], rdx
0x14001b108  push    rbp
0x14001b109  sub     rsp, 20h
0x14001b10d  mov     rbp, rdx
0x14001b110  mov     dword ptr [rbp+58h], 80004005h
0x14001b117  mov     rax, 0
0x14001b121  add     rsp, 20h
0x14001b125  pop     rbp
0x14001b126  retn
```
