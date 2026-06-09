# __tailMerge_dnsapi_dll

- ea: `0x18001a44a`
- end: `0x18001a4c3`
- name: `__tailMerge_dnsapi_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a4c9`
- `0x18001a4db`
- `0x18001a4ed`
- `0x18001aa02`

## callees

- `0x18000f880`
- `0x18001a44a`

## pseudocode

```c
__int64 __fastcall _tailMerge_dnsapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dnsapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a44a  mov     [rsp+arg_0], rcx
0x18001a44f  mov     [rsp+arg_8], rdx
0x18001a454  mov     [rsp+arg_10], r8
0x18001a459  mov     [rsp+arg_18], r9
0x18001a45e  sub     rsp, 68h
0x18001a462  movdqa  [rsp+68h+var_48], xmm0
0x18001a468  movdqa  [rsp+68h+var_38], xmm1
0x18001a46e  movdqa  [rsp+68h+var_28], xmm2
0x18001a474  movdqa  [rsp+68h+var_18], xmm3
0x18001a47a  mov     rdx, rax
0x18001a47d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dnsapi_dll
0x18001a484  call    __delayLoadHelper2
0x18001a489  movdqa  xmm0, [rsp+68h+var_48]
0x18001a48f  movdqa  xmm1, [rsp+68h+var_38]
0x18001a495  movdqa  xmm2, [rsp+68h+var_28]
0x18001a49b  movdqa  xmm3, [rsp+68h+var_18]
0x18001a4a1  mov     rcx, [rsp+68h+arg_0]
0x18001a4a6  mov     rdx, [rsp+68h+arg_8]
0x18001a4ab  mov     r8, [rsp+68h+arg_10]
0x18001a4b3  mov     r9, [rsp+68h+arg_18]
0x18001a4bb  add     rsp, 68h
0x18001a4bf  jmp     short $+2
0x18001a4c1  jmp     rax
```
