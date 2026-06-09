# __tailMerge_wldap32_dll

- ea: `0x18000b23f`
- end: `0x18000b2b8`
- name: `__tailMerge_wldap32_dll`
- size: `121`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b2be`
- `0x18000b572`
- `0x18000b584`
- `0x18000b596`
- `0x18000b5a8`
- `0x18000b5ba`
- `0x18000b657`
- `0x18000b669`
- `0x18000b67b`
- `0x18000b68d`
- `0x18000b69f`
- `0x18000b6b1`
- `0x18000b6c3`
- `0x18000b6d5`
- `0x18000b6e7`
- `0x18000b6f9`
- `0x18000b70b`
- `0x18000b71d`
- `0x18000b72f`

## callees

- `0x180004590`
- `0x18000b23f`

## pseudocode

```c
__int64 __fastcall _tailMerge_wldap32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wldap32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b23f  mov     [rsp+arg_0], rcx
0x18000b244  mov     [rsp+arg_8], rdx
0x18000b249  mov     [rsp+arg_10], r8
0x18000b24e  mov     [rsp+arg_18], r9
0x18000b253  sub     rsp, 68h
0x18000b257  movdqa  [rsp+68h+var_48], xmm0
0x18000b25d  movdqa  [rsp+68h+var_38], xmm1
0x18000b263  movdqa  [rsp+68h+var_28], xmm2
0x18000b269  movdqa  [rsp+68h+var_18], xmm3
0x18000b26f  mov     rdx, rax
0x18000b272  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wldap32_dll
0x18000b279  call    __delayLoadHelper2
0x18000b27e  movdqa  xmm0, [rsp+68h+var_48]
0x18000b284  movdqa  xmm1, [rsp+68h+var_38]
0x18000b28a  movdqa  xmm2, [rsp+68h+var_28]
0x18000b290  movdqa  xmm3, [rsp+68h+var_18]
0x18000b296  mov     rcx, [rsp+68h+arg_0]
0x18000b29b  mov     rdx, [rsp+68h+arg_8]
0x18000b2a0  mov     r8, [rsp+68h+arg_10]
0x18000b2a8  mov     r9, [rsp+68h+arg_18]
0x18000b2b0  add     rsp, 68h
0x18000b2b4  jmp     short $+2
0x18000b2b6  jmp     rax
```
