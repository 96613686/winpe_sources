# __tailMerge_crypt32_dll

- ea: `0x18001af6e`
- end: `0x18001afe7`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001afed`

## callees

- `0x18001af6e`
- `0x180024ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001af6e  mov     [rsp+arg_0], rcx
0x18001af73  mov     [rsp+arg_8], rdx
0x18001af78  mov     [rsp+arg_10], r8
0x18001af7d  mov     [rsp+arg_18], r9
0x18001af82  sub     rsp, 68h
0x18001af86  movdqa  [rsp+68h+var_48], xmm0
0x18001af8c  movdqa  [rsp+68h+var_38], xmm1
0x18001af92  movdqa  [rsp+68h+var_28], xmm2
0x18001af98  movdqa  [rsp+68h+var_18], xmm3
0x18001af9e  mov     rdx, rax
0x18001afa1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18001afa8  call    __delayLoadHelper2
0x18001afad  movdqa  xmm0, [rsp+68h+var_48]
0x18001afb3  movdqa  xmm1, [rsp+68h+var_38]
0x18001afb9  movdqa  xmm2, [rsp+68h+var_28]
0x18001afbf  movdqa  xmm3, [rsp+68h+var_18]
0x18001afc5  mov     rcx, [rsp+68h+arg_0]
0x18001afca  mov     rdx, [rsp+68h+arg_8]
0x18001afcf  mov     r8, [rsp+68h+arg_10]
0x18001afd7  mov     r9, [rsp+68h+arg_18]
0x18001afdf  add     rsp, 68h
0x18001afe3  jmp     short $+2
0x18001afe5  jmp     rax
```
