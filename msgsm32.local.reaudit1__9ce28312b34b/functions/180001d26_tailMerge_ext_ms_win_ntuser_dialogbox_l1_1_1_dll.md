# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll

- ea: `0x180001d26`
- end: `0x180001d9f`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001da5`

## callees

- `0x180001d26`
- `0x1800063b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d26  mov     [rsp+arg_0], rcx
0x180001d2b  mov     [rsp+arg_8], rdx
0x180001d30  mov     [rsp+arg_10], r8
0x180001d35  mov     [rsp+arg_18], r9
0x180001d3a  sub     rsp, 68h
0x180001d3e  movdqa  [rsp+68h+var_48], xmm0
0x180001d44  movdqa  [rsp+68h+var_38], xmm1
0x180001d4a  movdqa  [rsp+68h+var_28], xmm2
0x180001d50  movdqa  [rsp+68h+var_18], xmm3
0x180001d56  mov     rdx, rax
0x180001d59  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_1_dll
0x180001d60  call    __delayLoadHelper2
0x180001d65  movdqa  xmm0, [rsp+68h+var_48]
0x180001d6b  movdqa  xmm1, [rsp+68h+var_38]
0x180001d71  movdqa  xmm2, [rsp+68h+var_28]
0x180001d77  movdqa  xmm3, [rsp+68h+var_18]
0x180001d7d  mov     rcx, [rsp+68h+arg_0]
0x180001d82  mov     rdx, [rsp+68h+arg_8]
0x180001d87  mov     r8, [rsp+68h+arg_10]
0x180001d8f  mov     r9, [rsp+68h+arg_18]
0x180001d97  add     rsp, 68h
0x180001d9b  jmp     short $+2
0x180001d9d  jmp     rax
```
