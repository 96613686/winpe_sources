# __tailMerge_ext_ms_win_core_psm_bi_l1_1_0_dll

- ea: `0x18001cb05`
- end: `0x18001cb7e`
- name: `__tailMerge_ext_ms_win_core_psm_bi_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001cb84`
- `0x18001cb96`
- `0x18001cba8`
- `0x18001cbcc`
- `0x18001cbde`
- `0x18001cc02`

## callees

- `0x1800174f0`
- `0x18001cb05`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_psm_bi_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_bi_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001cb05  mov     [rsp+arg_0], rcx
0x18001cb0a  mov     [rsp+arg_8], rdx
0x18001cb0f  mov     [rsp+arg_10], r8
0x18001cb14  mov     [rsp+arg_18], r9
0x18001cb19  sub     rsp, 68h
0x18001cb1d  movdqa  [rsp+68h+var_48], xmm0
0x18001cb23  movdqa  [rsp+68h+var_38], xmm1
0x18001cb29  movdqa  [rsp+68h+var_28], xmm2
0x18001cb2f  movdqa  [rsp+68h+var_18], xmm3
0x18001cb35  mov     rdx, rax
0x18001cb38  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_bi_l1_1_0_dll
0x18001cb3f  call    __delayLoadHelper2
0x18001cb44  movdqa  xmm0, [rsp+68h+var_48]
0x18001cb4a  movdqa  xmm1, [rsp+68h+var_38]
0x18001cb50  movdqa  xmm2, [rsp+68h+var_28]
0x18001cb56  movdqa  xmm3, [rsp+68h+var_18]
0x18001cb5c  mov     rcx, [rsp+68h+arg_0]
0x18001cb61  mov     rdx, [rsp+68h+arg_8]
0x18001cb66  mov     r8, [rsp+68h+arg_10]
0x18001cb6e  mov     r9, [rsp+68h+arg_18]
0x18001cb76  add     rsp, 68h
0x18001cb7a  jmp     short $+2
0x18001cb7c  jmp     rax
```
