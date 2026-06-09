# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x18000a6c5`
- end: `0x18000a73e`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a744`
- `0x18000a756`
- `0x18000a768`
- `0x18000a77a`

## callees

- `0x180007cb0`
- `0x18000a6c5`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a6c5  mov     [rsp+arg_0], rcx
0x18000a6ca  mov     [rsp+arg_8], rdx
0x18000a6cf  mov     [rsp+arg_10], r8
0x18000a6d4  mov     [rsp+arg_18], r9
0x18000a6d9  sub     rsp, 68h
0x18000a6dd  movdqa  [rsp+68h+var_48], xmm0
0x18000a6e3  movdqa  [rsp+68h+var_38], xmm1
0x18000a6e9  movdqa  [rsp+68h+var_28], xmm2
0x18000a6ef  movdqa  [rsp+68h+var_18], xmm3
0x18000a6f5  mov     rdx, rax
0x18000a6f8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x18000a6ff  call    __delayLoadHelper2
0x18000a704  movdqa  xmm0, [rsp+68h+var_48]
0x18000a70a  movdqa  xmm1, [rsp+68h+var_38]
0x18000a710  movdqa  xmm2, [rsp+68h+var_28]
0x18000a716  movdqa  xmm3, [rsp+68h+var_18]
0x18000a71c  mov     rcx, [rsp+68h+arg_0]
0x18000a721  mov     rdx, [rsp+68h+arg_8]
0x18000a726  mov     r8, [rsp+68h+arg_10]
0x18000a72e  mov     r9, [rsp+68h+arg_18]
0x18000a736  add     rsp, 68h
0x18000a73a  jmp     short $+2
0x18000a73c  jmp     rax
```
