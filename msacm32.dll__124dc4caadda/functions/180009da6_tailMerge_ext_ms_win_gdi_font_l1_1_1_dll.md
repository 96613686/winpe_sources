# __tailMerge_ext_ms_win_gdi_font_l1_1_1_dll

- ea: `0x180009da6`
- end: `0x180009e1f`
- name: `__tailMerge_ext_ms_win_gdi_font_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009e25`

## callees

- `0x180007cb0`
- `0x180009da6`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_font_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009da6  mov     [rsp+arg_0], rcx
0x180009dab  mov     [rsp+arg_8], rdx
0x180009db0  mov     [rsp+arg_10], r8
0x180009db5  mov     [rsp+arg_18], r9
0x180009dba  sub     rsp, 68h
0x180009dbe  movdqa  [rsp+68h+var_48], xmm0
0x180009dc4  movdqa  [rsp+68h+var_38], xmm1
0x180009dca  movdqa  [rsp+68h+var_28], xmm2
0x180009dd0  movdqa  [rsp+68h+var_18], xmm3
0x180009dd6  mov     rdx, rax
0x180009dd9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_1_dll
0x180009de0  call    __delayLoadHelper2
0x180009de5  movdqa  xmm0, [rsp+68h+var_48]
0x180009deb  movdqa  xmm1, [rsp+68h+var_38]
0x180009df1  movdqa  xmm2, [rsp+68h+var_28]
0x180009df7  movdqa  xmm3, [rsp+68h+var_18]
0x180009dfd  mov     rcx, [rsp+68h+arg_0]
0x180009e02  mov     rdx, [rsp+68h+arg_8]
0x180009e07  mov     r8, [rsp+68h+arg_10]
0x180009e0f  mov     r9, [rsp+68h+arg_18]
0x180009e17  add     rsp, 68h
0x180009e1b  jmp     short $+2
0x180009e1d  jmp     rax
```
