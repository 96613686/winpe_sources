# __tailMerge_winhttp_dll

- ea: `0x18000ad9b`
- end: `0x18000ae14`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ae1a`
- `0x18000ae2c`
- `0x18000ae3e`
- `0x18000ae50`
- `0x18000ae62`
- `0x18000ae74`
- `0x18000ae86`
- `0x18000ae98`
- `0x18000aeaa`
- `0x18000aebc`
- `0x18000aece`
- `0x18000aee0`

## callees

- `0x1800079c0`
- `0x18000ad9b`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ad9b  mov     [rsp+arg_0], rcx
0x18000ada0  mov     [rsp+arg_8], rdx
0x18000ada5  mov     [rsp+arg_10], r8
0x18000adaa  mov     [rsp+arg_18], r9
0x18000adaf  sub     rsp, 68h
0x18000adb3  movdqa  [rsp+68h+var_48], xmm0
0x18000adb9  movdqa  [rsp+68h+var_38], xmm1
0x18000adbf  movdqa  [rsp+68h+var_28], xmm2
0x18000adc5  movdqa  [rsp+68h+var_18], xmm3
0x18000adcb  mov     rdx, rax
0x18000adce  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x18000add5  call    __delayLoadHelper2
0x18000adda  movdqa  xmm0, [rsp+68h+var_48]
0x18000ade0  movdqa  xmm1, [rsp+68h+var_38]
0x18000ade6  movdqa  xmm2, [rsp+68h+var_28]
0x18000adec  movdqa  xmm3, [rsp+68h+var_18]
0x18000adf2  mov     rcx, [rsp+68h+arg_0]
0x18000adf7  mov     rdx, [rsp+68h+arg_8]
0x18000adfc  mov     r8, [rsp+68h+arg_10]
0x18000ae04  mov     r9, [rsp+68h+arg_18]
0x18000ae0c  add     rsp, 68h
0x18000ae10  jmp     short $+2
0x18000ae12  jmp     rax
```
