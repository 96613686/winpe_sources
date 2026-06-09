# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll

- ea: `0x180009f47`
- end: `0x180009fc0`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009fc6`
- `0x180009fd8`
- `0x18000a040`
- `0x18000a052`
- `0x18000a064`
- `0x18000a076`

## callees

- `0x180007cb0`
- `0x180009f47`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009f47  mov     [rsp+arg_0], rcx
0x180009f4c  mov     [rsp+arg_8], rdx
0x180009f51  mov     [rsp+arg_10], r8
0x180009f56  mov     [rsp+arg_18], r9
0x180009f5b  sub     rsp, 68h
0x180009f5f  movdqa  [rsp+68h+var_48], xmm0
0x180009f65  movdqa  [rsp+68h+var_38], xmm1
0x180009f6b  movdqa  [rsp+68h+var_28], xmm2
0x180009f71  movdqa  [rsp+68h+var_18], xmm3
0x180009f77  mov     rdx, rax
0x180009f7a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll
0x180009f81  call    __delayLoadHelper2
0x180009f86  movdqa  xmm0, [rsp+68h+var_48]
0x180009f8c  movdqa  xmm1, [rsp+68h+var_38]
0x180009f92  movdqa  xmm2, [rsp+68h+var_28]
0x180009f98  movdqa  xmm3, [rsp+68h+var_18]
0x180009f9e  mov     rcx, [rsp+68h+arg_0]
0x180009fa3  mov     rdx, [rsp+68h+arg_8]
0x180009fa8  mov     r8, [rsp+68h+arg_10]
0x180009fb0  mov     r9, [rsp+68h+arg_18]
0x180009fb8  add     rsp, 68h
0x180009fbc  jmp     short $+2
0x180009fbe  jmp     rax
```
