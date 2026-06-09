# __tailMerge_api_ms_win_power_setting_l1_1_0_dll

- ea: `0x18000edc2`
- end: `0x18000ee3b`
- name: `__tailMerge_api_ms_win_power_setting_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ee41`

## callees

- `0x18000bd20`
- `0x18000edc2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_power_setting_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_setting_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000edc2  mov     [rsp+arg_0], rcx
0x18000edc7  mov     [rsp+arg_8], rdx
0x18000edcc  mov     [rsp+arg_10], r8
0x18000edd1  mov     [rsp+arg_18], r9
0x18000edd6  sub     rsp, 68h
0x18000edda  movdqa  [rsp+68h+var_48], xmm0
0x18000ede0  movdqa  [rsp+68h+var_38], xmm1
0x18000ede6  movdqa  [rsp+68h+var_28], xmm2
0x18000edec  movdqa  [rsp+68h+var_18], xmm3
0x18000edf2  mov     rdx, rax
0x18000edf5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_setting_l1_1_0_dll
0x18000edfc  call    __delayLoadHelper2
0x18000ee01  movdqa  xmm0, [rsp+68h+var_48]
0x18000ee07  movdqa  xmm1, [rsp+68h+var_38]
0x18000ee0d  movdqa  xmm2, [rsp+68h+var_28]
0x18000ee13  movdqa  xmm3, [rsp+68h+var_18]
0x18000ee19  mov     rcx, [rsp+68h+arg_0]
0x18000ee1e  mov     rdx, [rsp+68h+arg_8]
0x18000ee23  mov     r8, [rsp+68h+arg_10]
0x18000ee2b  mov     r9, [rsp+68h+arg_18]
0x18000ee33  add     rsp, 68h
0x18000ee37  jmp     short $+2
0x18000ee39  jmp     rax
```
