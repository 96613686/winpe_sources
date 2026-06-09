# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x180020d2e`
- end: `0x180020da7`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020dad`
- `0x180020dbf`
- `0x180020dd1`

## callees

- `0x180018b30`
- `0x180020d2e`

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
0x180020d2e  mov     [rsp+arg_0], rcx
0x180020d33  mov     [rsp+arg_8], rdx
0x180020d38  mov     [rsp+arg_10], r8
0x180020d3d  mov     [rsp+arg_18], r9
0x180020d42  sub     rsp, 68h
0x180020d46  movdqa  [rsp+68h+var_48], xmm0
0x180020d4c  movdqa  [rsp+68h+var_38], xmm1
0x180020d52  movdqa  [rsp+68h+var_28], xmm2
0x180020d58  movdqa  [rsp+68h+var_18], xmm3
0x180020d5e  mov     rdx, rax
0x180020d61  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x180020d68  call    __delayLoadHelper2
0x180020d6d  movdqa  xmm0, [rsp+68h+var_48]
0x180020d73  movdqa  xmm1, [rsp+68h+var_38]
0x180020d79  movdqa  xmm2, [rsp+68h+var_28]
0x180020d7f  movdqa  xmm3, [rsp+68h+var_18]
0x180020d85  mov     rcx, [rsp+68h+arg_0]
0x180020d8a  mov     rdx, [rsp+68h+arg_8]
0x180020d8f  mov     r8, [rsp+68h+arg_10]
0x180020d97  mov     r9, [rsp+68h+arg_18]
0x180020d9f  add     rsp, 68h
0x180020da3  jmp     short $+2
0x180020da5  jmp     rax
```
