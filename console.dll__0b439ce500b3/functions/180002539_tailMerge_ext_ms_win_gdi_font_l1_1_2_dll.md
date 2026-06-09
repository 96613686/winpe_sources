# __tailMerge_ext_ms_win_gdi_font_l1_1_2_dll

- ea: `0x180002539`
- end: `0x1800025b2`
- name: `__tailMerge_ext_ms_win_gdi_font_l1_1_2_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025b8`

## callees

- `0x180002539`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_font_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002539  mov     [rsp+arg_0], rcx
0x18000253e  mov     [rsp+arg_8], rdx
0x180002543  mov     [rsp+arg_10], r8
0x180002548  mov     [rsp+arg_18], r9
0x18000254d  sub     rsp, 68h
0x180002551  movdqa  [rsp+68h+var_48], xmm0
0x180002557  movdqa  [rsp+68h+var_38], xmm1
0x18000255d  movdqa  [rsp+68h+var_28], xmm2
0x180002563  movdqa  [rsp+68h+var_18], xmm3
0x180002569  mov     rdx, rax
0x18000256c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_2_dll
0x180002573  call    __delayLoadHelper2
0x180002578  movdqa  xmm0, [rsp+68h+var_48]
0x18000257e  movdqa  xmm1, [rsp+68h+var_38]
0x180002584  movdqa  xmm2, [rsp+68h+var_28]
0x18000258a  movdqa  xmm3, [rsp+68h+var_18]
0x180002590  mov     rcx, [rsp+68h+arg_0]
0x180002595  mov     rdx, [rsp+68h+arg_8]
0x18000259a  mov     r8, [rsp+68h+arg_10]
0x1800025a2  mov     r9, [rsp+68h+arg_18]
0x1800025aa  add     rsp, 68h
0x1800025ae  jmp     short $+2
0x1800025b0  jmp     rax
```
