# __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll

- ea: `0x140002f06`
- end: `0x140002f7f`
- name: `__tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002f85`

## callees

- `0x140002f06`
- `0x140019490`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002f06  mov     [rsp+arg_0], rcx
0x140002f0b  mov     [rsp+arg_8], rdx
0x140002f10  mov     [rsp+arg_10], r8
0x140002f15  mov     [rsp+arg_18], r9
0x140002f1a  sub     rsp, 68h
0x140002f1e  movdqa  [rsp+68h+var_48], xmm0
0x140002f24  movdqa  [rsp+68h+var_38], xmm1
0x140002f2a  movdqa  [rsp+68h+var_28], xmm2
0x140002f30  movdqa  [rsp+68h+var_18], xmm3
0x140002f36  mov     rdx, rax
0x140002f39  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll
0x140002f40  call    __delayLoadHelper2
0x140002f45  movdqa  xmm0, [rsp+68h+var_48]
0x140002f4b  movdqa  xmm1, [rsp+68h+var_38]
0x140002f51  movdqa  xmm2, [rsp+68h+var_28]
0x140002f57  movdqa  xmm3, [rsp+68h+var_18]
0x140002f5d  mov     rcx, [rsp+68h+arg_0]
0x140002f62  mov     rdx, [rsp+68h+arg_8]
0x140002f67  mov     r8, [rsp+68h+arg_10]
0x140002f6f  mov     r9, [rsp+68h+arg_18]
0x140002f77  add     rsp, 68h
0x140002f7b  jmp     short $+2
0x140002f7d  jmp     rax
```
