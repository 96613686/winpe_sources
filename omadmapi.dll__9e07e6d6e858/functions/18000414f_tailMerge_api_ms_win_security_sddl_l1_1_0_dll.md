# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000414f`
- end: `0x1800041c8`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800041ce`

## callees

- `0x18000414f`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000414f  mov     [rsp+arg_0], rcx
0x180004154  mov     [rsp+arg_8], rdx
0x180004159  mov     [rsp+arg_10], r8
0x18000415e  mov     [rsp+arg_18], r9
0x180004163  sub     rsp, 68h
0x180004167  movdqa  [rsp+68h+var_48], xmm0
0x18000416d  movdqa  [rsp+68h+var_38], xmm1
0x180004173  movdqa  [rsp+68h+var_28], xmm2
0x180004179  movdqa  [rsp+68h+var_18], xmm3
0x18000417f  mov     rdx, rax
0x180004182  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180004189  call    __delayLoadHelper2
0x18000418e  movdqa  xmm0, [rsp+68h+var_48]
0x180004194  movdqa  xmm1, [rsp+68h+var_38]
0x18000419a  movdqa  xmm2, [rsp+68h+var_28]
0x1800041a0  movdqa  xmm3, [rsp+68h+var_18]
0x1800041a6  mov     rcx, [rsp+68h+arg_0]
0x1800041ab  mov     rdx, [rsp+68h+arg_8]
0x1800041b0  mov     r8, [rsp+68h+arg_10]
0x1800041b8  mov     r9, [rsp+68h+arg_18]
0x1800041c0  add     rsp, 68h
0x1800041c4  jmp     short $+2
0x1800041c6  jmp     rax
```
