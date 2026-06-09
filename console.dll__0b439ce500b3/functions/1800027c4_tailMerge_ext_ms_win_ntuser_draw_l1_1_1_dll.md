# __tailMerge_ext_ms_win_ntuser_draw_l1_1_1_dll

- ea: `0x1800027c4`
- end: `0x18000283d`
- name: `__tailMerge_ext_ms_win_ntuser_draw_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002843`

## callees

- `0x1800027c4`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_draw_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027c4  mov     [rsp+arg_0], rcx
0x1800027c9  mov     [rsp+arg_8], rdx
0x1800027ce  mov     [rsp+arg_10], r8
0x1800027d3  mov     [rsp+arg_18], r9
0x1800027d8  sub     rsp, 68h
0x1800027dc  movdqa  [rsp+68h+var_48], xmm0
0x1800027e2  movdqa  [rsp+68h+var_38], xmm1
0x1800027e8  movdqa  [rsp+68h+var_28], xmm2
0x1800027ee  movdqa  [rsp+68h+var_18], xmm3
0x1800027f4  mov     rdx, rax
0x1800027f7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_1_dll
0x1800027fe  call    __delayLoadHelper2
0x180002803  movdqa  xmm0, [rsp+68h+var_48]
0x180002809  movdqa  xmm1, [rsp+68h+var_38]
0x18000280f  movdqa  xmm2, [rsp+68h+var_28]
0x180002815  movdqa  xmm3, [rsp+68h+var_18]
0x18000281b  mov     rcx, [rsp+68h+arg_0]
0x180002820  mov     rdx, [rsp+68h+arg_8]
0x180002825  mov     r8, [rsp+68h+arg_10]
0x18000282d  mov     r9, [rsp+68h+arg_18]
0x180002835  add     rsp, 68h
0x180002839  jmp     short $+2
0x18000283b  jmp     rax
```
