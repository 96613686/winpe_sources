# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x18000ad20`
- end: `0x18000ad99`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ad9f`

## callees

- `0x180009170`
- `0x18000ad20`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_registry_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ad20  mov     [rsp+arg_0], rcx
0x18000ad25  mov     [rsp+arg_8], rdx
0x18000ad2a  mov     [rsp+arg_10], r8
0x18000ad2f  mov     [rsp+arg_18], r9
0x18000ad34  sub     rsp, 68h
0x18000ad38  movdqa  [rsp+68h+var_48], xmm0
0x18000ad3e  movdqa  [rsp+68h+var_38], xmm1
0x18000ad44  movdqa  [rsp+68h+var_28], xmm2
0x18000ad4a  movdqa  [rsp+68h+var_18], xmm3
0x18000ad50  mov     rdx, rax
0x18000ad53  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x18000ad5a  call    __delayLoadHelper2
0x18000ad5f  movdqa  xmm0, [rsp+68h+var_48]
0x18000ad65  movdqa  xmm1, [rsp+68h+var_38]
0x18000ad6b  movdqa  xmm2, [rsp+68h+var_28]
0x18000ad71  movdqa  xmm3, [rsp+68h+var_18]
0x18000ad77  mov     rcx, [rsp+68h+arg_0]
0x18000ad7c  mov     rdx, [rsp+68h+arg_8]
0x18000ad81  mov     r8, [rsp+68h+arg_10]
0x18000ad89  mov     r9, [rsp+68h+arg_18]
0x18000ad91  add     rsp, 68h
0x18000ad95  jmp     short $+2
0x18000ad97  jmp     rax
```
