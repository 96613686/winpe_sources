# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000a8b2`
- end: `0x18000a92b`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a931`
- `0x18000a9ce`
- `0x18000ae19`

## callees

- `0x180001530`
- `0x18000a8b2`

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
0x18000a8b2  mov     [rsp+arg_0], rcx
0x18000a8b7  mov     [rsp+arg_8], rdx
0x18000a8bc  mov     [rsp+arg_10], r8
0x18000a8c1  mov     [rsp+arg_18], r9
0x18000a8c6  sub     rsp, 68h
0x18000a8ca  movdqa  [rsp+68h+var_48], xmm0
0x18000a8d0  movdqa  [rsp+68h+var_38], xmm1
0x18000a8d6  movdqa  [rsp+68h+var_28], xmm2
0x18000a8dc  movdqa  [rsp+68h+var_18], xmm3
0x18000a8e2  mov     rdx, rax
0x18000a8e5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000a8ec  call    __delayLoadHelper2
0x18000a8f1  movdqa  xmm0, [rsp+68h+var_48]
0x18000a8f7  movdqa  xmm1, [rsp+68h+var_38]
0x18000a8fd  movdqa  xmm2, [rsp+68h+var_28]
0x18000a903  movdqa  xmm3, [rsp+68h+var_18]
0x18000a909  mov     rcx, [rsp+68h+arg_0]
0x18000a90e  mov     rdx, [rsp+68h+arg_8]
0x18000a913  mov     r8, [rsp+68h+arg_10]
0x18000a91b  mov     r9, [rsp+68h+arg_18]
0x18000a923  add     rsp, 68h
0x18000a927  jmp     short $+2
0x18000a929  jmp     rax
```
