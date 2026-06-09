# __tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll

- ea: `0x180001ca4`
- end: `0x180001d1d`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d23`
- `0x180001f78`
- `0x1800020b7`

## callees

- `0x180001ca4`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001ca4  mov     [rsp+arg_0], rcx
0x180001ca9  mov     [rsp+arg_8], rdx
0x180001cae  mov     [rsp+arg_10], r8
0x180001cb3  mov     [rsp+arg_18], r9
0x180001cb8  sub     rsp, 68h
0x180001cbc  movdqa  [rsp+68h+var_48], xmm0
0x180001cc2  movdqa  [rsp+68h+var_38], xmm1
0x180001cc8  movdqa  [rsp+68h+var_28], xmm2
0x180001cce  movdqa  [rsp+68h+var_18], xmm3
0x180001cd4  mov     rdx, rax
0x180001cd7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_4_dll
0x180001cde  call    __delayLoadHelper2
0x180001ce3  movdqa  xmm0, [rsp+68h+var_48]
0x180001ce9  movdqa  xmm1, [rsp+68h+var_38]
0x180001cef  movdqa  xmm2, [rsp+68h+var_28]
0x180001cf5  movdqa  xmm3, [rsp+68h+var_18]
0x180001cfb  mov     rcx, [rsp+68h+arg_0]
0x180001d00  mov     rdx, [rsp+68h+arg_8]
0x180001d05  mov     r8, [rsp+68h+arg_10]
0x180001d0d  mov     r9, [rsp+68h+arg_18]
0x180001d15  add     rsp, 68h
0x180001d19  jmp     short $+2
0x180001d1b  jmp     rax
```
