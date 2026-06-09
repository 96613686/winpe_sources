# _CILogRead::DumpPage_::_1_::catch$1

- ea: `0x180012cf1`
- end: `0x180012d15`
- name: `_CILogRead::DumpPage_::_1_::catch$1`
- size: `36`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogRead::DumpPage_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 120) = *(_DWORD *)(a2 + 76);
  return 0;
}

```

## disassembly

```asm
0x180012cf1  mov     [rsp+arg_8], rdx
0x180012cf6  push    rbp
0x180012cf7  sub     rsp, 40h
0x180012cfb  mov     rbp, rdx
0x180012cfe  mov     eax, [rbp+4Ch]
0x180012d01  mov     [rbp+78h], eax
0x180012d04  mov     rax, 0
0x180012d0e  add     rsp, 40h
0x180012d12  pop     rbp
0x180012d13  retn
```
