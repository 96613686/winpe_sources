# __tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll

- ea: `0x18000a811`
- end: `0x18000a88a`
- name: `__tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a890`

## callees

- `0x180007cb0`
- `0x18000a811`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_gdi_object_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a811  mov     [rsp+arg_0], rcx
0x18000a816  mov     [rsp+arg_8], rdx
0x18000a81b  mov     [rsp+arg_10], r8
0x18000a820  mov     [rsp+arg_18], r9
0x18000a825  sub     rsp, 68h
0x18000a829  movdqa  [rsp+68h+var_48], xmm0
0x18000a82f  movdqa  [rsp+68h+var_38], xmm1
0x18000a835  movdqa  [rsp+68h+var_28], xmm2
0x18000a83b  movdqa  [rsp+68h+var_18], xmm3
0x18000a841  mov     rdx, rax
0x18000a844  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_gdi_object_l1_1_0_dll
0x18000a84b  call    __delayLoadHelper2
0x18000a850  movdqa  xmm0, [rsp+68h+var_48]
0x18000a856  movdqa  xmm1, [rsp+68h+var_38]
0x18000a85c  movdqa  xmm2, [rsp+68h+var_28]
0x18000a862  movdqa  xmm3, [rsp+68h+var_18]
0x18000a868  mov     rcx, [rsp+68h+arg_0]
0x18000a86d  mov     rdx, [rsp+68h+arg_8]
0x18000a872  mov     r8, [rsp+68h+arg_10]
0x18000a87a  mov     r9, [rsp+68h+arg_18]
0x18000a882  add     rsp, 68h
0x18000a886  jmp     short $+2
0x18000a888  jmp     rax
```
