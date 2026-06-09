# __tailMerge_crypt32_dll

- ea: `0x18002129a`
- end: `0x180021313`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021319`
- `0x18002132b`

## callees

- `0x180018b30`
- `0x18002129a`

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
0x18002129a  mov     [rsp+arg_0], rcx
0x18002129f  mov     [rsp+arg_8], rdx
0x1800212a4  mov     [rsp+arg_10], r8
0x1800212a9  mov     [rsp+arg_18], r9
0x1800212ae  sub     rsp, 68h
0x1800212b2  movdqa  [rsp+68h+var_48], xmm0
0x1800212b8  movdqa  [rsp+68h+var_38], xmm1
0x1800212be  movdqa  [rsp+68h+var_28], xmm2
0x1800212c4  movdqa  [rsp+68h+var_18], xmm3
0x1800212ca  mov     rdx, rax
0x1800212cd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x1800212d4  call    __delayLoadHelper2
0x1800212d9  movdqa  xmm0, [rsp+68h+var_48]
0x1800212df  movdqa  xmm1, [rsp+68h+var_38]
0x1800212e5  movdqa  xmm2, [rsp+68h+var_28]
0x1800212eb  movdqa  xmm3, [rsp+68h+var_18]
0x1800212f1  mov     rcx, [rsp+68h+arg_0]
0x1800212f6  mov     rdx, [rsp+68h+arg_8]
0x1800212fb  mov     r8, [rsp+68h+arg_10]
0x180021303  mov     r9, [rsp+68h+arg_18]
0x18002130b  add     rsp, 68h
0x18002130f  jmp     short $+2
0x180021311  jmp     rax
```
