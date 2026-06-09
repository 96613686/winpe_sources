# __tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll

- ea: `0x180002e29`
- end: `0x180002ea2`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ea8`

## callees

- `0x180002e29`
- `0x180018ae0`

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
0x180002e29  mov     [rsp+arg_0], rcx
0x180002e2e  mov     [rsp+arg_8], rdx
0x180002e33  mov     [rsp+arg_10], r8
0x180002e38  mov     [rsp+arg_18], r9
0x180002e3d  sub     rsp, 68h
0x180002e41  movdqa  [rsp+68h+var_48], xmm0
0x180002e47  movdqa  [rsp+68h+var_38], xmm1
0x180002e4d  movdqa  [rsp+68h+var_28], xmm2
0x180002e53  movdqa  [rsp+68h+var_18], xmm3
0x180002e59  mov     rdx, rax
0x180002e5c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll
0x180002e63  call    __delayLoadHelper2
0x180002e68  movdqa  xmm0, [rsp+68h+var_48]
0x180002e6e  movdqa  xmm1, [rsp+68h+var_38]
0x180002e74  movdqa  xmm2, [rsp+68h+var_28]
0x180002e7a  movdqa  xmm3, [rsp+68h+var_18]
0x180002e80  mov     rcx, [rsp+68h+arg_0]
0x180002e85  mov     rdx, [rsp+68h+arg_8]
0x180002e8a  mov     r8, [rsp+68h+arg_10]
0x180002e92  mov     r9, [rsp+68h+arg_18]
0x180002e9a  add     rsp, 68h
0x180002e9e  jmp     short $+2
0x180002ea0  jmp     rax
```
