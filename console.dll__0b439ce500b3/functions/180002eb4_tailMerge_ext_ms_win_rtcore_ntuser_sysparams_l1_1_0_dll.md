# __tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll

- ea: `0x180002eb4`
- end: `0x180002f2d`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f33`
- `0x180002f45`

## callees

- `0x180002eb4`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002eb4  mov     [rsp+arg_0], rcx
0x180002eb9  mov     [rsp+arg_8], rdx
0x180002ebe  mov     [rsp+arg_10], r8
0x180002ec3  mov     [rsp+arg_18], r9
0x180002ec8  sub     rsp, 68h
0x180002ecc  movdqa  [rsp+68h+var_48], xmm0
0x180002ed2  movdqa  [rsp+68h+var_38], xmm1
0x180002ed8  movdqa  [rsp+68h+var_28], xmm2
0x180002ede  movdqa  [rsp+68h+var_18], xmm3
0x180002ee4  mov     rdx, rax
0x180002ee7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll
0x180002eee  call    __delayLoadHelper2
0x180002ef3  movdqa  xmm0, [rsp+68h+var_48]
0x180002ef9  movdqa  xmm1, [rsp+68h+var_38]
0x180002eff  movdqa  xmm2, [rsp+68h+var_28]
0x180002f05  movdqa  xmm3, [rsp+68h+var_18]
0x180002f0b  mov     rcx, [rsp+68h+arg_0]
0x180002f10  mov     rdx, [rsp+68h+arg_8]
0x180002f15  mov     r8, [rsp+68h+arg_10]
0x180002f1d  mov     r9, [rsp+68h+arg_18]
0x180002f25  add     rsp, 68h
0x180002f29  jmp     short $+2
0x180002f2b  jmp     rax
```
