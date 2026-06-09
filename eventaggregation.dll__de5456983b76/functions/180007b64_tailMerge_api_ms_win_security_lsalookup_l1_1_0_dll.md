# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x180007b64`
- end: `0x180007bdd`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007be3`

## callees

- `0x180007b64`
- `0x18000bd20`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180007b64  mov     [rsp+arg_0], rcx
0x180007b69  mov     [rsp+arg_8], rdx
0x180007b6e  mov     [rsp+arg_10], r8
0x180007b73  mov     [rsp+arg_18], r9
0x180007b78  sub     rsp, 68h
0x180007b7c  movdqa  [rsp+68h+var_48], xmm0
0x180007b82  movdqa  [rsp+68h+var_38], xmm1
0x180007b88  movdqa  [rsp+68h+var_28], xmm2
0x180007b8e  movdqa  [rsp+68h+var_18], xmm3
0x180007b94  mov     rdx, rax
0x180007b97  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x180007b9e  call    __delayLoadHelper2
0x180007ba3  movdqa  xmm0, [rsp+68h+var_48]
0x180007ba9  movdqa  xmm1, [rsp+68h+var_38]
0x180007baf  movdqa  xmm2, [rsp+68h+var_28]
0x180007bb5  movdqa  xmm3, [rsp+68h+var_18]
0x180007bbb  mov     rcx, [rsp+68h+arg_0]
0x180007bc0  mov     rdx, [rsp+68h+arg_8]
0x180007bc5  mov     r8, [rsp+68h+arg_10]
0x180007bcd  mov     r9, [rsp+68h+arg_18]
0x180007bd5  add     rsp, 68h
0x180007bd9  jmp     short $+2
0x180007bdb  jmp     rax
```
