# __tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll

- ea: `0x180001db9`
- end: `0x180001e32`
- name: `__tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e38`

## callees

- `0x180001db9`
- `0x180010f60`

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
0x180001db9  mov     [rsp+arg_0], rcx
0x180001dbe  mov     [rsp+arg_8], rdx
0x180001dc3  mov     [rsp+arg_10], r8
0x180001dc8  mov     [rsp+arg_18], r9
0x180001dcd  sub     rsp, 68h
0x180001dd1  movdqa  [rsp+68h+var_48], xmm0
0x180001dd7  movdqa  [rsp+68h+var_38], xmm1
0x180001ddd  movdqa  [rsp+68h+var_28], xmm2
0x180001de3  movdqa  [rsp+68h+var_18], xmm3
0x180001de9  mov     rdx, rax
0x180001dec  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_1_dll
0x180001df3  call    __delayLoadHelper2
0x180001df8  movdqa  xmm0, [rsp+68h+var_48]
0x180001dfe  movdqa  xmm1, [rsp+68h+var_38]
0x180001e04  movdqa  xmm2, [rsp+68h+var_28]
0x180001e0a  movdqa  xmm3, [rsp+68h+var_18]
0x180001e10  mov     rcx, [rsp+68h+arg_0]
0x180001e15  mov     rdx, [rsp+68h+arg_8]
0x180001e1a  mov     r8, [rsp+68h+arg_10]
0x180001e22  mov     r9, [rsp+68h+arg_18]
0x180001e2a  add     rsp, 68h
0x180001e2e  jmp     short $+2
0x180001e30  jmp     rax
```
