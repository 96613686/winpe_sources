# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180015c61`
- end: `0x180015cda`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015ce0`

## callees

- `0x180014230`
- `0x180015c61`

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
0x180015c61  mov     [rsp+arg_0], rcx
0x180015c66  mov     [rsp+arg_8], rdx
0x180015c6b  mov     [rsp+arg_10], r8
0x180015c70  mov     [rsp+arg_18], r9
0x180015c75  sub     rsp, 68h
0x180015c79  movdqa  [rsp+68h+var_48], xmm0
0x180015c7f  movdqa  [rsp+68h+var_38], xmm1
0x180015c85  movdqa  [rsp+68h+var_28], xmm2
0x180015c8b  movdqa  [rsp+68h+var_18], xmm3
0x180015c91  mov     rdx, rax
0x180015c94  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180015c9b  call    __delayLoadHelper2
0x180015ca0  movdqa  xmm0, [rsp+68h+var_48]
0x180015ca6  movdqa  xmm1, [rsp+68h+var_38]
0x180015cac  movdqa  xmm2, [rsp+68h+var_28]
0x180015cb2  movdqa  xmm3, [rsp+68h+var_18]
0x180015cb8  mov     rcx, [rsp+68h+arg_0]
0x180015cbd  mov     rdx, [rsp+68h+arg_8]
0x180015cc2  mov     r8, [rsp+68h+arg_10]
0x180015cca  mov     r9, [rsp+68h+arg_18]
0x180015cd2  add     rsp, 68h
0x180015cd6  jmp     short $+2
0x180015cd8  jmp     rax
```
