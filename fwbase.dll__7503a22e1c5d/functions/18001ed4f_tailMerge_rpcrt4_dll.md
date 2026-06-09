# __tailMerge_rpcrt4_dll

- ea: `0x18001ed4f`
- end: `0x18001edc8`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001edce`
- `0x18001ee6b`
- `0x18001ee7d`

## callees

- `0x180013080`
- `0x18001ed4f`

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
0x18001ed4f  mov     [rsp+arg_0], rcx
0x18001ed54  mov     [rsp+arg_8], rdx
0x18001ed59  mov     [rsp+arg_10], r8
0x18001ed5e  mov     [rsp+arg_18], r9
0x18001ed63  sub     rsp, 68h
0x18001ed67  movdqa  [rsp+68h+var_48], xmm0
0x18001ed6d  movdqa  [rsp+68h+var_38], xmm1
0x18001ed73  movdqa  [rsp+68h+var_28], xmm2
0x18001ed79  movdqa  [rsp+68h+var_18], xmm3
0x18001ed7f  mov     rdx, rax
0x18001ed82  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18001ed89  call    __delayLoadHelper2
0x18001ed8e  movdqa  xmm0, [rsp+68h+var_48]
0x18001ed94  movdqa  xmm1, [rsp+68h+var_38]
0x18001ed9a  movdqa  xmm2, [rsp+68h+var_28]
0x18001eda0  movdqa  xmm3, [rsp+68h+var_18]
0x18001eda6  mov     rcx, [rsp+68h+arg_0]
0x18001edab  mov     rdx, [rsp+68h+arg_8]
0x18001edb0  mov     r8, [rsp+68h+arg_10]
0x18001edb8  mov     r9, [rsp+68h+arg_18]
0x18001edc0  add     rsp, 68h
0x18001edc4  jmp     short $+2
0x18001edc6  jmp     rax
```
