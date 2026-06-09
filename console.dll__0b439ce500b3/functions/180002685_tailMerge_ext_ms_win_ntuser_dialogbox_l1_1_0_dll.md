# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll

- ea: `0x180002685`
- end: `0x1800026fe`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002704`
- `0x180002716`
- `0x180002728`
- `0x18000273a`
- `0x180002770`
- `0x180002782`
- `0x180002794`
- `0x1800027a6`

## callees

- `0x180002685`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002685  mov     [rsp+arg_0], rcx
0x18000268a  mov     [rsp+arg_8], rdx
0x18000268f  mov     [rsp+arg_10], r8
0x180002694  mov     [rsp+arg_18], r9
0x180002699  sub     rsp, 68h
0x18000269d  movdqa  [rsp+68h+var_48], xmm0
0x1800026a3  movdqa  [rsp+68h+var_38], xmm1
0x1800026a9  movdqa  [rsp+68h+var_28], xmm2
0x1800026af  movdqa  [rsp+68h+var_18], xmm3
0x1800026b5  mov     rdx, rax
0x1800026b8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll
0x1800026bf  call    __delayLoadHelper2
0x1800026c4  movdqa  xmm0, [rsp+68h+var_48]
0x1800026ca  movdqa  xmm1, [rsp+68h+var_38]
0x1800026d0  movdqa  xmm2, [rsp+68h+var_28]
0x1800026d6  movdqa  xmm3, [rsp+68h+var_18]
0x1800026dc  mov     rcx, [rsp+68h+arg_0]
0x1800026e1  mov     rdx, [rsp+68h+arg_8]
0x1800026e6  mov     r8, [rsp+68h+arg_10]
0x1800026ee  mov     r9, [rsp+68h+arg_18]
0x1800026f6  add     rsp, 68h
0x1800026fa  jmp     short $+2
0x1800026fc  jmp     rax
```
