# _CProviderImpersonation::Create_::_1_::catch$0

- ea: `0x14001b159`
- end: `0x14001b17e`
- name: `_CProviderImpersonation::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CProviderImpersonation::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001b159  mov     [rsp+arg_8], rdx
0x14001b15e  push    rbp
0x14001b15f  sub     rsp, 20h
0x14001b163  mov     rbp, rdx
0x14001b166  mov     dword ptr [rbp+40h], 8007000Eh
0x14001b16d  mov     rax, 0
0x14001b177  add     rsp, 20h
0x14001b17b  pop     rbp
0x14001b17c  retn
```
