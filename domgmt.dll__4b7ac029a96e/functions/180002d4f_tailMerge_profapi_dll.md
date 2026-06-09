# __tailMerge_profapi_dll

- ea: `0x180002d4f`
- end: `0x180002dc8`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002dce`

## callees

- `0x180002d4f`
- `0x18000d4b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002d4f  mov     [rsp+arg_0], rcx
0x180002d54  mov     [rsp+arg_8], rdx
0x180002d59  mov     [rsp+arg_10], r8
0x180002d5e  mov     [rsp+arg_18], r9
0x180002d63  sub     rsp, 68h
0x180002d67  movdqa  [rsp+68h+var_48], xmm0
0x180002d6d  movdqa  [rsp+68h+var_38], xmm1
0x180002d73  movdqa  [rsp+68h+var_28], xmm2
0x180002d79  movdqa  [rsp+68h+var_18], xmm3
0x180002d7f  mov     rdx, rax
0x180002d82  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x180002d89  call    __delayLoadHelper2
0x180002d8e  movdqa  xmm0, [rsp+68h+var_48]
0x180002d94  movdqa  xmm1, [rsp+68h+var_38]
0x180002d9a  movdqa  xmm2, [rsp+68h+var_28]
0x180002da0  movdqa  xmm3, [rsp+68h+var_18]
0x180002da6  mov     rcx, [rsp+68h+arg_0]
0x180002dab  mov     rdx, [rsp+68h+arg_8]
0x180002db0  mov     r8, [rsp+68h+arg_10]
0x180002db8  mov     r9, [rsp+68h+arg_18]
0x180002dc0  add     rsp, 68h
0x180002dc4  jmp     short $+2
0x180002dc6  jmp     rax
```
