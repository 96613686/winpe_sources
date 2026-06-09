# __tailMerge_wldap32_dll

- ea: `0x180005dca`
- end: `0x180005e43`
- name: `__tailMerge_wldap32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005e49`
- `0x180005e5b`
- `0x180005e6d`
- `0x180005e7f`
- `0x180005e91`
- `0x180005ea3`
- `0x180005eb5`
- `0x180005ec7`
- `0x180005f64`
- `0x180006140`
- `0x180006152`
- `0x180006164`
- `0x180006176`
- `0x180006188`
- `0x18000619a`
- `0x1800061ac`

## callees

- `0x1800046b0`
- `0x180005dca`

## pseudocode

```c
__int64 __fastcall _tailMerge_wldap32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wldap32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005dca  mov     [rsp+arg_0], rcx
0x180005dcf  mov     [rsp+arg_8], rdx
0x180005dd4  mov     [rsp+arg_10], r8
0x180005dd9  mov     [rsp+arg_18], r9
0x180005dde  sub     rsp, 68h
0x180005de2  movdqa  [rsp+68h+var_48], xmm0
0x180005de8  movdqa  [rsp+68h+var_38], xmm1
0x180005dee  movdqa  [rsp+68h+var_28], xmm2
0x180005df4  movdqa  [rsp+68h+var_18], xmm3
0x180005dfa  mov     rdx, rax
0x180005dfd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wldap32_dll
0x180005e04  call    __delayLoadHelper2
0x180005e09  movdqa  xmm0, [rsp+68h+var_48]
0x180005e0f  movdqa  xmm1, [rsp+68h+var_38]
0x180005e15  movdqa  xmm2, [rsp+68h+var_28]
0x180005e1b  movdqa  xmm3, [rsp+68h+var_18]
0x180005e21  mov     rcx, [rsp+68h+arg_0]
0x180005e26  mov     rdx, [rsp+68h+arg_8]
0x180005e2b  mov     r8, [rsp+68h+arg_10]
0x180005e33  mov     r9, [rsp+68h+arg_18]
0x180005e3b  add     rsp, 68h
0x180005e3f  jmp     short $+2
0x180005e41  jmp     rax
```
