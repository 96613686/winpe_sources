# __tailMerge_wcmapi_dll

- ea: `0x18001af6d`
- end: `0x18001afe6`
- name: `__tailMerge_wcmapi_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001afec`
- `0x18001affe`
- `0x18001b010`

## callees

- `0x18000f880`
- `0x18001af6d`

## pseudocode

```c
__int64 __fastcall _tailMerge_wcmapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wcmapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001af6d  mov     [rsp+arg_0], rcx
0x18001af72  mov     [rsp+arg_8], rdx
0x18001af77  mov     [rsp+arg_10], r8
0x18001af7c  mov     [rsp+arg_18], r9
0x18001af81  sub     rsp, 68h
0x18001af85  movdqa  [rsp+68h+var_48], xmm0
0x18001af8b  movdqa  [rsp+68h+var_38], xmm1
0x18001af91  movdqa  [rsp+68h+var_28], xmm2
0x18001af97  movdqa  [rsp+68h+var_18], xmm3
0x18001af9d  mov     rdx, rax
0x18001afa0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wcmapi_dll
0x18001afa7  call    __delayLoadHelper2
0x18001afac  movdqa  xmm0, [rsp+68h+var_48]
0x18001afb2  movdqa  xmm1, [rsp+68h+var_38]
0x18001afb8  movdqa  xmm2, [rsp+68h+var_28]
0x18001afbe  movdqa  xmm3, [rsp+68h+var_18]
0x18001afc4  mov     rcx, [rsp+68h+arg_0]
0x18001afc9  mov     rdx, [rsp+68h+arg_8]
0x18001afce  mov     r8, [rsp+68h+arg_10]
0x18001afd6  mov     r9, [rsp+68h+arg_18]
0x18001afde  add     rsp, 68h
0x18001afe2  jmp     short $+2
0x18001afe4  jmp     rax
```
