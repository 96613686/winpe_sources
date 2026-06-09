# __tailMerge_bcrypt_dll

- ea: `0x180016f53`
- end: `0x180016fcc`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016fd2`

## callees

- `0x18000e1a0`
- `0x180016f53`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180016f53  mov     [rsp+arg_0], rcx
0x180016f58  mov     [rsp+arg_8], rdx
0x180016f5d  mov     [rsp+arg_10], r8
0x180016f62  mov     [rsp+arg_18], r9
0x180016f67  sub     rsp, 68h
0x180016f6b  movdqa  [rsp+68h+var_48], xmm0
0x180016f71  movdqa  [rsp+68h+var_38], xmm1
0x180016f77  movdqa  [rsp+68h+var_28], xmm2
0x180016f7d  movdqa  [rsp+68h+var_18], xmm3
0x180016f83  mov     rdx, rax
0x180016f86  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180016f8d  call    __delayLoadHelper2
0x180016f92  movdqa  xmm0, [rsp+68h+var_48]
0x180016f98  movdqa  xmm1, [rsp+68h+var_38]
0x180016f9e  movdqa  xmm2, [rsp+68h+var_28]
0x180016fa4  movdqa  xmm3, [rsp+68h+var_18]
0x180016faa  mov     rcx, [rsp+68h+arg_0]
0x180016faf  mov     rdx, [rsp+68h+arg_8]
0x180016fb4  mov     r8, [rsp+68h+arg_10]
0x180016fbc  mov     r9, [rsp+68h+arg_18]
0x180016fc4  add     rsp, 68h
0x180016fc8  jmp     short $+2
0x180016fca  jmp     rax
```
