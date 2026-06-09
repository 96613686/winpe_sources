# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000aa9b`
- end: `0x18000ab14`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ab1a`
- `0x18000ae2b`

## callees

- `0x180001530`
- `0x18000aa9b`

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
0x18000aa9b  mov     [rsp+arg_0], rcx
0x18000aaa0  mov     [rsp+arg_8], rdx
0x18000aaa5  mov     [rsp+arg_10], r8
0x18000aaaa  mov     [rsp+arg_18], r9
0x18000aaaf  sub     rsp, 68h
0x18000aab3  movdqa  [rsp+68h+var_48], xmm0
0x18000aab9  movdqa  [rsp+68h+var_38], xmm1
0x18000aabf  movdqa  [rsp+68h+var_28], xmm2
0x18000aac5  movdqa  [rsp+68h+var_18], xmm3
0x18000aacb  mov     rdx, rax
0x18000aace  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18000aad5  call    __delayLoadHelper2
0x18000aada  movdqa  xmm0, [rsp+68h+var_48]
0x18000aae0  movdqa  xmm1, [rsp+68h+var_38]
0x18000aae6  movdqa  xmm2, [rsp+68h+var_28]
0x18000aaec  movdqa  xmm3, [rsp+68h+var_18]
0x18000aaf2  mov     rcx, [rsp+68h+arg_0]
0x18000aaf7  mov     rdx, [rsp+68h+arg_8]
0x18000aafc  mov     r8, [rsp+68h+arg_10]
0x18000ab04  mov     r9, [rsp+68h+arg_18]
0x18000ab0c  add     rsp, 68h
0x18000ab10  jmp     short $+2
0x18000ab12  jmp     rax
```
