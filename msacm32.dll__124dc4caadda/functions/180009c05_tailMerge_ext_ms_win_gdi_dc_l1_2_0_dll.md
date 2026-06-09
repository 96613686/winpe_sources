# __tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll

- ea: `0x180009c05`
- end: `0x180009c7e`
- name: `__tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009c84`

## callees

- `0x180007cb0`
- `0x180009c05`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009c05  mov     [rsp+arg_0], rcx
0x180009c0a  mov     [rsp+arg_8], rdx
0x180009c0f  mov     [rsp+arg_10], r8
0x180009c14  mov     [rsp+arg_18], r9
0x180009c19  sub     rsp, 68h
0x180009c1d  movdqa  [rsp+68h+var_48], xmm0
0x180009c23  movdqa  [rsp+68h+var_38], xmm1
0x180009c29  movdqa  [rsp+68h+var_28], xmm2
0x180009c2f  movdqa  [rsp+68h+var_18], xmm3
0x180009c35  mov     rdx, rax
0x180009c38  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll
0x180009c3f  call    __delayLoadHelper2
0x180009c44  movdqa  xmm0, [rsp+68h+var_48]
0x180009c4a  movdqa  xmm1, [rsp+68h+var_38]
0x180009c50  movdqa  xmm2, [rsp+68h+var_28]
0x180009c56  movdqa  xmm3, [rsp+68h+var_18]
0x180009c5c  mov     rcx, [rsp+68h+arg_0]
0x180009c61  mov     rdx, [rsp+68h+arg_8]
0x180009c66  mov     r8, [rsp+68h+arg_10]
0x180009c6e  mov     r9, [rsp+68h+arg_18]
0x180009c76  add     rsp, 68h
0x180009c7a  jmp     short $+2
0x180009c7c  jmp     rax
```
