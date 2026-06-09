# __tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll

- ea: `0x180002beb`
- end: `0x180002c64`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c6a`

## callees

- `0x180002beb`
- `0x180018ae0`

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
0x180002beb  mov     [rsp+arg_0], rcx
0x180002bf0  mov     [rsp+arg_8], rdx
0x180002bf5  mov     [rsp+arg_10], r8
0x180002bfa  mov     [rsp+arg_18], r9
0x180002bff  sub     rsp, 68h
0x180002c03  movdqa  [rsp+68h+var_48], xmm0
0x180002c09  movdqa  [rsp+68h+var_38], xmm1
0x180002c0f  movdqa  [rsp+68h+var_28], xmm2
0x180002c15  movdqa  [rsp+68h+var_18], xmm3
0x180002c1b  mov     rdx, rax
0x180002c1e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_4_dll
0x180002c25  call    __delayLoadHelper2
0x180002c2a  movdqa  xmm0, [rsp+68h+var_48]
0x180002c30  movdqa  xmm1, [rsp+68h+var_38]
0x180002c36  movdqa  xmm2, [rsp+68h+var_28]
0x180002c3c  movdqa  xmm3, [rsp+68h+var_18]
0x180002c42  mov     rcx, [rsp+68h+arg_0]
0x180002c47  mov     rdx, [rsp+68h+arg_8]
0x180002c4c  mov     r8, [rsp+68h+arg_10]
0x180002c54  mov     r9, [rsp+68h+arg_18]
0x180002c5c  add     rsp, 68h
0x180002c60  jmp     short $+2
0x180002c62  jmp     rax
```
