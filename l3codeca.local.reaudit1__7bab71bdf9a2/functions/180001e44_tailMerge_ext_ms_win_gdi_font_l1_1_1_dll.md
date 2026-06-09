# __tailMerge_ext_ms_win_gdi_font_l1_1_1_dll

- ea: `0x180001e44`
- end: `0x180001ebd`
- name: `__tailMerge_ext_ms_win_gdi_font_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ec3`

## callees

- `0x180001e44`
- `0x180010f60`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_font_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e44  mov     [rsp+arg_0], rcx
0x180001e49  mov     [rsp+arg_8], rdx
0x180001e4e  mov     [rsp+arg_10], r8
0x180001e53  mov     [rsp+arg_18], r9
0x180001e58  sub     rsp, 68h
0x180001e5c  movdqa  [rsp+68h+var_48], xmm0
0x180001e62  movdqa  [rsp+68h+var_38], xmm1
0x180001e68  movdqa  [rsp+68h+var_28], xmm2
0x180001e6e  movdqa  [rsp+68h+var_18], xmm3
0x180001e74  mov     rdx, rax
0x180001e77  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_1_dll
0x180001e7e  call    __delayLoadHelper2
0x180001e83  movdqa  xmm0, [rsp+68h+var_48]
0x180001e89  movdqa  xmm1, [rsp+68h+var_38]
0x180001e8f  movdqa  xmm2, [rsp+68h+var_28]
0x180001e95  movdqa  xmm3, [rsp+68h+var_18]
0x180001e9b  mov     rcx, [rsp+68h+arg_0]
0x180001ea0  mov     rdx, [rsp+68h+arg_8]
0x180001ea5  mov     r8, [rsp+68h+arg_10]
0x180001ead  mov     r9, [rsp+68h+arg_18]
0x180001eb5  add     rsp, 68h
0x180001eb9  jmp     short $+2
0x180001ebb  jmp     rax
```
