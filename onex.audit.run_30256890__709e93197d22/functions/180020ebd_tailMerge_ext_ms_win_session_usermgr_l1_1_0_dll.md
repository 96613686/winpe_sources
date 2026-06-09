# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x180020ebd`
- end: `0x180020f36`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020f3c`
- `0x180020f4e`
- `0x180020f60`

## callees

- `0x180018b30`
- `0x180020ebd`

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
0x180020ebd  mov     [rsp+arg_0], rcx
0x180020ec2  mov     [rsp+arg_8], rdx
0x180020ec7  mov     [rsp+arg_10], r8
0x180020ecc  mov     [rsp+arg_18], r9
0x180020ed1  sub     rsp, 68h
0x180020ed5  movdqa  [rsp+68h+var_48], xmm0
0x180020edb  movdqa  [rsp+68h+var_38], xmm1
0x180020ee1  movdqa  [rsp+68h+var_28], xmm2
0x180020ee7  movdqa  [rsp+68h+var_18], xmm3
0x180020eed  mov     rdx, rax
0x180020ef0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x180020ef7  call    __delayLoadHelper2
0x180020efc  movdqa  xmm0, [rsp+68h+var_48]
0x180020f02  movdqa  xmm1, [rsp+68h+var_38]
0x180020f08  movdqa  xmm2, [rsp+68h+var_28]
0x180020f0e  movdqa  xmm3, [rsp+68h+var_18]
0x180020f14  mov     rcx, [rsp+68h+arg_0]
0x180020f19  mov     rdx, [rsp+68h+arg_8]
0x180020f1e  mov     r8, [rsp+68h+arg_10]
0x180020f26  mov     r9, [rsp+68h+arg_18]
0x180020f2e  add     rsp, 68h
0x180020f32  jmp     short $+2
0x180020f34  jmp     rax
```
