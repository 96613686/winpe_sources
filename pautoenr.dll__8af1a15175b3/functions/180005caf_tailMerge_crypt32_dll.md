# __tailMerge_crypt32_dll

- ea: `0x180005caf`
- end: `0x180005d28`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005d2e`
- `0x180005d40`
- `0x180005d52`
- `0x180005d64`
- `0x180005d76`
- `0x180005d88`
- `0x180005d9a`
- `0x180005dac`
- `0x180005dbe`
- `0x180006001`
- `0x1800060c2`
- `0x1800060d4`
- `0x1800060e6`
- `0x1800060f8`
- `0x18000610a`
- `0x18000611c`
- `0x18000612e`

## callees

- `0x1800046b0`
- `0x180005caf`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005caf  mov     [rsp+arg_0], rcx
0x180005cb4  mov     [rsp+arg_8], rdx
0x180005cb9  mov     [rsp+arg_10], r8
0x180005cbe  mov     [rsp+arg_18], r9
0x180005cc3  sub     rsp, 68h
0x180005cc7  movdqa  [rsp+68h+var_48], xmm0
0x180005ccd  movdqa  [rsp+68h+var_38], xmm1
0x180005cd3  movdqa  [rsp+68h+var_28], xmm2
0x180005cd9  movdqa  [rsp+68h+var_18], xmm3
0x180005cdf  mov     rdx, rax
0x180005ce2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180005ce9  call    __delayLoadHelper2
0x180005cee  movdqa  xmm0, [rsp+68h+var_48]
0x180005cf4  movdqa  xmm1, [rsp+68h+var_38]
0x180005cfa  movdqa  xmm2, [rsp+68h+var_28]
0x180005d00  movdqa  xmm3, [rsp+68h+var_18]
0x180005d06  mov     rcx, [rsp+68h+arg_0]
0x180005d0b  mov     rdx, [rsp+68h+arg_8]
0x180005d10  mov     r8, [rsp+68h+arg_10]
0x180005d18  mov     r9, [rsp+68h+arg_18]
0x180005d20  add     rsp, 68h
0x180005d24  jmp     short $+2
0x180005d26  jmp     rax
```
