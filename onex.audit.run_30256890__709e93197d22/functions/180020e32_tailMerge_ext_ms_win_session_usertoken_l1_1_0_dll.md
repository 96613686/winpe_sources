# __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll

- ea: `0x180020e32`
- end: `0x180020eab`
- name: `__tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020eb1`

## callees

- `0x180018b30`
- `0x180020e32`

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
0x180020e32  mov     [rsp+arg_0], rcx
0x180020e37  mov     [rsp+arg_8], rdx
0x180020e3c  mov     [rsp+arg_10], r8
0x180020e41  mov     [rsp+arg_18], r9
0x180020e46  sub     rsp, 68h
0x180020e4a  movdqa  [rsp+68h+var_48], xmm0
0x180020e50  movdqa  [rsp+68h+var_38], xmm1
0x180020e56  movdqa  [rsp+68h+var_28], xmm2
0x180020e5c  movdqa  [rsp+68h+var_18], xmm3
0x180020e62  mov     rdx, rax
0x180020e65  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll
0x180020e6c  call    __delayLoadHelper2
0x180020e71  movdqa  xmm0, [rsp+68h+var_48]
0x180020e77  movdqa  xmm1, [rsp+68h+var_38]
0x180020e7d  movdqa  xmm2, [rsp+68h+var_28]
0x180020e83  movdqa  xmm3, [rsp+68h+var_18]
0x180020e89  mov     rcx, [rsp+68h+arg_0]
0x180020e8e  mov     rdx, [rsp+68h+arg_8]
0x180020e93  mov     r8, [rsp+68h+arg_10]
0x180020e9b  mov     r9, [rsp+68h+arg_18]
0x180020ea3  add     rsp, 68h
0x180020ea7  jmp     short $+2
0x180020ea9  jmp     rax
```
