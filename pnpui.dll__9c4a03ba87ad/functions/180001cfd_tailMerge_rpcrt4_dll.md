# __tailMerge_rpcrt4_dll

- ea: `0x180001cfd`
- end: `0x180001d76`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d7c`
- `0x180001f41`

## callees

- `0x180001cfd`
- `0x18000cb80`

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
0x180001cfd  mov     [rsp+arg_0], rcx
0x180001d02  mov     [rsp+arg_8], rdx
0x180001d07  mov     [rsp+arg_10], r8
0x180001d0c  mov     [rsp+arg_18], r9
0x180001d11  sub     rsp, 68h
0x180001d15  movdqa  [rsp+68h+var_48], xmm0
0x180001d1b  movdqa  [rsp+68h+var_38], xmm1
0x180001d21  movdqa  [rsp+68h+var_28], xmm2
0x180001d27  movdqa  [rsp+68h+var_18], xmm3
0x180001d2d  mov     rdx, rax
0x180001d30  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180001d37  call    __delayLoadHelper2
0x180001d3c  movdqa  xmm0, [rsp+68h+var_48]
0x180001d42  movdqa  xmm1, [rsp+68h+var_38]
0x180001d48  movdqa  xmm2, [rsp+68h+var_28]
0x180001d4e  movdqa  xmm3, [rsp+68h+var_18]
0x180001d54  mov     rcx, [rsp+68h+arg_0]
0x180001d59  mov     rdx, [rsp+68h+arg_8]
0x180001d5e  mov     r8, [rsp+68h+arg_10]
0x180001d66  mov     r9, [rsp+68h+arg_18]
0x180001d6e  add     rsp, 68h
0x180001d72  jmp     short $+2
0x180001d74  jmp     rax
```
