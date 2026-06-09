# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x18000ae49`
- end: `0x18000aec2`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000aec8`
- `0x18000af22`

## callees

- `0x180001530`
- `0x18000ae49`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ae49  mov     [rsp+arg_0], rcx
0x18000ae4e  mov     [rsp+arg_8], rdx
0x18000ae53  mov     [rsp+arg_10], r8
0x18000ae58  mov     [rsp+arg_18], r9
0x18000ae5d  sub     rsp, 68h
0x18000ae61  movdqa  [rsp+68h+var_48], xmm0
0x18000ae67  movdqa  [rsp+68h+var_38], xmm1
0x18000ae6d  movdqa  [rsp+68h+var_28], xmm2
0x18000ae73  movdqa  [rsp+68h+var_18], xmm3
0x18000ae79  mov     rdx, rax
0x18000ae7c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x18000ae83  call    __delayLoadHelper2
0x18000ae88  movdqa  xmm0, [rsp+68h+var_48]
0x18000ae8e  movdqa  xmm1, [rsp+68h+var_38]
0x18000ae94  movdqa  xmm2, [rsp+68h+var_28]
0x18000ae9a  movdqa  xmm3, [rsp+68h+var_18]
0x18000aea0  mov     rcx, [rsp+68h+arg_0]
0x18000aea5  mov     rdx, [rsp+68h+arg_8]
0x18000aeaa  mov     r8, [rsp+68h+arg_10]
0x18000aeb2  mov     r9, [rsp+68h+arg_18]
0x18000aeba  add     rsp, 68h
0x18000aebe  jmp     short $+2
0x18000aec0  jmp     rax
```
