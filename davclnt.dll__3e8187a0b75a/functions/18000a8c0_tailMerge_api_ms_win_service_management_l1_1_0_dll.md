# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x18000a8c0`
- end: `0x18000a939`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000a93f`
- `0x18000a951`
- `0x18000a963`

## callees

- `0x1800079c0`
- `0x18000a8c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a8c0  mov     [rsp+arg_0], rcx
0x18000a8c5  mov     [rsp+arg_8], rdx
0x18000a8ca  mov     [rsp+arg_10], r8
0x18000a8cf  mov     [rsp+arg_18], r9
0x18000a8d4  sub     rsp, 68h
0x18000a8d8  movdqa  [rsp+68h+var_48], xmm0
0x18000a8de  movdqa  [rsp+68h+var_38], xmm1
0x18000a8e4  movdqa  [rsp+68h+var_28], xmm2
0x18000a8ea  movdqa  [rsp+68h+var_18], xmm3
0x18000a8f0  mov     rdx, rax
0x18000a8f3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x18000a8fa  call    __delayLoadHelper2
0x18000a8ff  movdqa  xmm0, [rsp+68h+var_48]
0x18000a905  movdqa  xmm1, [rsp+68h+var_38]
0x18000a90b  movdqa  xmm2, [rsp+68h+var_28]
0x18000a911  movdqa  xmm3, [rsp+68h+var_18]
0x18000a917  mov     rcx, [rsp+68h+arg_0]
0x18000a91c  mov     rdx, [rsp+68h+arg_8]
0x18000a921  mov     r8, [rsp+68h+arg_10]
0x18000a929  mov     r9, [rsp+68h+arg_18]
0x18000a931  add     rsp, 68h
0x18000a935  jmp     short $+2
0x18000a937  jmp     rax
```
