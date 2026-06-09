# __tailMerge_ext_ms_win_core_psm_bi_l1_2_0_dll

- ea: `0x18001ca7a`
- end: `0x18001caf3`
- name: `__tailMerge_ext_ms_win_core_psm_bi_l1_2_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001caf9`
- `0x18001cbba`
- `0x18001cbf0`
- `0x18001cc14`

## callees

- `0x1800174f0`
- `0x18001ca7a`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_psm_bi_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_bi_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001ca7a  mov     [rsp+arg_0], rcx
0x18001ca7f  mov     [rsp+arg_8], rdx
0x18001ca84  mov     [rsp+arg_10], r8
0x18001ca89  mov     [rsp+arg_18], r9
0x18001ca8e  sub     rsp, 68h
0x18001ca92  movdqa  [rsp+68h+var_48], xmm0
0x18001ca98  movdqa  [rsp+68h+var_38], xmm1
0x18001ca9e  movdqa  [rsp+68h+var_28], xmm2
0x18001caa4  movdqa  [rsp+68h+var_18], xmm3
0x18001caaa  mov     rdx, rax
0x18001caad  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_bi_l1_2_0_dll
0x18001cab4  call    __delayLoadHelper2
0x18001cab9  movdqa  xmm0, [rsp+68h+var_48]
0x18001cabf  movdqa  xmm1, [rsp+68h+var_38]
0x18001cac5  movdqa  xmm2, [rsp+68h+var_28]
0x18001cacb  movdqa  xmm3, [rsp+68h+var_18]
0x18001cad1  mov     rcx, [rsp+68h+arg_0]
0x18001cad6  mov     rdx, [rsp+68h+arg_8]
0x18001cadb  mov     r8, [rsp+68h+arg_10]
0x18001cae3  mov     r9, [rsp+68h+arg_18]
0x18001caeb  add     rsp, 68h
0x18001caef  jmp     short $+2
0x18001caf1  jmp     rax
```
