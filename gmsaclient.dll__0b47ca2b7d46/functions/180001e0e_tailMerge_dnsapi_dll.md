# __tailMerge_dnsapi_dll

- ea: `0x180001e0e`
- end: `0x180001e87`
- name: `__tailMerge_dnsapi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e8d`

## callees

- `0x180001e0e`
- `0x180007a80`

## pseudocode

```c
__int64 __fastcall _tailMerge_dnsapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dnsapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e0e  mov     [rsp+arg_0], rcx
0x180001e13  mov     [rsp+arg_8], rdx
0x180001e18  mov     [rsp+arg_10], r8
0x180001e1d  mov     [rsp+arg_18], r9
0x180001e22  sub     rsp, 68h
0x180001e26  movdqa  [rsp+68h+var_48], xmm0
0x180001e2c  movdqa  [rsp+68h+var_38], xmm1
0x180001e32  movdqa  [rsp+68h+var_28], xmm2
0x180001e38  movdqa  [rsp+68h+var_18], xmm3
0x180001e3e  mov     rdx, rax
0x180001e41  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dnsapi_dll
0x180001e48  call    __delayLoadHelper2
0x180001e4d  movdqa  xmm0, [rsp+68h+var_48]
0x180001e53  movdqa  xmm1, [rsp+68h+var_38]
0x180001e59  movdqa  xmm2, [rsp+68h+var_28]
0x180001e5f  movdqa  xmm3, [rsp+68h+var_18]
0x180001e65  mov     rcx, [rsp+68h+arg_0]
0x180001e6a  mov     rdx, [rsp+68h+arg_8]
0x180001e6f  mov     r8, [rsp+68h+arg_10]
0x180001e77  mov     r9, [rsp+68h+arg_18]
0x180001e7f  add     rsp, 68h
0x180001e83  jmp     short $+2
0x180001e85  jmp     rax
```
