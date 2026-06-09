# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000de2a`
- end: `0x18000dea3`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dea9`

## callees

- `0x180009aa0`
- `0x18000de2a`

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
0x18000de2a  mov     [rsp+arg_0], rcx
0x18000de2f  mov     [rsp+arg_8], rdx
0x18000de34  mov     [rsp+arg_10], r8
0x18000de39  mov     [rsp+arg_18], r9
0x18000de3e  sub     rsp, 68h
0x18000de42  movdqa  [rsp+68h+var_48], xmm0
0x18000de48  movdqa  [rsp+68h+var_38], xmm1
0x18000de4e  movdqa  [rsp+68h+var_28], xmm2
0x18000de54  movdqa  [rsp+68h+var_18], xmm3
0x18000de5a  mov     rdx, rax
0x18000de5d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18000de64  call    __delayLoadHelper2
0x18000de69  movdqa  xmm0, [rsp+68h+var_48]
0x18000de6f  movdqa  xmm1, [rsp+68h+var_38]
0x18000de75  movdqa  xmm2, [rsp+68h+var_28]
0x18000de7b  movdqa  xmm3, [rsp+68h+var_18]
0x18000de81  mov     rcx, [rsp+68h+arg_0]
0x18000de86  mov     rdx, [rsp+68h+arg_8]
0x18000de8b  mov     r8, [rsp+68h+arg_10]
0x18000de93  mov     r9, [rsp+68h+arg_18]
0x18000de9b  add     rsp, 68h
0x18000de9f  jmp     short $+2
0x18000dea1  jmp     rax
```
