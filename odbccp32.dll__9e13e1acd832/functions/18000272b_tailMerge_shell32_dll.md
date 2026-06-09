# __tailMerge_shell32_dll

- ea: `0x18000272b`
- end: `0x1800027a4`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027aa`
- `0x1800027bc`
- `0x1800027ce`
- `0x1800027e0`
- `0x18000288f`

## callees

- `0x18000272b`
- `0x1800149c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000272b  mov     [rsp+arg_0], rcx
0x180002730  mov     [rsp+arg_8], rdx
0x180002735  mov     [rsp+arg_10], r8
0x18000273a  mov     [rsp+arg_18], r9
0x18000273f  sub     rsp, 68h
0x180002743  movdqa  [rsp+68h+var_48], xmm0
0x180002749  movdqa  [rsp+68h+var_38], xmm1
0x18000274f  movdqa  [rsp+68h+var_28], xmm2
0x180002755  movdqa  [rsp+68h+var_18], xmm3
0x18000275b  mov     rdx, rax
0x18000275e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x180002765  call    __delayLoadHelper2
0x18000276a  movdqa  xmm0, [rsp+68h+var_48]
0x180002770  movdqa  xmm1, [rsp+68h+var_38]
0x180002776  movdqa  xmm2, [rsp+68h+var_28]
0x18000277c  movdqa  xmm3, [rsp+68h+var_18]
0x180002782  mov     rcx, [rsp+68h+arg_0]
0x180002787  mov     rdx, [rsp+68h+arg_8]
0x18000278c  mov     r8, [rsp+68h+arg_10]
0x180002794  mov     r9, [rsp+68h+arg_18]
0x18000279c  add     rsp, 68h
0x1800027a0  jmp     short $+2
0x1800027a2  jmp     rax
```
