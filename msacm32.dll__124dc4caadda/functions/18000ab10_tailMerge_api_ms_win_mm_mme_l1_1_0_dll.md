# __tailMerge_api_ms_win_mm_mme_l1_1_0_dll

- ea: `0x18000ab10`
- end: `0x18000ab89`
- name: `__tailMerge_api_ms_win_mm_mme_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ab8f`
- `0x18000aba1`
- `0x18000abb3`
- `0x18000abc5`
- `0x18000abd7`
- `0x18000abe9`

## callees

- `0x180007cb0`
- `0x18000ab10`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_mm_mme_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_mme_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ab10  mov     [rsp+arg_0], rcx
0x18000ab15  mov     [rsp+arg_8], rdx
0x18000ab1a  mov     [rsp+arg_10], r8
0x18000ab1f  mov     [rsp+arg_18], r9
0x18000ab24  sub     rsp, 68h
0x18000ab28  movdqa  [rsp+68h+var_48], xmm0
0x18000ab2e  movdqa  [rsp+68h+var_38], xmm1
0x18000ab34  movdqa  [rsp+68h+var_28], xmm2
0x18000ab3a  movdqa  [rsp+68h+var_18], xmm3
0x18000ab40  mov     rdx, rax
0x18000ab43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_mme_l1_1_0_dll
0x18000ab4a  call    __delayLoadHelper2
0x18000ab4f  movdqa  xmm0, [rsp+68h+var_48]
0x18000ab55  movdqa  xmm1, [rsp+68h+var_38]
0x18000ab5b  movdqa  xmm2, [rsp+68h+var_28]
0x18000ab61  movdqa  xmm3, [rsp+68h+var_18]
0x18000ab67  mov     rcx, [rsp+68h+arg_0]
0x18000ab6c  mov     rdx, [rsp+68h+arg_8]
0x18000ab71  mov     r8, [rsp+68h+arg_10]
0x18000ab79  mov     r9, [rsp+68h+arg_18]
0x18000ab81  add     rsp, 68h
0x18000ab85  jmp     short $+2
0x18000ab87  jmp     rax
```
