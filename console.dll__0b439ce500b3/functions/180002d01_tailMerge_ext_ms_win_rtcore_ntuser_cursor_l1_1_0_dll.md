# __tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll

- ea: `0x180002d01`
- end: `0x180002d7a`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d80`

## callees

- `0x180002d01`
- `0x180018ae0`

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
0x180002d01  mov     [rsp+arg_0], rcx
0x180002d06  mov     [rsp+arg_8], rdx
0x180002d0b  mov     [rsp+arg_10], r8
0x180002d10  mov     [rsp+arg_18], r9
0x180002d15  sub     rsp, 68h
0x180002d19  movdqa  [rsp+68h+var_48], xmm0
0x180002d1f  movdqa  [rsp+68h+var_38], xmm1
0x180002d25  movdqa  [rsp+68h+var_28], xmm2
0x180002d2b  movdqa  [rsp+68h+var_18], xmm3
0x180002d31  mov     rdx, rax
0x180002d34  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll
0x180002d3b  call    __delayLoadHelper2
0x180002d40  movdqa  xmm0, [rsp+68h+var_48]
0x180002d46  movdqa  xmm1, [rsp+68h+var_38]
0x180002d4c  movdqa  xmm2, [rsp+68h+var_28]
0x180002d52  movdqa  xmm3, [rsp+68h+var_18]
0x180002d58  mov     rcx, [rsp+68h+arg_0]
0x180002d5d  mov     rdx, [rsp+68h+arg_8]
0x180002d62  mov     r8, [rsp+68h+arg_10]
0x180002d6a  mov     r9, [rsp+68h+arg_18]
0x180002d72  add     rsp, 68h
0x180002d76  jmp     short $+2
0x180002d78  jmp     rax
```
