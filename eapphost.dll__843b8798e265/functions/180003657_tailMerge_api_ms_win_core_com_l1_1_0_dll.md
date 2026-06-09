# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180003657`
- end: `0x1800036d0`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800036d6`
- `0x1800036e8`
- `0x1800036fa`
- `0x18000370c`
- `0x18000371e`
- `0x180003730`
- `0x180003742`
- `0x180003766`
- `0x180003778`
- `0x18000378a`
- `0x1800037bc`
- `0x1800037ce`

## callees

- `0x180003657`
- `0x180034f70`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003657  mov     [rsp+arg_0], rcx
0x18000365c  mov     [rsp+arg_8], rdx
0x180003661  mov     [rsp+arg_10], r8
0x180003666  mov     [rsp+arg_18], r9
0x18000366b  sub     rsp, 68h
0x18000366f  movdqa  [rsp+68h+var_48], xmm0
0x180003675  movdqa  [rsp+68h+var_38], xmm1
0x18000367b  movdqa  [rsp+68h+var_28], xmm2
0x180003681  movdqa  [rsp+68h+var_18], xmm3
0x180003687  mov     rdx, rax
0x18000368a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180003691  call    __delayLoadHelper2
0x180003696  movdqa  xmm0, [rsp+68h+var_48]
0x18000369c  movdqa  xmm1, [rsp+68h+var_38]
0x1800036a2  movdqa  xmm2, [rsp+68h+var_28]
0x1800036a8  movdqa  xmm3, [rsp+68h+var_18]
0x1800036ae  mov     rcx, [rsp+68h+arg_0]
0x1800036b3  mov     rdx, [rsp+68h+arg_8]
0x1800036b8  mov     r8, [rsp+68h+arg_10]
0x1800036c0  mov     r9, [rsp+68h+arg_18]
0x1800036c8  add     rsp, 68h
0x1800036cc  jmp     short $+2
0x1800036ce  jmp     rax
```
