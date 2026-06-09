# __tailMerge_ext_ms_win_security_efs_l1_1_1_dll

- ea: `0x180002236`
- end: `0x1800022af`
- name: `__tailMerge_ext_ms_win_security_efs_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022b5`

## callees

- `0x180002236`
- `0x1800132a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_efs_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_efs_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002236  mov     [rsp+arg_0], rcx
0x18000223b  mov     [rsp+arg_8], rdx
0x180002240  mov     [rsp+arg_10], r8
0x180002245  mov     [rsp+arg_18], r9
0x18000224a  sub     rsp, 68h
0x18000224e  movdqa  [rsp+68h+var_48], xmm0
0x180002254  movdqa  [rsp+68h+var_38], xmm1
0x18000225a  movdqa  [rsp+68h+var_28], xmm2
0x180002260  movdqa  [rsp+68h+var_18], xmm3
0x180002266  mov     rdx, rax
0x180002269  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_efs_l1_1_1_dll
0x180002270  call    __delayLoadHelper2
0x180002275  movdqa  xmm0, [rsp+68h+var_48]
0x18000227b  movdqa  xmm1, [rsp+68h+var_38]
0x180002281  movdqa  xmm2, [rsp+68h+var_28]
0x180002287  movdqa  xmm3, [rsp+68h+var_18]
0x18000228d  mov     rcx, [rsp+68h+arg_0]
0x180002292  mov     rdx, [rsp+68h+arg_8]
0x180002297  mov     r8, [rsp+68h+arg_10]
0x18000229f  mov     r9, [rsp+68h+arg_18]
0x1800022a7  add     rsp, 68h
0x1800022ab  jmp     short $+2
0x1800022ad  jmp     rax
```
