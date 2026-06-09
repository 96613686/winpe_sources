# __tailMerge_ncrypt_dll

- ea: `0x18000b1ad`
- end: `0x18000b226`
- name: `__tailMerge_ncrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b22c`
- `0x18000b23e`
- `0x18000b250`

## callees

- `0x1800079c0`
- `0x18000b1ad`

## pseudocode

```c
__int64 __fastcall _tailMerge_ncrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ncrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b1ad  mov     [rsp+arg_0], rcx
0x18000b1b2  mov     [rsp+arg_8], rdx
0x18000b1b7  mov     [rsp+arg_10], r8
0x18000b1bc  mov     [rsp+arg_18], r9
0x18000b1c1  sub     rsp, 68h
0x18000b1c5  movdqa  [rsp+68h+var_48], xmm0
0x18000b1cb  movdqa  [rsp+68h+var_38], xmm1
0x18000b1d1  movdqa  [rsp+68h+var_28], xmm2
0x18000b1d7  movdqa  [rsp+68h+var_18], xmm3
0x18000b1dd  mov     rdx, rax
0x18000b1e0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ncrypt_dll
0x18000b1e7  call    __delayLoadHelper2
0x18000b1ec  movdqa  xmm0, [rsp+68h+var_48]
0x18000b1f2  movdqa  xmm1, [rsp+68h+var_38]
0x18000b1f8  movdqa  xmm2, [rsp+68h+var_28]
0x18000b1fe  movdqa  xmm3, [rsp+68h+var_18]
0x18000b204  mov     rcx, [rsp+68h+arg_0]
0x18000b209  mov     rdx, [rsp+68h+arg_8]
0x18000b20e  mov     r8, [rsp+68h+arg_10]
0x18000b216  mov     r9, [rsp+68h+arg_18]
0x18000b21e  add     rsp, 68h
0x18000b222  jmp     short $+2
0x18000b224  jmp     rax
```
