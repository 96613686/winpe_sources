# _CILogRead::GetCurrentLogRecord_::_1_::catch$1

- ea: `0x180012d52`
- end: `0x180012d83`
- name: `_CILogRead::GetCurrentLogRecord_::_1_::catch$1`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogRead::GetCurrentLogRecord_::_1_::catch_1(__int64 a1, __int64 a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a2 + 36);
  if ( v2 == -1073741819 )
    v2 = -2147024809;
  *(_DWORD *)(a2 + 120) = v2;
  return 0;
}

```

## disassembly

```asm
0x180012d52  mov     [rsp+arg_8], rdx
0x180012d57  push    rbp
0x180012d58  sub     rsp, 20h
0x180012d5c  mov     rbp, rdx
0x180012d5f  mov     eax, [rbp+24h]
0x180012d62  mov     ecx, 80070057h
0x180012d67  cmp     eax, 0C0000005h
0x180012d6c  cmovz   eax, ecx
0x180012d6f  mov     [rbp+78h], eax
0x180012d72  mov     rax, 0
0x180012d7c  add     rsp, 20h
0x180012d80  pop     rbp
0x180012d81  retn
```
