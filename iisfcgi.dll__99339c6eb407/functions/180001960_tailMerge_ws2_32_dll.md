# __tailMerge_ws2_32_dll

- ea: `0x180001960`
- end: `0x1800019d9`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019df`
- `0x1800019f1`
- `0x180001ab2`
- `0x180001ac4`
- `0x180001ad6`
- `0x180001ae8`
- `0x180001afa`
- `0x180001b0c`
- `0x180001b1e`
- `0x180001b30`
- `0x180001b42`
- `0x180001b54`
- `0x180001b66`

## callees

- `0x180001960`
- `0x18000ecf0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001960  mov     [rsp+arg_0], rcx
0x180001965  mov     [rsp+arg_8], rdx
0x18000196a  mov     [rsp+arg_10], r8
0x18000196f  mov     [rsp+arg_18], r9
0x180001974  sub     rsp, 68h
0x180001978  movdqa  [rsp+68h+var_48], xmm0
0x18000197e  movdqa  [rsp+68h+var_38], xmm1
0x180001984  movdqa  [rsp+68h+var_28], xmm2
0x18000198a  movdqa  [rsp+68h+var_18], xmm3
0x180001990  mov     rdx, rax
0x180001993  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18000199a  call    __delayLoadHelper2
0x18000199f  movdqa  xmm0, [rsp+68h+var_48]
0x1800019a5  movdqa  xmm1, [rsp+68h+var_38]
0x1800019ab  movdqa  xmm2, [rsp+68h+var_28]
0x1800019b1  movdqa  xmm3, [rsp+68h+var_18]
0x1800019b7  mov     rcx, [rsp+68h+arg_0]
0x1800019bc  mov     rdx, [rsp+68h+arg_8]
0x1800019c1  mov     r8, [rsp+68h+arg_10]
0x1800019c9  mov     r9, [rsp+68h+arg_18]
0x1800019d1  add     rsp, 68h
0x1800019d5  jmp     short $+2
0x1800019d7  jmp     rax
```
