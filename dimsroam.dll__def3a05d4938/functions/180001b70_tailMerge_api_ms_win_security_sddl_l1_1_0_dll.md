# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180001b70`
- end: `0x180001be9`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001bef`

## callees

- `0x180001b70`
- `0x18000d7b0`

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
0x180001b70  mov     [rsp+arg_0], rcx
0x180001b75  mov     [rsp+arg_8], rdx
0x180001b7a  mov     [rsp+arg_10], r8
0x180001b7f  mov     [rsp+arg_18], r9
0x180001b84  sub     rsp, 68h
0x180001b88  movdqa  [rsp+68h+var_48], xmm0
0x180001b8e  movdqa  [rsp+68h+var_38], xmm1
0x180001b94  movdqa  [rsp+68h+var_28], xmm2
0x180001b9a  movdqa  [rsp+68h+var_18], xmm3
0x180001ba0  mov     rdx, rax
0x180001ba3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180001baa  call    __delayLoadHelper2
0x180001baf  movdqa  xmm0, [rsp+68h+var_48]
0x180001bb5  movdqa  xmm1, [rsp+68h+var_38]
0x180001bbb  movdqa  xmm2, [rsp+68h+var_28]
0x180001bc1  movdqa  xmm3, [rsp+68h+var_18]
0x180001bc7  mov     rcx, [rsp+68h+arg_0]
0x180001bcc  mov     rdx, [rsp+68h+arg_8]
0x180001bd1  mov     r8, [rsp+68h+arg_10]
0x180001bd9  mov     r9, [rsp+68h+arg_18]
0x180001be1  add     rsp, 68h
0x180001be5  jmp     short $+2
0x180001be7  jmp     rax
```
