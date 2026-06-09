# __tailMerge_oleaut32_dll

- ea: `0x18000af52`
- end: `0x18000afcb`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000afd1`
- `0x18000b06e`
- `0x18000b41c`
- `0x18000b440`
- `0x18000b452`
- `0x18000b464`
- `0x18000b476`
- `0x18000b488`
- `0x18000b49a`
- `0x18000b4ac`
- `0x18000b4be`
- `0x18000b4d0`
- `0x18000b4e2`
- `0x18000b4f4`
- `0x18000b506`
- `0x18000b518`
- `0x18000b52a`
- `0x18000b53c`
- `0x18000b54e`
- `0x18000b560`

## callees

- `0x180004590`
- `0x18000af52`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000af52  mov     [rsp+arg_0], rcx
0x18000af57  mov     [rsp+arg_8], rdx
0x18000af5c  mov     [rsp+arg_10], r8
0x18000af61  mov     [rsp+arg_18], r9
0x18000af66  sub     rsp, 68h
0x18000af6a  movdqa  [rsp+68h+var_48], xmm0
0x18000af70  movdqa  [rsp+68h+var_38], xmm1
0x18000af76  movdqa  [rsp+68h+var_28], xmm2
0x18000af7c  movdqa  [rsp+68h+var_18], xmm3
0x18000af82  mov     rdx, rax
0x18000af85  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000af8c  call    __delayLoadHelper2
0x18000af91  movdqa  xmm0, [rsp+68h+var_48]
0x18000af97  movdqa  xmm1, [rsp+68h+var_38]
0x18000af9d  movdqa  xmm2, [rsp+68h+var_28]
0x18000afa3  movdqa  xmm3, [rsp+68h+var_18]
0x18000afa9  mov     rcx, [rsp+68h+arg_0]
0x18000afae  mov     rdx, [rsp+68h+arg_8]
0x18000afb3  mov     r8, [rsp+68h+arg_10]
0x18000afbb  mov     r9, [rsp+68h+arg_18]
0x18000afc3  add     rsp, 68h
0x18000afc7  jmp     short $+2
0x18000afc9  jmp     rax
```
