# __tailMerge_lsasrv_dll

- ea: `0x18000fc8f`
- end: `0x18000fd08`
- name: `__tailMerge_lsasrv_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fd0e`
- `0x18000fd20`
- `0x18000fd32`

## callees

- `0x18000d050`
- `0x18000fc8f`

## pseudocode

```c
__int64 __fastcall _tailMerge_lsasrv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_lsasrv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000fc8f  mov     [rsp+arg_0], rcx
0x18000fc94  mov     [rsp+arg_8], rdx
0x18000fc99  mov     [rsp+arg_10], r8
0x18000fc9e  mov     [rsp+arg_18], r9
0x18000fca3  sub     rsp, 68h
0x18000fca7  movdqa  [rsp+68h+var_48], xmm0
0x18000fcad  movdqa  [rsp+68h+var_38], xmm1
0x18000fcb3  movdqa  [rsp+68h+var_28], xmm2
0x18000fcb9  movdqa  [rsp+68h+var_18], xmm3
0x18000fcbf  mov     rdx, rax
0x18000fcc2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_lsasrv_dll
0x18000fcc9  call    __delayLoadHelper2
0x18000fcce  movdqa  xmm0, [rsp+68h+var_48]
0x18000fcd4  movdqa  xmm1, [rsp+68h+var_38]
0x18000fcda  movdqa  xmm2, [rsp+68h+var_28]
0x18000fce0  movdqa  xmm3, [rsp+68h+var_18]
0x18000fce6  mov     rcx, [rsp+68h+arg_0]
0x18000fceb  mov     rdx, [rsp+68h+arg_8]
0x18000fcf0  mov     r8, [rsp+68h+arg_10]
0x18000fcf8  mov     r9, [rsp+68h+arg_18]
0x18000fd00  add     rsp, 68h
0x18000fd04  jmp     short $+2
0x18000fd06  jmp     rax
```
