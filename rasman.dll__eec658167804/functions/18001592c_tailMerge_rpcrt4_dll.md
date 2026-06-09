# __tailMerge_rpcrt4_dll

- ea: `0x18001592c`
- end: `0x1800159a5`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800159ab`
- `0x1800159bd`
- `0x1800159cf`
- `0x180015d16`
- `0x180015d28`
- `0x180015d3a`
- `0x180015d4c`
- `0x180015d5e`

## callees

- `0x180014230`
- `0x18001592c`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001592c  mov     [rsp+arg_0], rcx
0x180015931  mov     [rsp+arg_8], rdx
0x180015936  mov     [rsp+arg_10], r8
0x18001593b  mov     [rsp+arg_18], r9
0x180015940  sub     rsp, 68h
0x180015944  movdqa  [rsp+68h+var_48], xmm0
0x18001594a  movdqa  [rsp+68h+var_38], xmm1
0x180015950  movdqa  [rsp+68h+var_28], xmm2
0x180015956  movdqa  [rsp+68h+var_18], xmm3
0x18001595c  mov     rdx, rax
0x18001595f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180015966  call    __delayLoadHelper2
0x18001596b  movdqa  xmm0, [rsp+68h+var_48]
0x180015971  movdqa  xmm1, [rsp+68h+var_38]
0x180015977  movdqa  xmm2, [rsp+68h+var_28]
0x18001597d  movdqa  xmm3, [rsp+68h+var_18]
0x180015983  mov     rcx, [rsp+68h+arg_0]
0x180015988  mov     rdx, [rsp+68h+arg_8]
0x18001598d  mov     r8, [rsp+68h+arg_10]
0x180015995  mov     r9, [rsp+68h+arg_18]
0x18001599d  add     rsp, 68h
0x1800159a1  jmp     short $+2
0x1800159a3  jmp     rax
```
