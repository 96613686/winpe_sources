# __tailMerge_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll

- ea: `0x18000deb5`
- end: `0x18000df2e`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000df34`
- `0x18000dfd1`

## callees

- `0x180009aa0`
- `0x18000deb5`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000deb5  mov     [rsp+arg_0], rcx
0x18000deba  mov     [rsp+arg_8], rdx
0x18000debf  mov     [rsp+arg_10], r8
0x18000dec4  mov     [rsp+arg_18], r9
0x18000dec9  sub     rsp, 68h
0x18000decd  movdqa  [rsp+68h+var_48], xmm0
0x18000ded3  movdqa  [rsp+68h+var_38], xmm1
0x18000ded9  movdqa  [rsp+68h+var_28], xmm2
0x18000dedf  movdqa  [rsp+68h+var_18], xmm3
0x18000dee5  mov     rdx, rax
0x18000dee8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dpi_l1_2_0_dll
0x18000deef  call    __delayLoadHelper2
0x18000def4  movdqa  xmm0, [rsp+68h+var_48]
0x18000defa  movdqa  xmm1, [rsp+68h+var_38]
0x18000df00  movdqa  xmm2, [rsp+68h+var_28]
0x18000df06  movdqa  xmm3, [rsp+68h+var_18]
0x18000df0c  mov     rcx, [rsp+68h+arg_0]
0x18000df11  mov     rdx, [rsp+68h+arg_8]
0x18000df16  mov     r8, [rsp+68h+arg_10]
0x18000df1e  mov     r9, [rsp+68h+arg_18]
0x18000df26  add     rsp, 68h
0x18000df2a  jmp     short $+2
0x18000df2c  jmp     rax
```
