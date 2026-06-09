# __tailMerge_dnsapi_dll

- ea: `0x18001ef6e`
- end: `0x18001efe7`
- name: `__tailMerge_dnsapi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001efed`

## callees

- `0x180013080`
- `0x18001ef6e`

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
0x18001ef6e  mov     [rsp+arg_0], rcx
0x18001ef73  mov     [rsp+arg_8], rdx
0x18001ef78  mov     [rsp+arg_10], r8
0x18001ef7d  mov     [rsp+arg_18], r9
0x18001ef82  sub     rsp, 68h
0x18001ef86  movdqa  [rsp+68h+var_48], xmm0
0x18001ef8c  movdqa  [rsp+68h+var_38], xmm1
0x18001ef92  movdqa  [rsp+68h+var_28], xmm2
0x18001ef98  movdqa  [rsp+68h+var_18], xmm3
0x18001ef9e  mov     rdx, rax
0x18001efa1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dnsapi_dll
0x18001efa8  call    __delayLoadHelper2
0x18001efad  movdqa  xmm0, [rsp+68h+var_48]
0x18001efb3  movdqa  xmm1, [rsp+68h+var_38]
0x18001efb9  movdqa  xmm2, [rsp+68h+var_28]
0x18001efbf  movdqa  xmm3, [rsp+68h+var_18]
0x18001efc5  mov     rcx, [rsp+68h+arg_0]
0x18001efca  mov     rdx, [rsp+68h+arg_8]
0x18001efcf  mov     r8, [rsp+68h+arg_10]
0x18001efd7  mov     r9, [rsp+68h+arg_18]
0x18001efdf  add     rsp, 68h
0x18001efe3  jmp     short $+2
0x18001efe5  jmp     rax
```
