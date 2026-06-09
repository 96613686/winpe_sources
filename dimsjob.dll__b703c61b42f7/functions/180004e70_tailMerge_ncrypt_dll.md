# __tailMerge_ncrypt_dll

- ea: `0x180004e70`
- end: `0x180004ee9`
- name: `__tailMerge_ncrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004eef`
- `0x180004f01`

## callees

- `0x180004e70`
- `0x18000ab00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ncrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ncrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004e70  mov     [rsp+arg_0], rcx
0x180004e75  mov     [rsp+arg_8], rdx
0x180004e7a  mov     [rsp+arg_10], r8
0x180004e7f  mov     [rsp+arg_18], r9
0x180004e84  sub     rsp, 68h
0x180004e88  movdqa  [rsp+68h+var_48], xmm0
0x180004e8e  movdqa  [rsp+68h+var_38], xmm1
0x180004e94  movdqa  [rsp+68h+var_28], xmm2
0x180004e9a  movdqa  [rsp+68h+var_18], xmm3
0x180004ea0  mov     rdx, rax
0x180004ea3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ncrypt_dll
0x180004eaa  call    __delayLoadHelper2
0x180004eaf  movdqa  xmm0, [rsp+68h+var_48]
0x180004eb5  movdqa  xmm1, [rsp+68h+var_38]
0x180004ebb  movdqa  xmm2, [rsp+68h+var_28]
0x180004ec1  movdqa  xmm3, [rsp+68h+var_18]
0x180004ec7  mov     rcx, [rsp+68h+arg_0]
0x180004ecc  mov     rdx, [rsp+68h+arg_8]
0x180004ed1  mov     r8, [rsp+68h+arg_10]
0x180004ed9  mov     r9, [rsp+68h+arg_18]
0x180004ee1  add     rsp, 68h
0x180004ee5  jmp     short $+2
0x180004ee7  jmp     rax
```
