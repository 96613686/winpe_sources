# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000ef8c`
- end: `0x18000f005`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f00b`
- `0x18000f01d`
- `0x18000f02f`

## callees

- `0x18000bd20`
- `0x18000ef8c`

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
0x18000ef8c  mov     [rsp+arg_0], rcx
0x18000ef91  mov     [rsp+arg_8], rdx
0x18000ef96  mov     [rsp+arg_10], r8
0x18000ef9b  mov     [rsp+arg_18], r9
0x18000efa0  sub     rsp, 68h
0x18000efa4  movdqa  [rsp+68h+var_48], xmm0
0x18000efaa  movdqa  [rsp+68h+var_38], xmm1
0x18000efb0  movdqa  [rsp+68h+var_28], xmm2
0x18000efb6  movdqa  [rsp+68h+var_18], xmm3
0x18000efbc  mov     rdx, rax
0x18000efbf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000efc6  call    __delayLoadHelper2
0x18000efcb  movdqa  xmm0, [rsp+68h+var_48]
0x18000efd1  movdqa  xmm1, [rsp+68h+var_38]
0x18000efd7  movdqa  xmm2, [rsp+68h+var_28]
0x18000efdd  movdqa  xmm3, [rsp+68h+var_18]
0x18000efe3  mov     rcx, [rsp+68h+arg_0]
0x18000efe8  mov     rdx, [rsp+68h+arg_8]
0x18000efed  mov     r8, [rsp+68h+arg_10]
0x18000eff5  mov     r9, [rsp+68h+arg_18]
0x18000effd  add     rsp, 68h
0x18000f001  jmp     short $+2
0x18000f003  jmp     rax
```
