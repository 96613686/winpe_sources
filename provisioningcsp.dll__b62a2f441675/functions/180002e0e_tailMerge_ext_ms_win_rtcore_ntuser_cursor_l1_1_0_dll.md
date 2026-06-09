# __tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll

- ea: `0x180002e0e`
- end: `0x180002e87`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e8d`
- `0x180002e9f`

## callees

- `0x180002e0e`
- `0x180031710`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002e0e  mov     [rsp+arg_0], rcx
0x180002e13  mov     [rsp+arg_8], rdx
0x180002e18  mov     [rsp+arg_10], r8
0x180002e1d  mov     [rsp+arg_18], r9
0x180002e22  sub     rsp, 68h
0x180002e26  movdqa  [rsp+68h+var_48], xmm0
0x180002e2c  movdqa  [rsp+68h+var_38], xmm1
0x180002e32  movdqa  [rsp+68h+var_28], xmm2
0x180002e38  movdqa  [rsp+68h+var_18], xmm3
0x180002e3e  mov     rdx, rax
0x180002e41  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll
0x180002e48  call    __delayLoadHelper2
0x180002e4d  movdqa  xmm0, [rsp+68h+var_48]
0x180002e53  movdqa  xmm1, [rsp+68h+var_38]
0x180002e59  movdqa  xmm2, [rsp+68h+var_28]
0x180002e5f  movdqa  xmm3, [rsp+68h+var_18]
0x180002e65  mov     rcx, [rsp+68h+arg_0]
0x180002e6a  mov     rdx, [rsp+68h+arg_8]
0x180002e6f  mov     r8, [rsp+68h+arg_10]
0x180002e77  mov     r9, [rsp+68h+arg_18]
0x180002e7f  add     rsp, 68h
0x180002e83  jmp     short $+2
0x180002e85  jmp     rax
```
