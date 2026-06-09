# __tailMerge_ext_ms_win_gdi_font_l1_1_0_dll

- ea: `0x180002411`
- end: `0x18000248a`
- name: `__tailMerge_ext_ms_win_gdi_font_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002490`
- `0x18000252d`
- `0x1800025ca`
- `0x1800025ee`

## callees

- `0x180002411`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_font_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002411  mov     [rsp+arg_0], rcx
0x180002416  mov     [rsp+arg_8], rdx
0x18000241b  mov     [rsp+arg_10], r8
0x180002420  mov     [rsp+arg_18], r9
0x180002425  sub     rsp, 68h
0x180002429  movdqa  [rsp+68h+var_48], xmm0
0x18000242f  movdqa  [rsp+68h+var_38], xmm1
0x180002435  movdqa  [rsp+68h+var_28], xmm2
0x18000243b  movdqa  [rsp+68h+var_18], xmm3
0x180002441  mov     rdx, rax
0x180002444  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_0_dll
0x18000244b  call    __delayLoadHelper2
0x180002450  movdqa  xmm0, [rsp+68h+var_48]
0x180002456  movdqa  xmm1, [rsp+68h+var_38]
0x18000245c  movdqa  xmm2, [rsp+68h+var_28]
0x180002462  movdqa  xmm3, [rsp+68h+var_18]
0x180002468  mov     rcx, [rsp+68h+arg_0]
0x18000246d  mov     rdx, [rsp+68h+arg_8]
0x180002472  mov     r8, [rsp+68h+arg_10]
0x18000247a  mov     r9, [rsp+68h+arg_18]
0x180002482  add     rsp, 68h
0x180002486  jmp     short $+2
0x180002488  jmp     rax
```
