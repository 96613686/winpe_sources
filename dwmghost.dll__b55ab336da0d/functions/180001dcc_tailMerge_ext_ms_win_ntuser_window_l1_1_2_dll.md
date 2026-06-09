# __tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll

- ea: `0x180001dcc`
- end: `0x180001e45`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e4b`
- `0x180001f0c`
- `0x180001f42`

## callees

- `0x180001dcc`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001dcc  mov     [rsp+arg_0], rcx
0x180001dd1  mov     [rsp+arg_8], rdx
0x180001dd6  mov     [rsp+arg_10], r8
0x180001ddb  mov     [rsp+arg_18], r9
0x180001de0  sub     rsp, 68h
0x180001de4  movdqa  [rsp+68h+var_48], xmm0
0x180001dea  movdqa  [rsp+68h+var_38], xmm1
0x180001df0  movdqa  [rsp+68h+var_28], xmm2
0x180001df6  movdqa  [rsp+68h+var_18], xmm3
0x180001dfc  mov     rdx, rax
0x180001dff  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_2_dll
0x180001e06  call    __delayLoadHelper2
0x180001e0b  movdqa  xmm0, [rsp+68h+var_48]
0x180001e11  movdqa  xmm1, [rsp+68h+var_38]
0x180001e17  movdqa  xmm2, [rsp+68h+var_28]
0x180001e1d  movdqa  xmm3, [rsp+68h+var_18]
0x180001e23  mov     rcx, [rsp+68h+arg_0]
0x180001e28  mov     rdx, [rsp+68h+arg_8]
0x180001e2d  mov     r8, [rsp+68h+arg_10]
0x180001e35  mov     r9, [rsp+68h+arg_18]
0x180001e3d  add     rsp, 68h
0x180001e41  jmp     short $+2
0x180001e43  jmp     rax
```
