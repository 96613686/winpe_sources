# __tailMerge_wldap32_dll

- ea: `0x18000deb3`
- end: `0x18000df2c`
- name: `__tailMerge_wldap32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000df32`
- `0x18000df44`
- `0x18000df56`
- `0x18000df68`
- `0x18000df7a`
- `0x18000df8c`
- `0x18000df9e`
- `0x18000dfb0`
- `0x18000dfc2`
- `0x18000dfd4`
- `0x18000dfe6`
- `0x18000dff8`
- `0x18000e00a`
- `0x18000e01c`
- `0x18000e02e`
- `0x18000e040`
- `0x18000e052`
- `0x18000e064`

## callees

- `0x18000bd60`
- `0x18000deb3`

## pseudocode

```c
__int64 __fastcall _tailMerge_wldap32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wldap32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000deb3  mov     [rsp+arg_0], rcx
0x18000deb8  mov     [rsp+arg_8], rdx
0x18000debd  mov     [rsp+arg_10], r8
0x18000dec2  mov     [rsp+arg_18], r9
0x18000dec7  sub     rsp, 68h
0x18000decb  movdqa  [rsp+68h+var_48], xmm0
0x18000ded1  movdqa  [rsp+68h+var_38], xmm1
0x18000ded7  movdqa  [rsp+68h+var_28], xmm2
0x18000dedd  movdqa  [rsp+68h+var_18], xmm3
0x18000dee3  mov     rdx, rax
0x18000dee6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wldap32_dll
0x18000deed  call    __delayLoadHelper2
0x18000def2  movdqa  xmm0, [rsp+68h+var_48]
0x18000def8  movdqa  xmm1, [rsp+68h+var_38]
0x18000defe  movdqa  xmm2, [rsp+68h+var_28]
0x18000df04  movdqa  xmm3, [rsp+68h+var_18]
0x18000df0a  mov     rcx, [rsp+68h+arg_0]
0x18000df0f  mov     rdx, [rsp+68h+arg_8]
0x18000df14  mov     r8, [rsp+68h+arg_10]
0x18000df1c  mov     r9, [rsp+68h+arg_18]
0x18000df24  add     rsp, 68h
0x18000df28  jmp     short $+2
0x18000df2a  jmp     rax
```
