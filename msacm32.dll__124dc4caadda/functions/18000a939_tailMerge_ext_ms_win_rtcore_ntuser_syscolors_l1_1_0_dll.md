# __tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll

- ea: `0x18000a939`
- end: `0x18000a9b2`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a9b8`

## callees

- `0x180007cb0`
- `0x18000a939`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a939  mov     [rsp+arg_0], rcx
0x18000a93e  mov     [rsp+arg_8], rdx
0x18000a943  mov     [rsp+arg_10], r8
0x18000a948  mov     [rsp+arg_18], r9
0x18000a94d  sub     rsp, 68h
0x18000a951  movdqa  [rsp+68h+var_48], xmm0
0x18000a957  movdqa  [rsp+68h+var_38], xmm1
0x18000a95d  movdqa  [rsp+68h+var_28], xmm2
0x18000a963  movdqa  [rsp+68h+var_18], xmm3
0x18000a969  mov     rdx, rax
0x18000a96c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll
0x18000a973  call    __delayLoadHelper2
0x18000a978  movdqa  xmm0, [rsp+68h+var_48]
0x18000a97e  movdqa  xmm1, [rsp+68h+var_38]
0x18000a984  movdqa  xmm2, [rsp+68h+var_28]
0x18000a98a  movdqa  xmm3, [rsp+68h+var_18]
0x18000a990  mov     rcx, [rsp+68h+arg_0]
0x18000a995  mov     rdx, [rsp+68h+arg_8]
0x18000a99a  mov     r8, [rsp+68h+arg_10]
0x18000a9a2  mov     r9, [rsp+68h+arg_18]
0x18000a9aa  add     rsp, 68h
0x18000a9ae  jmp     short $+2
0x18000a9b0  jmp     rax
```
