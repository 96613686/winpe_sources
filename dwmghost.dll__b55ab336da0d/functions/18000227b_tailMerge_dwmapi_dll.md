# __tailMerge_dwmapi_dll

- ea: `0x18000227b`
- end: `0x1800022f4`
- name: `__tailMerge_dwmapi_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022fa`
- `0x18000230c`
- `0x18000231e`

## callees

- `0x18000227b`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_dwmapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dwmapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000227b  mov     [rsp+arg_0], rcx
0x180002280  mov     [rsp+arg_8], rdx
0x180002285  mov     [rsp+arg_10], r8
0x18000228a  mov     [rsp+arg_18], r9
0x18000228f  sub     rsp, 68h
0x180002293  movdqa  [rsp+68h+var_48], xmm0
0x180002299  movdqa  [rsp+68h+var_38], xmm1
0x18000229f  movdqa  [rsp+68h+var_28], xmm2
0x1800022a5  movdqa  [rsp+68h+var_18], xmm3
0x1800022ab  mov     rdx, rax
0x1800022ae  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dwmapi_dll
0x1800022b5  call    __delayLoadHelper2
0x1800022ba  movdqa  xmm0, [rsp+68h+var_48]
0x1800022c0  movdqa  xmm1, [rsp+68h+var_38]
0x1800022c6  movdqa  xmm2, [rsp+68h+var_28]
0x1800022cc  movdqa  xmm3, [rsp+68h+var_18]
0x1800022d2  mov     rcx, [rsp+68h+arg_0]
0x1800022d7  mov     rdx, [rsp+68h+arg_8]
0x1800022dc  mov     r8, [rsp+68h+arg_10]
0x1800022e4  mov     r9, [rsp+68h+arg_18]
0x1800022ec  add     rsp, 68h
0x1800022f0  jmp     short $+2
0x1800022f2  jmp     rax
```
