# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x18000ed25`
- end: `0x18000ed9e`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000eda4`
- `0x18000edb6`

## callees

- `0x18000bd20`
- `0x18000ed25`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ed25  mov     [rsp+arg_0], rcx
0x18000ed2a  mov     [rsp+arg_8], rdx
0x18000ed2f  mov     [rsp+arg_10], r8
0x18000ed34  mov     [rsp+arg_18], r9
0x18000ed39  sub     rsp, 68h
0x18000ed3d  movdqa  [rsp+68h+var_48], xmm0
0x18000ed43  movdqa  [rsp+68h+var_38], xmm1
0x18000ed49  movdqa  [rsp+68h+var_28], xmm2
0x18000ed4f  movdqa  [rsp+68h+var_18], xmm3
0x18000ed55  mov     rdx, rax
0x18000ed58  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x18000ed5f  call    __delayLoadHelper2
0x18000ed64  movdqa  xmm0, [rsp+68h+var_48]
0x18000ed6a  movdqa  xmm1, [rsp+68h+var_38]
0x18000ed70  movdqa  xmm2, [rsp+68h+var_28]
0x18000ed76  movdqa  xmm3, [rsp+68h+var_18]
0x18000ed7c  mov     rcx, [rsp+68h+arg_0]
0x18000ed81  mov     rdx, [rsp+68h+arg_8]
0x18000ed86  mov     r8, [rsp+68h+arg_10]
0x18000ed8e  mov     r9, [rsp+68h+arg_18]
0x18000ed96  add     rsp, 68h
0x18000ed9a  jmp     short $+2
0x18000ed9c  jmp     rax
```
