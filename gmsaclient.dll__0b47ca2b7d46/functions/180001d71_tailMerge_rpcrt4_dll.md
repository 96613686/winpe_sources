# __tailMerge_rpcrt4_dll

- ea: `0x180001d71`
- end: `0x180001dea`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001df0`
- `0x180001f2a`
- `0x180001f3c`

## callees

- `0x180001d71`
- `0x180007a80`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d71  mov     [rsp+arg_0], rcx
0x180001d76  mov     [rsp+arg_8], rdx
0x180001d7b  mov     [rsp+arg_10], r8
0x180001d80  mov     [rsp+arg_18], r9
0x180001d85  sub     rsp, 68h
0x180001d89  movdqa  [rsp+68h+var_48], xmm0
0x180001d8f  movdqa  [rsp+68h+var_38], xmm1
0x180001d95  movdqa  [rsp+68h+var_28], xmm2
0x180001d9b  movdqa  [rsp+68h+var_18], xmm3
0x180001da1  mov     rdx, rax
0x180001da4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180001dab  call    __delayLoadHelper2
0x180001db0  movdqa  xmm0, [rsp+68h+var_48]
0x180001db6  movdqa  xmm1, [rsp+68h+var_38]
0x180001dbc  movdqa  xmm2, [rsp+68h+var_28]
0x180001dc2  movdqa  xmm3, [rsp+68h+var_18]
0x180001dc8  mov     rcx, [rsp+68h+arg_0]
0x180001dcd  mov     rdx, [rsp+68h+arg_8]
0x180001dd2  mov     r8, [rsp+68h+arg_10]
0x180001dda  mov     r9, [rsp+68h+arg_18]
0x180001de2  add     rsp, 68h
0x180001de6  jmp     short $+2
0x180001de8  jmp     rax
```
