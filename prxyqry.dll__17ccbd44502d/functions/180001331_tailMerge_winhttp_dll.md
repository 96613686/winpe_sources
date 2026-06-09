# __tailMerge_winhttp_dll

- ea: `0x180001331`
- end: `0x1800013aa`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013b0`
- `0x1800013c2`
- `0x1800013d4`
- `0x180001483`
- `0x180001495`

## callees

- `0x180001331`
- `0x180003100`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001331  mov     [rsp+arg_0], rcx
0x180001336  mov     [rsp+arg_8], rdx
0x18000133b  mov     [rsp+arg_10], r8
0x180001340  mov     [rsp+arg_18], r9
0x180001345  sub     rsp, 68h
0x180001349  movdqa  [rsp+68h+var_48], xmm0
0x18000134f  movdqa  [rsp+68h+var_38], xmm1
0x180001355  movdqa  [rsp+68h+var_28], xmm2
0x18000135b  movdqa  [rsp+68h+var_18], xmm3
0x180001361  mov     rdx, rax
0x180001364  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x18000136b  call    __delayLoadHelper2
0x180001370  movdqa  xmm0, [rsp+68h+var_48]
0x180001376  movdqa  xmm1, [rsp+68h+var_38]
0x18000137c  movdqa  xmm2, [rsp+68h+var_28]
0x180001382  movdqa  xmm3, [rsp+68h+var_18]
0x180001388  mov     rcx, [rsp+68h+arg_0]
0x18000138d  mov     rdx, [rsp+68h+arg_8]
0x180001392  mov     r8, [rsp+68h+arg_10]
0x18000139a  mov     r9, [rsp+68h+arg_18]
0x1800013a2  add     rsp, 68h
0x1800013a6  jmp     short $+2
0x1800013a8  jmp     rax
```
