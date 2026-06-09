# __tailMerge_api_ms_win_service_management_l2_1_0_dll

- ea: `0x18000a96f`
- end: `0x18000a9e8`
- name: `__tailMerge_api_ms_win_service_management_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000a9ee`

## callees

- `0x1800079c0`
- `0x18000a96f`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a96f  mov     [rsp+arg_0], rcx
0x18000a974  mov     [rsp+arg_8], rdx
0x18000a979  mov     [rsp+arg_10], r8
0x18000a97e  mov     [rsp+arg_18], r9
0x18000a983  sub     rsp, 68h
0x18000a987  movdqa  [rsp+68h+var_48], xmm0
0x18000a98d  movdqa  [rsp+68h+var_38], xmm1
0x18000a993  movdqa  [rsp+68h+var_28], xmm2
0x18000a999  movdqa  [rsp+68h+var_18], xmm3
0x18000a99f  mov     rdx, rax
0x18000a9a2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll
0x18000a9a9  call    __delayLoadHelper2
0x18000a9ae  movdqa  xmm0, [rsp+68h+var_48]
0x18000a9b4  movdqa  xmm1, [rsp+68h+var_38]
0x18000a9ba  movdqa  xmm2, [rsp+68h+var_28]
0x18000a9c0  movdqa  xmm3, [rsp+68h+var_18]
0x18000a9c6  mov     rcx, [rsp+68h+arg_0]
0x18000a9cb  mov     rdx, [rsp+68h+arg_8]
0x18000a9d0  mov     r8, [rsp+68h+arg_10]
0x18000a9d8  mov     r9, [rsp+68h+arg_18]
0x18000a9e0  add     rsp, 68h
0x18000a9e4  jmp     short $+2
0x18000a9e6  jmp     rax
```
