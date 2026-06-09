# __tailMerge_cryptdll_dll

- ea: `0x18000fd50`
- end: `0x18000fdc9`
- name: `__tailMerge_cryptdll_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fdcf`
- `0x18000fde1`

## callees

- `0x18000d050`
- `0x18000fd50`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptdll_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptdll_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000fd50  mov     [rsp+arg_0], rcx
0x18000fd55  mov     [rsp+arg_8], rdx
0x18000fd5a  mov     [rsp+arg_10], r8
0x18000fd5f  mov     [rsp+arg_18], r9
0x18000fd64  sub     rsp, 68h
0x18000fd68  movdqa  [rsp+68h+var_48], xmm0
0x18000fd6e  movdqa  [rsp+68h+var_38], xmm1
0x18000fd74  movdqa  [rsp+68h+var_28], xmm2
0x18000fd7a  movdqa  [rsp+68h+var_18], xmm3
0x18000fd80  mov     rdx, rax
0x18000fd83  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptdll_dll
0x18000fd8a  call    __delayLoadHelper2
0x18000fd8f  movdqa  xmm0, [rsp+68h+var_48]
0x18000fd95  movdqa  xmm1, [rsp+68h+var_38]
0x18000fd9b  movdqa  xmm2, [rsp+68h+var_28]
0x18000fda1  movdqa  xmm3, [rsp+68h+var_18]
0x18000fda7  mov     rcx, [rsp+68h+arg_0]
0x18000fdac  mov     rdx, [rsp+68h+arg_8]
0x18000fdb1  mov     r8, [rsp+68h+arg_10]
0x18000fdb9  mov     r9, [rsp+68h+arg_18]
0x18000fdc1  add     rsp, 68h
0x18000fdc5  jmp     short $+2
0x18000fdc7  jmp     rax
```
