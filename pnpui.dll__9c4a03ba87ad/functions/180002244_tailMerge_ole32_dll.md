# __tailMerge_ole32_dll

- ea: `0x180002244`
- end: `0x1800022bd`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022c3`
- `0x1800022d5`
- `0x1800022e7`

## callees

- `0x180002244`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002244  mov     [rsp+arg_0], rcx
0x180002249  mov     [rsp+arg_8], rdx
0x18000224e  mov     [rsp+arg_10], r8
0x180002253  mov     [rsp+arg_18], r9
0x180002258  sub     rsp, 68h
0x18000225c  movdqa  [rsp+68h+var_48], xmm0
0x180002262  movdqa  [rsp+68h+var_38], xmm1
0x180002268  movdqa  [rsp+68h+var_28], xmm2
0x18000226e  movdqa  [rsp+68h+var_18], xmm3
0x180002274  mov     rdx, rax
0x180002277  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x18000227e  call    __delayLoadHelper2
0x180002283  movdqa  xmm0, [rsp+68h+var_48]
0x180002289  movdqa  xmm1, [rsp+68h+var_38]
0x18000228f  movdqa  xmm2, [rsp+68h+var_28]
0x180002295  movdqa  xmm3, [rsp+68h+var_18]
0x18000229b  mov     rcx, [rsp+68h+arg_0]
0x1800022a0  mov     rdx, [rsp+68h+arg_8]
0x1800022a5  mov     r8, [rsp+68h+arg_10]
0x1800022ad  mov     r9, [rsp+68h+arg_18]
0x1800022b5  add     rsp, 68h
0x1800022b9  jmp     short $+2
0x1800022bb  jmp     rax
```
