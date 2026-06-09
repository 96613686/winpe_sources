# __tailMerge_advapi32_dll

- ea: `0x140001e00`
- end: `0x140001e79`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001e7f`
- `0x140001e91`
- `0x140001ea3`

## callees

- `0x140001e00`
- `0x140006d20`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001e00  mov     [rsp+arg_0], rcx
0x140001e05  mov     [rsp+arg_8], rdx
0x140001e0a  mov     [rsp+arg_10], r8
0x140001e0f  mov     [rsp+arg_18], r9
0x140001e14  sub     rsp, 68h
0x140001e18  movdqa  [rsp+68h+var_48], xmm0
0x140001e1e  movdqa  [rsp+68h+var_38], xmm1
0x140001e24  movdqa  [rsp+68h+var_28], xmm2
0x140001e2a  movdqa  [rsp+68h+var_18], xmm3
0x140001e30  mov     rdx, rax
0x140001e33  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x140001e3a  call    __delayLoadHelper2
0x140001e3f  movdqa  xmm0, [rsp+68h+var_48]
0x140001e45  movdqa  xmm1, [rsp+68h+var_38]
0x140001e4b  movdqa  xmm2, [rsp+68h+var_28]
0x140001e51  movdqa  xmm3, [rsp+68h+var_18]
0x140001e57  mov     rcx, [rsp+68h+arg_0]
0x140001e5c  mov     rdx, [rsp+68h+arg_8]
0x140001e61  mov     r8, [rsp+68h+arg_10]
0x140001e69  mov     r9, [rsp+68h+arg_18]
0x140001e71  add     rsp, 68h
0x140001e75  jmp     short $+2
0x140001e77  jmp     rax
```
