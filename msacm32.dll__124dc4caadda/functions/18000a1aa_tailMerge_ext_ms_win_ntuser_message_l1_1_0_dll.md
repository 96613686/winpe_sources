# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x18000a1aa`
- end: `0x18000a223`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a229`
- `0x18000a23b`
- `0x18000a2a4`

## callees

- `0x180007cb0`
- `0x18000a1aa`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a1aa  mov     [rsp+arg_0], rcx
0x18000a1af  mov     [rsp+arg_8], rdx
0x18000a1b4  mov     [rsp+arg_10], r8
0x18000a1b9  mov     [rsp+arg_18], r9
0x18000a1be  sub     rsp, 68h
0x18000a1c2  movdqa  [rsp+68h+var_48], xmm0
0x18000a1c8  movdqa  [rsp+68h+var_38], xmm1
0x18000a1ce  movdqa  [rsp+68h+var_28], xmm2
0x18000a1d4  movdqa  [rsp+68h+var_18], xmm3
0x18000a1da  mov     rdx, rax
0x18000a1dd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x18000a1e4  call    __delayLoadHelper2
0x18000a1e9  movdqa  xmm0, [rsp+68h+var_48]
0x18000a1ef  movdqa  xmm1, [rsp+68h+var_38]
0x18000a1f5  movdqa  xmm2, [rsp+68h+var_28]
0x18000a1fb  movdqa  xmm3, [rsp+68h+var_18]
0x18000a201  mov     rcx, [rsp+68h+arg_0]
0x18000a206  mov     rdx, [rsp+68h+arg_8]
0x18000a20b  mov     r8, [rsp+68h+arg_10]
0x18000a213  mov     r9, [rsp+68h+arg_18]
0x18000a21b  add     rsp, 68h
0x18000a21f  jmp     short $+2
0x18000a221  jmp     rax
```
