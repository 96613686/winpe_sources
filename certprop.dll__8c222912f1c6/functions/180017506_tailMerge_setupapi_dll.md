# __tailMerge_setupapi_dll

- ea: `0x180017506`
- end: `0x18001757f`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180017585`
- `0x180017597`
- `0x1800175a9`
- `0x1800175bb`
- `0x1800175cd`
- `0x1800175df`

## callees

- `0x18000e1a0`
- `0x180017506`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_setupapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180017506  mov     [rsp+arg_0], rcx
0x18001750b  mov     [rsp+arg_8], rdx
0x180017510  mov     [rsp+arg_10], r8
0x180017515  mov     [rsp+arg_18], r9
0x18001751a  sub     rsp, 68h
0x18001751e  movdqa  [rsp+68h+var_48], xmm0
0x180017524  movdqa  [rsp+68h+var_38], xmm1
0x18001752a  movdqa  [rsp+68h+var_28], xmm2
0x180017530  movdqa  [rsp+68h+var_18], xmm3
0x180017536  mov     rdx, rax
0x180017539  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x180017540  call    __delayLoadHelper2
0x180017545  movdqa  xmm0, [rsp+68h+var_48]
0x18001754b  movdqa  xmm1, [rsp+68h+var_38]
0x180017551  movdqa  xmm2, [rsp+68h+var_28]
0x180017557  movdqa  xmm3, [rsp+68h+var_18]
0x18001755d  mov     rcx, [rsp+68h+arg_0]
0x180017562  mov     rdx, [rsp+68h+arg_8]
0x180017567  mov     r8, [rsp+68h+arg_10]
0x18001756f  mov     r9, [rsp+68h+arg_18]
0x180017577  add     rsp, 68h
0x18001757b  jmp     short $+2
0x18001757d  jmp     rax
```
