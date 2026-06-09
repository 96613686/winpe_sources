# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180005c00`
- end: `0x180005c79`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005c7f`
- `0x180005c91`
- `0x180005ca3`

## callees

- `0x1800046b0`
- `0x180005c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005c00  mov     [rsp+arg_0], rcx
0x180005c05  mov     [rsp+arg_8], rdx
0x180005c0a  mov     [rsp+arg_10], r8
0x180005c0f  mov     [rsp+arg_18], r9
0x180005c14  sub     rsp, 68h
0x180005c18  movdqa  [rsp+68h+var_48], xmm0
0x180005c1e  movdqa  [rsp+68h+var_38], xmm1
0x180005c24  movdqa  [rsp+68h+var_28], xmm2
0x180005c2a  movdqa  [rsp+68h+var_18], xmm3
0x180005c30  mov     rdx, rax
0x180005c33  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180005c3a  call    __delayLoadHelper2
0x180005c3f  movdqa  xmm0, [rsp+68h+var_48]
0x180005c45  movdqa  xmm1, [rsp+68h+var_38]
0x180005c4b  movdqa  xmm2, [rsp+68h+var_28]
0x180005c51  movdqa  xmm3, [rsp+68h+var_18]
0x180005c57  mov     rcx, [rsp+68h+arg_0]
0x180005c5c  mov     rdx, [rsp+68h+arg_8]
0x180005c61  mov     r8, [rsp+68h+arg_10]
0x180005c69  mov     r9, [rsp+68h+arg_18]
0x180005c71  add     rsp, 68h
0x180005c75  jmp     short $+2
0x180005c77  jmp     rax
```
