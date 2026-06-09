# __tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll

- ea: `0x180009d1b`
- end: `0x180009d94`
- name: `__tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009d9a`

## callees

- `0x180007cb0`
- `0x180009d1b`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009d1b  mov     [rsp+arg_0], rcx
0x180009d20  mov     [rsp+arg_8], rdx
0x180009d25  mov     [rsp+arg_10], r8
0x180009d2a  mov     [rsp+arg_18], r9
0x180009d2f  sub     rsp, 68h
0x180009d33  movdqa  [rsp+68h+var_48], xmm0
0x180009d39  movdqa  [rsp+68h+var_38], xmm1
0x180009d3f  movdqa  [rsp+68h+var_28], xmm2
0x180009d45  movdqa  [rsp+68h+var_18], xmm3
0x180009d4b  mov     rdx, rax
0x180009d4e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_1_dll
0x180009d55  call    __delayLoadHelper2
0x180009d5a  movdqa  xmm0, [rsp+68h+var_48]
0x180009d60  movdqa  xmm1, [rsp+68h+var_38]
0x180009d66  movdqa  xmm2, [rsp+68h+var_28]
0x180009d6c  movdqa  xmm3, [rsp+68h+var_18]
0x180009d72  mov     rcx, [rsp+68h+arg_0]
0x180009d77  mov     rdx, [rsp+68h+arg_8]
0x180009d7c  mov     r8, [rsp+68h+arg_10]
0x180009d84  mov     r9, [rsp+68h+arg_18]
0x180009d8c  add     rsp, 68h
0x180009d90  jmp     short $+2
0x180009d92  jmp     rax
```
