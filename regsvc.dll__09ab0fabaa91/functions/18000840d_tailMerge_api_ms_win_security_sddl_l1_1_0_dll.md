# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000840d`
- end: `0x180008486`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000848c`

## callees

- `0x18000840d`
- `0x18001e2e0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000840d  mov     [rsp+arg_0], rcx
0x180008412  mov     [rsp+arg_8], rdx
0x180008417  mov     [rsp+arg_10], r8
0x18000841c  mov     [rsp+arg_18], r9
0x180008421  sub     rsp, 68h
0x180008425  movdqa  [rsp+68h+var_48], xmm0
0x18000842b  movdqa  [rsp+68h+var_38], xmm1
0x180008431  movdqa  [rsp+68h+var_28], xmm2
0x180008437  movdqa  [rsp+68h+var_18], xmm3
0x18000843d  mov     rdx, rax
0x180008440  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180008447  call    __delayLoadHelper2
0x18000844c  movdqa  xmm0, [rsp+68h+var_48]
0x180008452  movdqa  xmm1, [rsp+68h+var_38]
0x180008458  movdqa  xmm2, [rsp+68h+var_28]
0x18000845e  movdqa  xmm3, [rsp+68h+var_18]
0x180008464  mov     rcx, [rsp+68h+arg_0]
0x180008469  mov     rdx, [rsp+68h+arg_8]
0x18000846e  mov     r8, [rsp+68h+arg_10]
0x180008476  mov     r9, [rsp+68h+arg_18]
0x18000847e  add     rsp, 68h
0x180008482  jmp     short $+2
0x180008484  jmp     rax
```
