# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x18000ab4b`
- end: `0x18000abc4`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000abca`

## callees

- `0x180009170`
- `0x18000ab4b`

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
0x18000ab4b  mov     [rsp+arg_0], rcx
0x18000ab50  mov     [rsp+arg_8], rdx
0x18000ab55  mov     [rsp+arg_10], r8
0x18000ab5a  mov     [rsp+arg_18], r9
0x18000ab5f  sub     rsp, 68h
0x18000ab63  movdqa  [rsp+68h+var_48], xmm0
0x18000ab69  movdqa  [rsp+68h+var_38], xmm1
0x18000ab6f  movdqa  [rsp+68h+var_28], xmm2
0x18000ab75  movdqa  [rsp+68h+var_18], xmm3
0x18000ab7b  mov     rdx, rax
0x18000ab7e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x18000ab85  call    __delayLoadHelper2
0x18000ab8a  movdqa  xmm0, [rsp+68h+var_48]
0x18000ab90  movdqa  xmm1, [rsp+68h+var_38]
0x18000ab96  movdqa  xmm2, [rsp+68h+var_28]
0x18000ab9c  movdqa  xmm3, [rsp+68h+var_18]
0x18000aba2  mov     rcx, [rsp+68h+arg_0]
0x18000aba7  mov     rdx, [rsp+68h+arg_8]
0x18000abac  mov     r8, [rsp+68h+arg_10]
0x18000abb4  mov     r9, [rsp+68h+arg_18]
0x18000abbc  add     rsp, 68h
0x18000abc0  jmp     short $+2
0x18000abc2  jmp     rax
```
