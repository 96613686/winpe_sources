# __tailMerge_api_ms_win_core_apiquery_l1_1_0_dll

- ea: `0x180005f73`
- end: `0x180005fec`
- name: `__tailMerge_api_ms_win_core_apiquery_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005ff2`

## callees

- `0x1800023e0`
- `0x180005f73`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_apiquery_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_apiquery_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005f73  mov     [rsp+arg_0], rcx
0x180005f78  mov     [rsp+arg_8], rdx
0x180005f7d  mov     [rsp+arg_10], r8
0x180005f82  mov     [rsp+arg_18], r9
0x180005f87  sub     rsp, 68h
0x180005f8b  movdqa  [rsp+68h+var_48], xmm0
0x180005f91  movdqa  [rsp+68h+var_38], xmm1
0x180005f97  movdqa  [rsp+68h+var_28], xmm2
0x180005f9d  movdqa  [rsp+68h+var_18], xmm3
0x180005fa3  mov     rdx, rax
0x180005fa6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_apiquery_l1_1_0_dll
0x180005fad  call    __delayLoadHelper2
0x180005fb2  movdqa  xmm0, [rsp+68h+var_48]
0x180005fb8  movdqa  xmm1, [rsp+68h+var_38]
0x180005fbe  movdqa  xmm2, [rsp+68h+var_28]
0x180005fc4  movdqa  xmm3, [rsp+68h+var_18]
0x180005fca  mov     rcx, [rsp+68h+arg_0]
0x180005fcf  mov     rdx, [rsp+68h+arg_8]
0x180005fd4  mov     r8, [rsp+68h+arg_10]
0x180005fdc  mov     r9, [rsp+68h+arg_18]
0x180005fe4  add     rsp, 68h
0x180005fe8  jmp     short $+2
0x180005fea  jmp     rax
```
