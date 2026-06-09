# __tailMerge_bcrypt_dll

- ea: `0x180001e99`
- end: `0x180001f12`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f18`

## callees

- `0x180001e99`
- `0x180007a80`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e99  mov     [rsp+arg_0], rcx
0x180001e9e  mov     [rsp+arg_8], rdx
0x180001ea3  mov     [rsp+arg_10], r8
0x180001ea8  mov     [rsp+arg_18], r9
0x180001ead  sub     rsp, 68h
0x180001eb1  movdqa  [rsp+68h+var_48], xmm0
0x180001eb7  movdqa  [rsp+68h+var_38], xmm1
0x180001ebd  movdqa  [rsp+68h+var_28], xmm2
0x180001ec3  movdqa  [rsp+68h+var_18], xmm3
0x180001ec9  mov     rdx, rax
0x180001ecc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180001ed3  call    __delayLoadHelper2
0x180001ed8  movdqa  xmm0, [rsp+68h+var_48]
0x180001ede  movdqa  xmm1, [rsp+68h+var_38]
0x180001ee4  movdqa  xmm2, [rsp+68h+var_28]
0x180001eea  movdqa  xmm3, [rsp+68h+var_18]
0x180001ef0  mov     rcx, [rsp+68h+arg_0]
0x180001ef5  mov     rdx, [rsp+68h+arg_8]
0x180001efa  mov     r8, [rsp+68h+arg_10]
0x180001f02  mov     r9, [rsp+68h+arg_18]
0x180001f0a  add     rsp, 68h
0x180001f0e  jmp     short $+2
0x180001f10  jmp     rax
```
