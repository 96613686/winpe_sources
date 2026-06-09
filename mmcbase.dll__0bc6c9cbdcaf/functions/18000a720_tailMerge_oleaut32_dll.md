# __tailMerge_oleaut32_dll

- ea: `0x18000a720`
- end: `0x18000a799`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a79f`
- `0x18000a7b1`
- `0x18000a7c3`

## callees

- `0x180006bb0`
- `0x18000a720`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a720  mov     [rsp+arg_0], rcx
0x18000a725  mov     [rsp+arg_8], rdx
0x18000a72a  mov     [rsp+arg_10], r8
0x18000a72f  mov     [rsp+arg_18], r9
0x18000a734  sub     rsp, 68h
0x18000a738  movdqa  [rsp+68h+var_48], xmm0
0x18000a73e  movdqa  [rsp+68h+var_38], xmm1
0x18000a744  movdqa  [rsp+68h+var_28], xmm2
0x18000a74a  movdqa  [rsp+68h+var_18], xmm3
0x18000a750  mov     rdx, rax
0x18000a753  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000a75a  call    __delayLoadHelper2
0x18000a75f  movdqa  xmm0, [rsp+68h+var_48]
0x18000a765  movdqa  xmm1, [rsp+68h+var_38]
0x18000a76b  movdqa  xmm2, [rsp+68h+var_28]
0x18000a771  movdqa  xmm3, [rsp+68h+var_18]
0x18000a777  mov     rcx, [rsp+68h+arg_0]
0x18000a77c  mov     rdx, [rsp+68h+arg_8]
0x18000a781  mov     r8, [rsp+68h+arg_10]
0x18000a789  mov     r9, [rsp+68h+arg_18]
0x18000a791  add     rsp, 68h
0x18000a795  jmp     short $+2
0x18000a797  jmp     rax
```
