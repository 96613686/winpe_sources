# __tailMerge_d3d12_dll

- ea: `0x140002ec8`
- end: `0x140002f41`
- name: `__tailMerge_d3d12_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002f47`

## callees

- `0x140002ec8`
- `0x140011270`

## pseudocode

```c
__int64 __fastcall _tailMerge_d3d12_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_d3d12_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002ec8  mov     [rsp+arg_0], rcx
0x140002ecd  mov     [rsp+arg_8], rdx
0x140002ed2  mov     [rsp+arg_10], r8
0x140002ed7  mov     [rsp+arg_18], r9
0x140002edc  sub     rsp, 68h
0x140002ee0  movdqa  [rsp+68h+var_48], xmm0
0x140002ee6  movdqa  [rsp+68h+var_38], xmm1
0x140002eec  movdqa  [rsp+68h+var_28], xmm2
0x140002ef2  movdqa  [rsp+68h+var_18], xmm3
0x140002ef8  mov     rdx, rax
0x140002efb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_d3d12_dll
0x140002f02  call    __delayLoadHelper2
0x140002f07  movdqa  xmm0, [rsp+68h+var_48]
0x140002f0d  movdqa  xmm1, [rsp+68h+var_38]
0x140002f13  movdqa  xmm2, [rsp+68h+var_28]
0x140002f19  movdqa  xmm3, [rsp+68h+var_18]
0x140002f1f  mov     rcx, [rsp+68h+arg_0]
0x140002f24  mov     rdx, [rsp+68h+arg_8]
0x140002f29  mov     r8, [rsp+68h+arg_10]
0x140002f31  mov     r9, [rsp+68h+arg_18]
0x140002f39  add     rsp, 68h
0x140002f3d  jmp     short $+2
0x140002f3f  jmp     rax
```
