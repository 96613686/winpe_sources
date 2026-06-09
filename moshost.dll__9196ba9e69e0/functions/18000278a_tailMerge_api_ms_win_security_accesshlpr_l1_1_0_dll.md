# __tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll

- ea: `0x18000278a`
- end: `0x180002803`
- name: `__tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002809`
- `0x18000281b`

## callees

- `0x18000278a`
- `0x18000c580`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_accesshlpr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000278a  mov     [rsp+arg_0], rcx
0x18000278f  mov     [rsp+arg_8], rdx
0x180002794  mov     [rsp+arg_10], r8
0x180002799  mov     [rsp+arg_18], r9
0x18000279e  sub     rsp, 68h
0x1800027a2  movdqa  [rsp+68h+var_48], xmm0
0x1800027a8  movdqa  [rsp+68h+var_38], xmm1
0x1800027ae  movdqa  [rsp+68h+var_28], xmm2
0x1800027b4  movdqa  [rsp+68h+var_18], xmm3
0x1800027ba  mov     rdx, rax
0x1800027bd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_accesshlpr_l1_1_0_dll
0x1800027c4  call    __delayLoadHelper2
0x1800027c9  movdqa  xmm0, [rsp+68h+var_48]
0x1800027cf  movdqa  xmm1, [rsp+68h+var_38]
0x1800027d5  movdqa  xmm2, [rsp+68h+var_28]
0x1800027db  movdqa  xmm3, [rsp+68h+var_18]
0x1800027e1  mov     rcx, [rsp+68h+arg_0]
0x1800027e6  mov     rdx, [rsp+68h+arg_8]
0x1800027eb  mov     r8, [rsp+68h+arg_10]
0x1800027f3  mov     r9, [rsp+68h+arg_18]
0x1800027fb  add     rsp, 68h
0x1800027ff  jmp     short $+2
0x180002801  jmp     rax
```
