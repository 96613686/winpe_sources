# __tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll

- ea: `0x180002228`
- end: `0x1800022a1`
- name: `__tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022a7`
- `0x1800022b9`

## callees

- `0x180002228`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_create_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002228  mov     [rsp+arg_0], rcx
0x18000222d  mov     [rsp+arg_8], rdx
0x180002232  mov     [rsp+arg_10], r8
0x180002237  mov     [rsp+arg_18], r9
0x18000223c  sub     rsp, 68h
0x180002240  movdqa  [rsp+68h+var_48], xmm0
0x180002246  movdqa  [rsp+68h+var_38], xmm1
0x18000224c  movdqa  [rsp+68h+var_28], xmm2
0x180002252  movdqa  [rsp+68h+var_18], xmm3
0x180002258  mov     rdx, rax
0x18000225b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_create_l1_1_0_dll
0x180002262  call    __delayLoadHelper2
0x180002267  movdqa  xmm0, [rsp+68h+var_48]
0x18000226d  movdqa  xmm1, [rsp+68h+var_38]
0x180002273  movdqa  xmm2, [rsp+68h+var_28]
0x180002279  movdqa  xmm3, [rsp+68h+var_18]
0x18000227f  mov     rcx, [rsp+68h+arg_0]
0x180002284  mov     rdx, [rsp+68h+arg_8]
0x180002289  mov     r8, [rsp+68h+arg_10]
0x180002291  mov     r9, [rsp+68h+arg_18]
0x180002299  add     rsp, 68h
0x18000229d  jmp     short $+2
0x18000229f  jmp     rax
```
