# __tailMerge_ext_ms_mf_pal_l2_1_0_dll

- ea: `0x18003a41f`
- end: `0x18003a498`
- name: `__tailMerge_ext_ms_mf_pal_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003a49e`
- `0x18003a4b0`
- `0x18003a4c2`
- `0x18003a528`
- `0x18003a53a`

## callees

- `0x18003a41f`
- `0x18006eee0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_mf_pal_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_mf_pal_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18003a41f  mov     [rsp+arg_0], rcx
0x18003a424  mov     [rsp+arg_8], rdx
0x18003a429  mov     [rsp+arg_10], r8
0x18003a42e  mov     [rsp+arg_18], r9
0x18003a433  sub     rsp, 68h
0x18003a437  movdqa  [rsp+68h+var_48], xmm0
0x18003a43d  movdqa  [rsp+68h+var_38], xmm1
0x18003a443  movdqa  [rsp+68h+var_28], xmm2
0x18003a449  movdqa  [rsp+68h+var_18], xmm3
0x18003a44f  mov     rdx, rax
0x18003a452  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_mf_pal_l2_1_0_dll
0x18003a459  call    __delayLoadHelper2
0x18003a45e  movdqa  xmm0, [rsp+68h+var_48]
0x18003a464  movdqa  xmm1, [rsp+68h+var_38]
0x18003a46a  movdqa  xmm2, [rsp+68h+var_28]
0x18003a470  movdqa  xmm3, [rsp+68h+var_18]
0x18003a476  mov     rcx, [rsp+68h+arg_0]
0x18003a47b  mov     rdx, [rsp+68h+arg_8]
0x18003a480  mov     r8, [rsp+68h+arg_10]
0x18003a488  mov     r9, [rsp+68h+arg_18]
0x18003a490  add     rsp, 68h
0x18003a494  jmp     short $+2
0x18003a496  jmp     rax
```
