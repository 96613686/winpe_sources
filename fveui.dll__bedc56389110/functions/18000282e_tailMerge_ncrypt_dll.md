# __tailMerge_ncrypt_dll

- ea: `0x18000282e`
- end: `0x1800028a7`
- name: `__tailMerge_ncrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800028ad`
- `0x1800028bf`
- `0x1800028d1`
- `0x1800028e3`
- `0x1800028f5`

## callees

- `0x18000282e`
- `0x18002b720`

## pseudocode

```c
__int64 __fastcall _tailMerge_ncrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ncrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000282e  mov     [rsp+arg_0], rcx
0x180002833  mov     [rsp+arg_8], rdx
0x180002838  mov     [rsp+arg_10], r8
0x18000283d  mov     [rsp+arg_18], r9
0x180002842  sub     rsp, 68h
0x180002846  movdqa  [rsp+68h+var_48], xmm0
0x18000284c  movdqa  [rsp+68h+var_38], xmm1
0x180002852  movdqa  [rsp+68h+var_28], xmm2
0x180002858  movdqa  [rsp+68h+var_18], xmm3
0x18000285e  mov     rdx, rax
0x180002861  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ncrypt_dll
0x180002868  call    __delayLoadHelper2
0x18000286d  movdqa  xmm0, [rsp+68h+var_48]
0x180002873  movdqa  xmm1, [rsp+68h+var_38]
0x180002879  movdqa  xmm2, [rsp+68h+var_28]
0x18000287f  movdqa  xmm3, [rsp+68h+var_18]
0x180002885  mov     rcx, [rsp+68h+arg_0]
0x18000288a  mov     rdx, [rsp+68h+arg_8]
0x18000288f  mov     r8, [rsp+68h+arg_10]
0x180002897  mov     r9, [rsp+68h+arg_18]
0x18000289f  add     rsp, 68h
0x1800028a3  jmp     short $+2
0x1800028a5  jmp     rax
```
