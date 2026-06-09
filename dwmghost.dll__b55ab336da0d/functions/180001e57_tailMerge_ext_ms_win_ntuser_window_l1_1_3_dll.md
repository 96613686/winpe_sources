# __tailMerge_ext_ms_win_ntuser_window_l1_1_3_dll

- ea: `0x180001e57`
- end: `0x180001ed0`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_3_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ed6`
- `0x180001efa`
- `0x180001f30`

## callees

- `0x180001e57`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_3_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_3_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e57  mov     [rsp+arg_0], rcx
0x180001e5c  mov     [rsp+arg_8], rdx
0x180001e61  mov     [rsp+arg_10], r8
0x180001e66  mov     [rsp+arg_18], r9
0x180001e6b  sub     rsp, 68h
0x180001e6f  movdqa  [rsp+68h+var_48], xmm0
0x180001e75  movdqa  [rsp+68h+var_38], xmm1
0x180001e7b  movdqa  [rsp+68h+var_28], xmm2
0x180001e81  movdqa  [rsp+68h+var_18], xmm3
0x180001e87  mov     rdx, rax
0x180001e8a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_3_dll
0x180001e91  call    __delayLoadHelper2
0x180001e96  movdqa  xmm0, [rsp+68h+var_48]
0x180001e9c  movdqa  xmm1, [rsp+68h+var_38]
0x180001ea2  movdqa  xmm2, [rsp+68h+var_28]
0x180001ea8  movdqa  xmm3, [rsp+68h+var_18]
0x180001eae  mov     rcx, [rsp+68h+arg_0]
0x180001eb3  mov     rdx, [rsp+68h+arg_8]
0x180001eb8  mov     r8, [rsp+68h+arg_10]
0x180001ec0  mov     r9, [rsp+68h+arg_18]
0x180001ec8  add     rsp, 68h
0x180001ecc  jmp     short $+2
0x180001ece  jmp     rax
```
