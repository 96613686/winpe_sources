# __tailMerge_rpcrt4_dll

- ea: `0x1800079d0`
- end: `0x180007a49`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007a4f`
- `0x180007a61`
- `0x180007a73`
- `0x180007a85`
- `0x180007a97`
- `0x180007aa9`
- `0x180007abb`

## callees

- `0x180005080`
- `0x1800079d0`

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
0x1800079d0  mov     [rsp+arg_0], rcx
0x1800079d5  mov     [rsp+arg_8], rdx
0x1800079da  mov     [rsp+arg_10], r8
0x1800079df  mov     [rsp+arg_18], r9
0x1800079e4  sub     rsp, 68h
0x1800079e8  movdqa  [rsp+68h+var_48], xmm0
0x1800079ee  movdqa  [rsp+68h+var_38], xmm1
0x1800079f4  movdqa  [rsp+68h+var_28], xmm2
0x1800079fa  movdqa  [rsp+68h+var_18], xmm3
0x180007a00  mov     rdx, rax
0x180007a03  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180007a0a  call    __delayLoadHelper2
0x180007a0f  movdqa  xmm0, [rsp+68h+var_48]
0x180007a15  movdqa  xmm1, [rsp+68h+var_38]
0x180007a1b  movdqa  xmm2, [rsp+68h+var_28]
0x180007a21  movdqa  xmm3, [rsp+68h+var_18]
0x180007a27  mov     rcx, [rsp+68h+arg_0]
0x180007a2c  mov     rdx, [rsp+68h+arg_8]
0x180007a31  mov     r8, [rsp+68h+arg_10]
0x180007a39  mov     r9, [rsp+68h+arg_18]
0x180007a41  add     rsp, 68h
0x180007a45  jmp     short $+2
0x180007a47  jmp     rax
```
