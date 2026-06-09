# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll

- ea: `0x180001d91`
- end: `0x180001e0a`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e10`
- `0x180001e22`
- `0x180001e34`

## callees

- `0x180001d91`
- `0x180004f50`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d91  mov     [rsp+arg_0], rcx
0x180001d96  mov     [rsp+arg_8], rdx
0x180001d9b  mov     [rsp+arg_10], r8
0x180001da0  mov     [rsp+arg_18], r9
0x180001da5  sub     rsp, 68h
0x180001da9  movdqa  [rsp+68h+var_48], xmm0
0x180001daf  movdqa  [rsp+68h+var_38], xmm1
0x180001db5  movdqa  [rsp+68h+var_28], xmm2
0x180001dbb  movdqa  [rsp+68h+var_18], xmm3
0x180001dc1  mov     rdx, rax
0x180001dc4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll
0x180001dcb  call    __delayLoadHelper2
0x180001dd0  movdqa  xmm0, [rsp+68h+var_48]
0x180001dd6  movdqa  xmm1, [rsp+68h+var_38]
0x180001ddc  movdqa  xmm2, [rsp+68h+var_28]
0x180001de2  movdqa  xmm3, [rsp+68h+var_18]
0x180001de8  mov     rcx, [rsp+68h+arg_0]
0x180001ded  mov     rdx, [rsp+68h+arg_8]
0x180001df2  mov     r8, [rsp+68h+arg_10]
0x180001dfa  mov     r9, [rsp+68h+arg_18]
0x180001e02  add     rsp, 68h
0x180001e06  jmp     short $+2
0x180001e08  jmp     rax
```
