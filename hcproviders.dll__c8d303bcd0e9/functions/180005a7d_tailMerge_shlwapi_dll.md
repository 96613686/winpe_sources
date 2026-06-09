# __tailMerge_shlwapi_dll

- ea: `0x180005a7d`
- end: `0x180005af6`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005afc`
- `0x180005b0e`

## callees

- `0x180004100`
- `0x180005a7d`

## pseudocode

```c
__int64 __fastcall _tailMerge_shlwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shlwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005a7d  mov     [rsp+arg_0], rcx
0x180005a82  mov     [rsp+arg_8], rdx
0x180005a87  mov     [rsp+arg_10], r8
0x180005a8c  mov     [rsp+arg_18], r9
0x180005a91  sub     rsp, 68h
0x180005a95  movdqa  [rsp+68h+var_48], xmm0
0x180005a9b  movdqa  [rsp+68h+var_38], xmm1
0x180005aa1  movdqa  [rsp+68h+var_28], xmm2
0x180005aa7  movdqa  [rsp+68h+var_18], xmm3
0x180005aad  mov     rdx, rax
0x180005ab0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x180005ab7  call    __delayLoadHelper2
0x180005abc  movdqa  xmm0, [rsp+68h+var_48]
0x180005ac2  movdqa  xmm1, [rsp+68h+var_38]
0x180005ac8  movdqa  xmm2, [rsp+68h+var_28]
0x180005ace  movdqa  xmm3, [rsp+68h+var_18]
0x180005ad4  mov     rcx, [rsp+68h+arg_0]
0x180005ad9  mov     rdx, [rsp+68h+arg_8]
0x180005ade  mov     r8, [rsp+68h+arg_10]
0x180005ae6  mov     r9, [rsp+68h+arg_18]
0x180005aee  add     rsp, 68h
0x180005af2  jmp     short $+2
0x180005af4  jmp     rax
```
