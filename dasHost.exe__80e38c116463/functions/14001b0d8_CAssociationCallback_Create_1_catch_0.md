# _CAssociationCallback::Create_::_1_::catch$0

- ea: `0x14001b0d8`
- end: `0x14001b0fd`
- name: `_CAssociationCallback::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CAssociationCallback::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x14001b0d8  mov     [rsp+arg_8], rdx
0x14001b0dd  push    rbp
0x14001b0de  sub     rsp, 20h
0x14001b0e2  mov     rbp, rdx
0x14001b0e5  mov     dword ptr [rbp+70h], 80004005h
0x14001b0ec  mov     rax, 0
0x14001b0f6  add     rsp, 20h
0x14001b0fa  pop     rbp
0x14001b0fb  retn
```
