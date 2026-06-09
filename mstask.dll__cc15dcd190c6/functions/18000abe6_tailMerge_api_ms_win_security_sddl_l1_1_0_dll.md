# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000abe6`
- end: `0x18000ac5f`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac65`

## callees

- `0x180009170`
- `0x18000abe6`

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
0x18000abe6  mov     [rsp+arg_0], rcx
0x18000abeb  mov     [rsp+arg_8], rdx
0x18000abf0  mov     [rsp+arg_10], r8
0x18000abf5  mov     [rsp+arg_18], r9
0x18000abfa  sub     rsp, 68h
0x18000abfe  movdqa  [rsp+68h+var_48], xmm0
0x18000ac04  movdqa  [rsp+68h+var_38], xmm1
0x18000ac0a  movdqa  [rsp+68h+var_28], xmm2
0x18000ac10  movdqa  [rsp+68h+var_18], xmm3
0x18000ac16  mov     rdx, rax
0x18000ac19  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18000ac20  call    __delayLoadHelper2
0x18000ac25  movdqa  xmm0, [rsp+68h+var_48]
0x18000ac2b  movdqa  xmm1, [rsp+68h+var_38]
0x18000ac31  movdqa  xmm2, [rsp+68h+var_28]
0x18000ac37  movdqa  xmm3, [rsp+68h+var_18]
0x18000ac3d  mov     rcx, [rsp+68h+arg_0]
0x18000ac42  mov     rdx, [rsp+68h+arg_8]
0x18000ac47  mov     r8, [rsp+68h+arg_10]
0x18000ac4f  mov     r9, [rsp+68h+arg_18]
0x18000ac57  add     rsp, 68h
0x18000ac5b  jmp     short $+2
0x18000ac5d  jmp     rax
```
