# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000ec9a`
- end: `0x18000ed13`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed19`

## callees

- `0x18000bd20`
- `0x18000ec9a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ec9a  mov     [rsp+arg_0], rcx
0x18000ec9f  mov     [rsp+arg_8], rdx
0x18000eca4  mov     [rsp+arg_10], r8
0x18000eca9  mov     [rsp+arg_18], r9
0x18000ecae  sub     rsp, 68h
0x18000ecb2  movdqa  [rsp+68h+var_48], xmm0
0x18000ecb8  movdqa  [rsp+68h+var_38], xmm1
0x18000ecbe  movdqa  [rsp+68h+var_28], xmm2
0x18000ecc4  movdqa  [rsp+68h+var_18], xmm3
0x18000ecca  mov     rdx, rax
0x18000eccd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18000ecd4  call    __delayLoadHelper2
0x18000ecd9  movdqa  xmm0, [rsp+68h+var_48]
0x18000ecdf  movdqa  xmm1, [rsp+68h+var_38]
0x18000ece5  movdqa  xmm2, [rsp+68h+var_28]
0x18000eceb  movdqa  xmm3, [rsp+68h+var_18]
0x18000ecf1  mov     rcx, [rsp+68h+arg_0]
0x18000ecf6  mov     rdx, [rsp+68h+arg_8]
0x18000ecfb  mov     r8, [rsp+68h+arg_10]
0x18000ed03  mov     r9, [rsp+68h+arg_18]
0x18000ed0b  add     rsp, 68h
0x18000ed0f  jmp     short $+2
0x18000ed11  jmp     rax
```
