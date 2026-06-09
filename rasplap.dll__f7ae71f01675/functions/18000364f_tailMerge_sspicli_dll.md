# __tailMerge_sspicli_dll

- ea: `0x18000364f`
- end: `0x1800036c8`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800036ce`
- `0x1800036e0`
- `0x1800036f2`

## callees

- `0x1800015c0`
- `0x18000364f`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000364f  mov     [rsp+arg_0], rcx
0x180003654  mov     [rsp+arg_8], rdx
0x180003659  mov     [rsp+arg_10], r8
0x18000365e  mov     [rsp+arg_18], r9
0x180003663  sub     rsp, 68h
0x180003667  movdqa  [rsp+68h+var_48], xmm0
0x18000366d  movdqa  [rsp+68h+var_38], xmm1
0x180003673  movdqa  [rsp+68h+var_28], xmm2
0x180003679  movdqa  [rsp+68h+var_18], xmm3
0x18000367f  mov     rdx, rax
0x180003682  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180003689  call    __delayLoadHelper2
0x18000368e  movdqa  xmm0, [rsp+68h+var_48]
0x180003694  movdqa  xmm1, [rsp+68h+var_38]
0x18000369a  movdqa  xmm2, [rsp+68h+var_28]
0x1800036a0  movdqa  xmm3, [rsp+68h+var_18]
0x1800036a6  mov     rcx, [rsp+68h+arg_0]
0x1800036ab  mov     rdx, [rsp+68h+arg_8]
0x1800036b0  mov     r8, [rsp+68h+arg_10]
0x1800036b8  mov     r9, [rsp+68h+arg_18]
0x1800036c0  add     rsp, 68h
0x1800036c4  jmp     short $+2
0x1800036c6  jmp     rax
```
