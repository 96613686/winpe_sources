# __tailMerge_crypt32_dll

- ea: `0x180003381`
- end: `0x1800033fa`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003400`
- `0x180003412`
- `0x180003424`

## callees

- `0x1800015c0`
- `0x180003381`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003381  mov     [rsp+arg_0], rcx
0x180003386  mov     [rsp+arg_8], rdx
0x18000338b  mov     [rsp+arg_10], r8
0x180003390  mov     [rsp+arg_18], r9
0x180003395  sub     rsp, 68h
0x180003399  movdqa  [rsp+68h+var_48], xmm0
0x18000339f  movdqa  [rsp+68h+var_38], xmm1
0x1800033a5  movdqa  [rsp+68h+var_28], xmm2
0x1800033ab  movdqa  [rsp+68h+var_18], xmm3
0x1800033b1  mov     rdx, rax
0x1800033b4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x1800033bb  call    __delayLoadHelper2
0x1800033c0  movdqa  xmm0, [rsp+68h+var_48]
0x1800033c6  movdqa  xmm1, [rsp+68h+var_38]
0x1800033cc  movdqa  xmm2, [rsp+68h+var_28]
0x1800033d2  movdqa  xmm3, [rsp+68h+var_18]
0x1800033d8  mov     rcx, [rsp+68h+arg_0]
0x1800033dd  mov     rdx, [rsp+68h+arg_8]
0x1800033e2  mov     r8, [rsp+68h+arg_10]
0x1800033ea  mov     r9, [rsp+68h+arg_18]
0x1800033f2  add     rsp, 68h
0x1800033f6  jmp     short $+2
0x1800033f8  jmp     rax
```
