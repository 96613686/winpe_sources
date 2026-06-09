# __tailMerge_ws2_32_dll

- ea: `0x180001950`
- end: `0x1800019c9`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019cf`
- `0x1800019e1`
- `0x1800019f3`

## callees

- `0x180001950`
- `0x180002c40`

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
0x180001950  mov     [rsp+arg_0], rcx
0x180001955  mov     [rsp+arg_8], rdx
0x18000195a  mov     [rsp+arg_10], r8
0x18000195f  mov     [rsp+arg_18], r9
0x180001964  sub     rsp, 68h
0x180001968  movdqa  [rsp+68h+var_48], xmm0
0x18000196e  movdqa  [rsp+68h+var_38], xmm1
0x180001974  movdqa  [rsp+68h+var_28], xmm2
0x18000197a  movdqa  [rsp+68h+var_18], xmm3
0x180001980  mov     rdx, rax
0x180001983  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18000198a  call    __delayLoadHelper2
0x18000198f  movdqa  xmm0, [rsp+68h+var_48]
0x180001995  movdqa  xmm1, [rsp+68h+var_38]
0x18000199b  movdqa  xmm2, [rsp+68h+var_28]
0x1800019a1  movdqa  xmm3, [rsp+68h+var_18]
0x1800019a7  mov     rcx, [rsp+68h+arg_0]
0x1800019ac  mov     rdx, [rsp+68h+arg_8]
0x1800019b1  mov     r8, [rsp+68h+arg_10]
0x1800019b9  mov     r9, [rsp+68h+arg_18]
0x1800019c1  add     rsp, 68h
0x1800019c5  jmp     short $+2
0x1800019c7  jmp     rax
```
