# __tailMerge_api_ms_win_power_setting_l1_1_0_dll

- ea: `0x18001aa0e`
- end: `0x18001aa87`
- name: `__tailMerge_api_ms_win_power_setting_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001aa8d`
- `0x18001aa9f`

## callees

- `0x18000f880`
- `0x18001aa0e`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_power_setting_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_setting_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001aa0e  mov     [rsp+arg_0], rcx
0x18001aa13  mov     [rsp+arg_8], rdx
0x18001aa18  mov     [rsp+arg_10], r8
0x18001aa1d  mov     [rsp+arg_18], r9
0x18001aa22  sub     rsp, 68h
0x18001aa26  movdqa  [rsp+68h+var_48], xmm0
0x18001aa2c  movdqa  [rsp+68h+var_38], xmm1
0x18001aa32  movdqa  [rsp+68h+var_28], xmm2
0x18001aa38  movdqa  [rsp+68h+var_18], xmm3
0x18001aa3e  mov     rdx, rax
0x18001aa41  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_setting_l1_1_0_dll
0x18001aa48  call    __delayLoadHelper2
0x18001aa4d  movdqa  xmm0, [rsp+68h+var_48]
0x18001aa53  movdqa  xmm1, [rsp+68h+var_38]
0x18001aa59  movdqa  xmm2, [rsp+68h+var_28]
0x18001aa5f  movdqa  xmm3, [rsp+68h+var_18]
0x18001aa65  mov     rcx, [rsp+68h+arg_0]
0x18001aa6a  mov     rdx, [rsp+68h+arg_8]
0x18001aa6f  mov     r8, [rsp+68h+arg_10]
0x18001aa77  mov     r9, [rsp+68h+arg_18]
0x18001aa7f  add     rsp, 68h
0x18001aa83  jmp     short $+2
0x18001aa85  jmp     rax
```
