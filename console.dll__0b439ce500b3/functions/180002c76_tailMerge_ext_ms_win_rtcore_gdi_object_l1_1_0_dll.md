# __tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll

- ea: `0x180002c76`
- end: `0x180002cef`
- name: `__tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002cf5`

## callees

- `0x180002c76`
- `0x180018ae0`

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
0x180002c76  mov     [rsp+arg_0], rcx
0x180002c7b  mov     [rsp+arg_8], rdx
0x180002c80  mov     [rsp+arg_10], r8
0x180002c85  mov     [rsp+arg_18], r9
0x180002c8a  sub     rsp, 68h
0x180002c8e  movdqa  [rsp+68h+var_48], xmm0
0x180002c94  movdqa  [rsp+68h+var_38], xmm1
0x180002c9a  movdqa  [rsp+68h+var_28], xmm2
0x180002ca0  movdqa  [rsp+68h+var_18], xmm3
0x180002ca6  mov     rdx, rax
0x180002ca9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_gdi_object_l1_1_0_dll
0x180002cb0  call    __delayLoadHelper2
0x180002cb5  movdqa  xmm0, [rsp+68h+var_48]
0x180002cbb  movdqa  xmm1, [rsp+68h+var_38]
0x180002cc1  movdqa  xmm2, [rsp+68h+var_28]
0x180002cc7  movdqa  xmm3, [rsp+68h+var_18]
0x180002ccd  mov     rcx, [rsp+68h+arg_0]
0x180002cd2  mov     rdx, [rsp+68h+arg_8]
0x180002cd7  mov     r8, [rsp+68h+arg_10]
0x180002cdf  mov     r9, [rsp+68h+arg_18]
0x180002ce7  add     rsp, 68h
0x180002ceb  jmp     short $+2
0x180002ced  jmp     rax
```
