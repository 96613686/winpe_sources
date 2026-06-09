# __tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll

- ea: `0x180002d8c`
- end: `0x180002e05`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e0b`
- `0x180002e1d`

## callees

- `0x180002d8c`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002d8c  mov     [rsp+arg_0], rcx
0x180002d91  mov     [rsp+arg_8], rdx
0x180002d96  mov     [rsp+arg_10], r8
0x180002d9b  mov     [rsp+arg_18], r9
0x180002da0  sub     rsp, 68h
0x180002da4  movdqa  [rsp+68h+var_48], xmm0
0x180002daa  movdqa  [rsp+68h+var_38], xmm1
0x180002db0  movdqa  [rsp+68h+var_28], xmm2
0x180002db6  movdqa  [rsp+68h+var_18], xmm3
0x180002dbc  mov     rdx, rax
0x180002dbf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll
0x180002dc6  call    __delayLoadHelper2
0x180002dcb  movdqa  xmm0, [rsp+68h+var_48]
0x180002dd1  movdqa  xmm1, [rsp+68h+var_38]
0x180002dd7  movdqa  xmm2, [rsp+68h+var_28]
0x180002ddd  movdqa  xmm3, [rsp+68h+var_18]
0x180002de3  mov     rcx, [rsp+68h+arg_0]
0x180002de8  mov     rdx, [rsp+68h+arg_8]
0x180002ded  mov     r8, [rsp+68h+arg_10]
0x180002df5  mov     r9, [rsp+68h+arg_18]
0x180002dfd  add     rsp, 68h
0x180002e01  jmp     short $+2
0x180002e03  jmp     rax
```
