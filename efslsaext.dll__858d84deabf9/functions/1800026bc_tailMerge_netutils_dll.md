# __tailMerge_netutils_dll

- ea: `0x1800026bc`
- end: `0x180002735`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000273b`

## callees

- `0x1800026bc`
- `0x180007f20`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026bc  mov     [rsp+arg_0], rcx
0x1800026c1  mov     [rsp+arg_8], rdx
0x1800026c6  mov     [rsp+arg_10], r8
0x1800026cb  mov     [rsp+arg_18], r9
0x1800026d0  sub     rsp, 68h
0x1800026d4  movdqa  [rsp+68h+var_48], xmm0
0x1800026da  movdqa  [rsp+68h+var_38], xmm1
0x1800026e0  movdqa  [rsp+68h+var_28], xmm2
0x1800026e6  movdqa  [rsp+68h+var_18], xmm3
0x1800026ec  mov     rdx, rax
0x1800026ef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x1800026f6  call    __delayLoadHelper2
0x1800026fb  movdqa  xmm0, [rsp+68h+var_48]
0x180002701  movdqa  xmm1, [rsp+68h+var_38]
0x180002707  movdqa  xmm2, [rsp+68h+var_28]
0x18000270d  movdqa  xmm3, [rsp+68h+var_18]
0x180002713  mov     rcx, [rsp+68h+arg_0]
0x180002718  mov     rdx, [rsp+68h+arg_8]
0x18000271d  mov     r8, [rsp+68h+arg_10]
0x180002725  mov     r9, [rsp+68h+arg_18]
0x18000272d  add     rsp, 68h
0x180002731  jmp     short $+2
0x180002733  jmp     rax
```
