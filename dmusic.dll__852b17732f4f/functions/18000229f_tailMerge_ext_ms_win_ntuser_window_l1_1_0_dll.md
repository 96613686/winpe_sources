# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x18000229f`
- end: `0x180002318`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000231e`
- `0x180002330`
- `0x180002342`

## callees

- `0x18000229f`
- `0x1800215a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000229f  mov     [rsp+arg_0], rcx
0x1800022a4  mov     [rsp+arg_8], rdx
0x1800022a9  mov     [rsp+arg_10], r8
0x1800022ae  mov     [rsp+arg_18], r9
0x1800022b3  sub     rsp, 68h
0x1800022b7  movdqa  [rsp+68h+var_48], xmm0
0x1800022bd  movdqa  [rsp+68h+var_38], xmm1
0x1800022c3  movdqa  [rsp+68h+var_28], xmm2
0x1800022c9  movdqa  [rsp+68h+var_18], xmm3
0x1800022cf  mov     rdx, rax
0x1800022d2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x1800022d9  call    __delayLoadHelper2
0x1800022de  movdqa  xmm0, [rsp+68h+var_48]
0x1800022e4  movdqa  xmm1, [rsp+68h+var_38]
0x1800022ea  movdqa  xmm2, [rsp+68h+var_28]
0x1800022f0  movdqa  xmm3, [rsp+68h+var_18]
0x1800022f6  mov     rcx, [rsp+68h+arg_0]
0x1800022fb  mov     rdx, [rsp+68h+arg_8]
0x180002300  mov     r8, [rsp+68h+arg_10]
0x180002308  mov     r9, [rsp+68h+arg_18]
0x180002310  add     rsp, 68h
0x180002314  jmp     short $+2
0x180002316  jmp     rax
```
