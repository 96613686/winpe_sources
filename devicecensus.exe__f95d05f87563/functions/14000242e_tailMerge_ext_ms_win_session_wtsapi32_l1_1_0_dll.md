# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x14000242e`
- end: `0x1400024a7`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400024ad`
- `0x1400024bf`
- `0x1400024d1`

## callees

- `0x14000242e`
- `0x140011470`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000242e  mov     [rsp+arg_0], rcx
0x140002433  mov     [rsp+arg_8], rdx
0x140002438  mov     [rsp+arg_10], r8
0x14000243d  mov     [rsp+arg_18], r9
0x140002442  sub     rsp, 68h
0x140002446  movdqa  [rsp+68h+var_48], xmm0
0x14000244c  movdqa  [rsp+68h+var_38], xmm1
0x140002452  movdqa  [rsp+68h+var_28], xmm2
0x140002458  movdqa  [rsp+68h+var_18], xmm3
0x14000245e  mov     rdx, rax
0x140002461  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x140002468  call    __delayLoadHelper2
0x14000246d  movdqa  xmm0, [rsp+68h+var_48]
0x140002473  movdqa  xmm1, [rsp+68h+var_38]
0x140002479  movdqa  xmm2, [rsp+68h+var_28]
0x14000247f  movdqa  xmm3, [rsp+68h+var_18]
0x140002485  mov     rcx, [rsp+68h+arg_0]
0x14000248a  mov     rdx, [rsp+68h+arg_8]
0x14000248f  mov     r8, [rsp+68h+arg_10]
0x140002497  mov     r9, [rsp+68h+arg_18]
0x14000249f  add     rsp, 68h
0x1400024a3  jmp     short $+2
0x1400024a5  jmp     rax
```
