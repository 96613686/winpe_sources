# __tailMerge_api_ms_win_security_base_l1_1_0_dll

- ea: `0x18001620b`
- end: `0x180016284`
- name: `__tailMerge_api_ms_win_security_base_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001628a`
- `0x18001629c`
- `0x1800162c0`
- `0x1800165f5`
- `0x180016692`
- `0x1800166a4`

## callees

- `0x180014ae0`
- `0x18001620b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001620b  mov     [rsp+arg_0], rcx
0x180016210  mov     [rsp+arg_8], rdx
0x180016215  mov     [rsp+arg_10], r8
0x18001621a  mov     [rsp+arg_18], r9
0x18001621f  sub     rsp, 68h
0x180016223  movdqa  [rsp+68h+var_48], xmm0
0x180016229  movdqa  [rsp+68h+var_38], xmm1
0x18001622f  movdqa  [rsp+68h+var_28], xmm2
0x180016235  movdqa  [rsp+68h+var_18], xmm3
0x18001623b  mov     rdx, rax
0x18001623e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll
0x180016245  call    __delayLoadHelper2
0x18001624a  movdqa  xmm0, [rsp+68h+var_48]
0x180016250  movdqa  xmm1, [rsp+68h+var_38]
0x180016256  movdqa  xmm2, [rsp+68h+var_28]
0x18001625c  movdqa  xmm3, [rsp+68h+var_18]
0x180016262  mov     rcx, [rsp+68h+arg_0]
0x180016267  mov     rdx, [rsp+68h+arg_8]
0x18001626c  mov     r8, [rsp+68h+arg_10]
0x180016274  mov     r9, [rsp+68h+arg_18]
0x18001627c  add     rsp, 68h
0x180016280  jmp     short $+2
0x180016282  jmp     rax
```
