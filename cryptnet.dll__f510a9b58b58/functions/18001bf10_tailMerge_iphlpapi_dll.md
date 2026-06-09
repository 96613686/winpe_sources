# __tailMerge_iphlpapi_dll

- ea: `0x18001bf10`
- end: `0x18001bf89`
- name: `__tailMerge_iphlpapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001bf8f`
- `0x18001bfa1`
- `0x18001bfb3`
- `0x18001bfc5`

## callees

- `0x1800187e0`
- `0x18001bf10`

## pseudocode

```c
__int64 __fastcall _tailMerge_iphlpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001bf10  mov     [rsp+arg_0], rcx
0x18001bf15  mov     [rsp+arg_8], rdx
0x18001bf1a  mov     [rsp+arg_10], r8
0x18001bf1f  mov     [rsp+arg_18], r9
0x18001bf24  sub     rsp, 68h
0x18001bf28  movdqa  [rsp+68h+var_48], xmm0
0x18001bf2e  movdqa  [rsp+68h+var_38], xmm1
0x18001bf34  movdqa  [rsp+68h+var_28], xmm2
0x18001bf3a  movdqa  [rsp+68h+var_18], xmm3
0x18001bf40  mov     rdx, rax
0x18001bf43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll
0x18001bf4a  call    __delayLoadHelper2
0x18001bf4f  movdqa  xmm0, [rsp+68h+var_48]
0x18001bf55  movdqa  xmm1, [rsp+68h+var_38]
0x18001bf5b  movdqa  xmm2, [rsp+68h+var_28]
0x18001bf61  movdqa  xmm3, [rsp+68h+var_18]
0x18001bf67  mov     rcx, [rsp+68h+arg_0]
0x18001bf6c  mov     rdx, [rsp+68h+arg_8]
0x18001bf71  mov     r8, [rsp+68h+arg_10]
0x18001bf79  mov     r9, [rsp+68h+arg_18]
0x18001bf81  add     rsp, 68h
0x18001bf85  jmp     short $+2
0x18001bf87  jmp     rax
```
