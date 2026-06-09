# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x140002d6b`
- end: `0x140002de4`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002dea`
- `0x140002dfc`
- `0x140002e64`

## callees

- `0x140002d6b`
- `0x140018670`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002d6b  mov     [rsp+arg_0], rcx
0x140002d70  mov     [rsp+arg_8], rdx
0x140002d75  mov     [rsp+arg_10], r8
0x140002d7a  mov     [rsp+arg_18], r9
0x140002d7f  sub     rsp, 68h
0x140002d83  movdqa  [rsp+68h+var_48], xmm0
0x140002d89  movdqa  [rsp+68h+var_38], xmm1
0x140002d8f  movdqa  [rsp+68h+var_28], xmm2
0x140002d95  movdqa  [rsp+68h+var_18], xmm3
0x140002d9b  mov     rdx, rax
0x140002d9e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x140002da5  call    __delayLoadHelper2
0x140002daa  movdqa  xmm0, [rsp+68h+var_48]
0x140002db0  movdqa  xmm1, [rsp+68h+var_38]
0x140002db6  movdqa  xmm2, [rsp+68h+var_28]
0x140002dbc  movdqa  xmm3, [rsp+68h+var_18]
0x140002dc2  mov     rcx, [rsp+68h+arg_0]
0x140002dc7  mov     rdx, [rsp+68h+arg_8]
0x140002dcc  mov     r8, [rsp+68h+arg_10]
0x140002dd4  mov     r9, [rsp+68h+arg_18]
0x140002ddc  add     rsp, 68h
0x140002de0  jmp     short $+2
0x140002de2  jmp     rax
```
