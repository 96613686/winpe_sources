# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18001edda`
- end: `0x18001ee53`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ee59`
- `0x18001eeb3`
- `0x18001eec5`
- `0x18001eed7`

## callees

- `0x180013080`
- `0x18001edda`

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
0x18001edda  mov     [rsp+arg_0], rcx
0x18001eddf  mov     [rsp+arg_8], rdx
0x18001ede4  mov     [rsp+arg_10], r8
0x18001ede9  mov     [rsp+arg_18], r9
0x18001edee  sub     rsp, 68h
0x18001edf2  movdqa  [rsp+68h+var_48], xmm0
0x18001edf8  movdqa  [rsp+68h+var_38], xmm1
0x18001edfe  movdqa  [rsp+68h+var_28], xmm2
0x18001ee04  movdqa  [rsp+68h+var_18], xmm3
0x18001ee0a  mov     rdx, rax
0x18001ee0d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18001ee14  call    __delayLoadHelper2
0x18001ee19  movdqa  xmm0, [rsp+68h+var_48]
0x18001ee1f  movdqa  xmm1, [rsp+68h+var_38]
0x18001ee25  movdqa  xmm2, [rsp+68h+var_28]
0x18001ee2b  movdqa  xmm3, [rsp+68h+var_18]
0x18001ee31  mov     rcx, [rsp+68h+arg_0]
0x18001ee36  mov     rdx, [rsp+68h+arg_8]
0x18001ee3b  mov     r8, [rsp+68h+arg_10]
0x18001ee43  mov     r9, [rsp+68h+arg_18]
0x18001ee4b  add     rsp, 68h
0x18001ee4f  jmp     short $+2
0x18001ee51  jmp     rax
```
