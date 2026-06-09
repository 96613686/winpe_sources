# __tailMerge_rpcrt4_dll

- ea: `0x180002824`
- end: `0x18000289d`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800028a3`
- `0x1800028b5`
- `0x1800028c7`
- `0x1800028d9`
- `0x1800028eb`
- `0x1800028fd`
- `0x18000290f`
- `0x180002921`
- `0x180002933`

## callees

- `0x1800017d0`
- `0x180002824`

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
0x180002824  mov     [rsp+arg_0], rcx
0x180002829  mov     [rsp+arg_8], rdx
0x18000282e  mov     [rsp+arg_10], r8
0x180002833  mov     [rsp+arg_18], r9
0x180002838  sub     rsp, 68h
0x18000283c  movdqa  [rsp+68h+var_48], xmm0
0x180002842  movdqa  [rsp+68h+var_38], xmm1
0x180002848  movdqa  [rsp+68h+var_28], xmm2
0x18000284e  movdqa  [rsp+68h+var_18], xmm3
0x180002854  mov     rdx, rax
0x180002857  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000285e  call    __delayLoadHelper2
0x180002863  movdqa  xmm0, [rsp+68h+var_48]
0x180002869  movdqa  xmm1, [rsp+68h+var_38]
0x18000286f  movdqa  xmm2, [rsp+68h+var_28]
0x180002875  movdqa  xmm3, [rsp+68h+var_18]
0x18000287b  mov     rcx, [rsp+68h+arg_0]
0x180002880  mov     rdx, [rsp+68h+arg_8]
0x180002885  mov     r8, [rsp+68h+arg_10]
0x18000288d  mov     r9, [rsp+68h+arg_18]
0x180002895  add     rsp, 68h
0x180002899  jmp     short $+2
0x18000289b  jmp     rax
```
