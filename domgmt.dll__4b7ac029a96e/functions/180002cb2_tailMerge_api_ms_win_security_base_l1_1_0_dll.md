# __tailMerge_api_ms_win_security_base_l1_1_0_dll

- ea: `0x180002cb2`
- end: `0x180002d2b`
- name: `__tailMerge_api_ms_win_security_base_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d31`

## callees

- `0x180002cb2`
- `0x18000d4b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002cb2  mov     [rsp+arg_0], rcx
0x180002cb7  mov     [rsp+arg_8], rdx
0x180002cbc  mov     [rsp+arg_10], r8
0x180002cc1  mov     [rsp+arg_18], r9
0x180002cc6  sub     rsp, 68h
0x180002cca  movdqa  [rsp+68h+var_48], xmm0
0x180002cd0  movdqa  [rsp+68h+var_38], xmm1
0x180002cd6  movdqa  [rsp+68h+var_28], xmm2
0x180002cdc  movdqa  [rsp+68h+var_18], xmm3
0x180002ce2  mov     rdx, rax
0x180002ce5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll
0x180002cec  call    __delayLoadHelper2
0x180002cf1  movdqa  xmm0, [rsp+68h+var_48]
0x180002cf7  movdqa  xmm1, [rsp+68h+var_38]
0x180002cfd  movdqa  xmm2, [rsp+68h+var_28]
0x180002d03  movdqa  xmm3, [rsp+68h+var_18]
0x180002d09  mov     rcx, [rsp+68h+arg_0]
0x180002d0e  mov     rdx, [rsp+68h+arg_8]
0x180002d13  mov     r8, [rsp+68h+arg_10]
0x180002d1b  mov     r9, [rsp+68h+arg_18]
0x180002d23  add     rsp, 68h
0x180002d27  jmp     short $+2
0x180002d29  jmp     rax
```
