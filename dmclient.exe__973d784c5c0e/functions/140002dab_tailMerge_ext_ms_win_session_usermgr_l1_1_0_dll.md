# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x140002dab`
- end: `0x140002e24`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002e2a`
- `0x140002e3c`
- `0x140002ea4`

## callees

- `0x140002dab`
- `0x140019490`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002dab  mov     [rsp+arg_0], rcx
0x140002db0  mov     [rsp+arg_8], rdx
0x140002db5  mov     [rsp+arg_10], r8
0x140002dba  mov     [rsp+arg_18], r9
0x140002dbf  sub     rsp, 68h
0x140002dc3  movdqa  [rsp+68h+var_48], xmm0
0x140002dc9  movdqa  [rsp+68h+var_38], xmm1
0x140002dcf  movdqa  [rsp+68h+var_28], xmm2
0x140002dd5  movdqa  [rsp+68h+var_18], xmm3
0x140002ddb  mov     rdx, rax
0x140002dde  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x140002de5  call    __delayLoadHelper2
0x140002dea  movdqa  xmm0, [rsp+68h+var_48]
0x140002df0  movdqa  xmm1, [rsp+68h+var_38]
0x140002df6  movdqa  xmm2, [rsp+68h+var_28]
0x140002dfc  movdqa  xmm3, [rsp+68h+var_18]
0x140002e02  mov     rcx, [rsp+68h+arg_0]
0x140002e07  mov     rdx, [rsp+68h+arg_8]
0x140002e0c  mov     r8, [rsp+68h+arg_10]
0x140002e14  mov     r9, [rsp+68h+arg_18]
0x140002e1c  add     rsp, 68h
0x140002e20  jmp     short $+2
0x140002e22  jmp     rax
```
