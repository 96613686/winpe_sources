# __tailMerge_dsrole_dll

- ea: `0x180015bb2`
- end: `0x180015c2b`
- name: `__tailMerge_dsrole_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015c31`
- `0x180015c43`

## callees

- `0x180014230`
- `0x180015bb2`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsrole_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_dsrole_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015bb2  mov     [rsp+arg_0], rcx
0x180015bb7  mov     [rsp+arg_8], rdx
0x180015bbc  mov     [rsp+arg_10], r8
0x180015bc1  mov     [rsp+arg_18], r9
0x180015bc6  sub     rsp, 68h
0x180015bca  movdqa  [rsp+68h+var_48], xmm0
0x180015bd0  movdqa  [rsp+68h+var_38], xmm1
0x180015bd6  movdqa  [rsp+68h+var_28], xmm2
0x180015bdc  movdqa  [rsp+68h+var_18], xmm3
0x180015be2  mov     rdx, rax
0x180015be5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsrole_dll
0x180015bec  call    __delayLoadHelper2
0x180015bf1  movdqa  xmm0, [rsp+68h+var_48]
0x180015bf7  movdqa  xmm1, [rsp+68h+var_38]
0x180015bfd  movdqa  xmm2, [rsp+68h+var_28]
0x180015c03  movdqa  xmm3, [rsp+68h+var_18]
0x180015c09  mov     rcx, [rsp+68h+arg_0]
0x180015c0e  mov     rdx, [rsp+68h+arg_8]
0x180015c13  mov     r8, [rsp+68h+arg_10]
0x180015c1b  mov     r9, [rsp+68h+arg_18]
0x180015c23  add     rsp, 68h
0x180015c27  jmp     short $+2
0x180015c29  jmp     rax
```
