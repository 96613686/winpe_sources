# _CILogRead::GetCurrentLogRecord_::_1_::catch$0

- ea: `0x180012d1b`
- end: `0x180012d4c`
- name: `_CILogRead::GetCurrentLogRecord_::_1_::catch$0`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogRead::GetCurrentLogRecord_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a2 + 32);
  if ( v2 == -1073741819 )
    v2 = -2147024809;
  *(_DWORD *)(a2 + 120) = v2;
  return 0;
}

```

## disassembly

```asm
0x180012d1b  mov     [rsp+arg_8], rdx
0x180012d20  push    rbp
0x180012d21  sub     rsp, 20h
0x180012d25  mov     rbp, rdx
0x180012d28  mov     eax, [rbp+20h]
0x180012d2b  mov     ecx, 80070057h
0x180012d30  cmp     eax, 0C0000005h
0x180012d35  cmovz   eax, ecx
0x180012d38  mov     [rbp+78h], eax
0x180012d3b  mov     rax, 0
0x180012d45  add     rsp, 20h
0x180012d49  pop     rbp
0x180012d4a  retn
```
