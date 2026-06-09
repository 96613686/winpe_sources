# __tailMerge_fltlib_dll

- ea: `0x180002427`
- end: `0x1800024a0`
- name: `__tailMerge_fltlib_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800024a6`
- `0x1800024b8`
- `0x1800024ca`

## callees

- `0x180002427`
- `0x18001cd30`

## pseudocode

```c
__int64 __fastcall _tailMerge_fltlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_fltlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002427  mov     [rsp+arg_0], rcx
0x18000242c  mov     [rsp+arg_8], rdx
0x180002431  mov     [rsp+arg_10], r8
0x180002436  mov     [rsp+arg_18], r9
0x18000243b  sub     rsp, 68h
0x18000243f  movdqa  [rsp+68h+var_48], xmm0
0x180002445  movdqa  [rsp+68h+var_38], xmm1
0x18000244b  movdqa  [rsp+68h+var_28], xmm2
0x180002451  movdqa  [rsp+68h+var_18], xmm3
0x180002457  mov     rdx, rax
0x18000245a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_fltlib_dll
0x180002461  call    __delayLoadHelper2
0x180002466  movdqa  xmm0, [rsp+68h+var_48]
0x18000246c  movdqa  xmm1, [rsp+68h+var_38]
0x180002472  movdqa  xmm2, [rsp+68h+var_28]
0x180002478  movdqa  xmm3, [rsp+68h+var_18]
0x18000247e  mov     rcx, [rsp+68h+arg_0]
0x180002483  mov     rdx, [rsp+68h+arg_8]
0x180002488  mov     r8, [rsp+68h+arg_10]
0x180002490  mov     r9, [rsp+68h+arg_18]
0x180002498  add     rsp, 68h
0x18000249c  jmp     short $+2
0x18000249e  jmp     rax
```
