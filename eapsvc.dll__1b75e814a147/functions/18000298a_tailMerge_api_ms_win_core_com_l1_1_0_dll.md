# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000298a`
- end: `0x180002a03`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a09`
- `0x180002a1b`
- `0x180002aca`
- `0x180002adc`
- `0x180002aee`

## callees

- `0x18000298a`
- `0x180014ce0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000298a  mov     [rsp+arg_0], rcx
0x18000298f  mov     [rsp+arg_8], rdx
0x180002994  mov     [rsp+arg_10], r8
0x180002999  mov     [rsp+arg_18], r9
0x18000299e  sub     rsp, 68h
0x1800029a2  movdqa  [rsp+68h+var_48], xmm0
0x1800029a8  movdqa  [rsp+68h+var_38], xmm1
0x1800029ae  movdqa  [rsp+68h+var_28], xmm2
0x1800029b4  movdqa  [rsp+68h+var_18], xmm3
0x1800029ba  mov     rdx, rax
0x1800029bd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x1800029c4  call    __delayLoadHelper2
0x1800029c9  movdqa  xmm0, [rsp+68h+var_48]
0x1800029cf  movdqa  xmm1, [rsp+68h+var_38]
0x1800029d5  movdqa  xmm2, [rsp+68h+var_28]
0x1800029db  movdqa  xmm3, [rsp+68h+var_18]
0x1800029e1  mov     rcx, [rsp+68h+arg_0]
0x1800029e6  mov     rdx, [rsp+68h+arg_8]
0x1800029eb  mov     r8, [rsp+68h+arg_10]
0x1800029f3  mov     r9, [rsp+68h+arg_18]
0x1800029fb  add     rsp, 68h
0x1800029ff  jmp     short $+2
0x180002a01  jmp     rax
```
