# __tailMerge_wmsgapi_dll

- ea: `0x18001710b`
- end: `0x180017184`
- name: `__tailMerge_wmsgapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001718a`

## callees

- `0x18000e1a0`
- `0x18001710b`

## pseudocode

```c
__int64 __fastcall _tailMerge_wmsgapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wmsgapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001710b  mov     [rsp+arg_0], rcx
0x180017110  mov     [rsp+arg_8], rdx
0x180017115  mov     [rsp+arg_10], r8
0x18001711a  mov     [rsp+arg_18], r9
0x18001711f  sub     rsp, 68h
0x180017123  movdqa  [rsp+68h+var_48], xmm0
0x180017129  movdqa  [rsp+68h+var_38], xmm1
0x18001712f  movdqa  [rsp+68h+var_28], xmm2
0x180017135  movdqa  [rsp+68h+var_18], xmm3
0x18001713b  mov     rdx, rax
0x18001713e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wmsgapi_dll
0x180017145  call    __delayLoadHelper2
0x18001714a  movdqa  xmm0, [rsp+68h+var_48]
0x180017150  movdqa  xmm1, [rsp+68h+var_38]
0x180017156  movdqa  xmm2, [rsp+68h+var_28]
0x18001715c  movdqa  xmm3, [rsp+68h+var_18]
0x180017162  mov     rcx, [rsp+68h+arg_0]
0x180017167  mov     rdx, [rsp+68h+arg_8]
0x18001716c  mov     r8, [rsp+68h+arg_10]
0x180017174  mov     r9, [rsp+68h+arg_18]
0x18001717c  add     rsp, 68h
0x180017180  jmp     short $+2
0x180017182  jmp     rax
```
