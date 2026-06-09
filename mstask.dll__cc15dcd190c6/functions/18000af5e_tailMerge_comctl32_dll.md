# __tailMerge_comctl32_dll

- ea: `0x18000af5e`
- end: `0x18000afd7`
- name: `__tailMerge_comctl32_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000afdd`
- `0x18000b05b`
- `0x18000b091`
- `0x18000b145`
- `0x18000b50f`
- `0x18000b521`
- `0x18000b533`
- `0x18000b545`
- `0x18000b569`
- `0x18000b57b`

## callees

- `0x180009170`
- `0x18000af5e`

## pseudocode

```c
__int64 __fastcall _tailMerge_comctl32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_comctl32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000af5e  mov     [rsp+arg_0], rcx
0x18000af63  mov     [rsp+arg_8], rdx
0x18000af68  mov     [rsp+arg_10], r8
0x18000af6d  mov     [rsp+arg_18], r9
0x18000af72  sub     rsp, 68h
0x18000af76  movdqa  [rsp+68h+var_48], xmm0
0x18000af7c  movdqa  [rsp+68h+var_38], xmm1
0x18000af82  movdqa  [rsp+68h+var_28], xmm2
0x18000af88  movdqa  [rsp+68h+var_18], xmm3
0x18000af8e  mov     rdx, rax
0x18000af91  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comctl32_dll
0x18000af98  call    __delayLoadHelper2
0x18000af9d  movdqa  xmm0, [rsp+68h+var_48]
0x18000afa3  movdqa  xmm1, [rsp+68h+var_38]
0x18000afa9  movdqa  xmm2, [rsp+68h+var_28]
0x18000afaf  movdqa  xmm3, [rsp+68h+var_18]
0x18000afb5  mov     rcx, [rsp+68h+arg_0]
0x18000afba  mov     rdx, [rsp+68h+arg_8]
0x18000afbf  mov     r8, [rsp+68h+arg_10]
0x18000afc7  mov     r9, [rsp+68h+arg_18]
0x18000afcf  add     rsp, 68h
0x18000afd3  jmp     short $+2
0x18000afd5  jmp     rax
```
