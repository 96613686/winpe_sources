# __tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll

- ea: `0x1800022c5`
- end: `0x18000233e`
- name: `__tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002344`
- `0x1800023f3`

## callees

- `0x1800022c5`
- `0x180018ae0`

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
0x1800022c5  mov     [rsp+arg_0], rcx
0x1800022ca  mov     [rsp+arg_8], rdx
0x1800022cf  mov     [rsp+arg_10], r8
0x1800022d4  mov     [rsp+arg_18], r9
0x1800022d9  sub     rsp, 68h
0x1800022dd  movdqa  [rsp+68h+var_48], xmm0
0x1800022e3  movdqa  [rsp+68h+var_38], xmm1
0x1800022e9  movdqa  [rsp+68h+var_28], xmm2
0x1800022ef  movdqa  [rsp+68h+var_18], xmm3
0x1800022f5  mov     rdx, rax
0x1800022f8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_1_dll
0x1800022ff  call    __delayLoadHelper2
0x180002304  movdqa  xmm0, [rsp+68h+var_48]
0x18000230a  movdqa  xmm1, [rsp+68h+var_38]
0x180002310  movdqa  xmm2, [rsp+68h+var_28]
0x180002316  movdqa  xmm3, [rsp+68h+var_18]
0x18000231c  mov     rcx, [rsp+68h+arg_0]
0x180002321  mov     rdx, [rsp+68h+arg_8]
0x180002326  mov     r8, [rsp+68h+arg_10]
0x18000232e  mov     r9, [rsp+68h+arg_18]
0x180002336  add     rsp, 68h
0x18000233a  jmp     short $+2
0x18000233c  jmp     rax
```
