# __tailMerge_credui_dll

- ea: `0x18000b0c8`
- end: `0x18000b141`
- name: `__tailMerge_credui_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b147`
- `0x18000b159`
- `0x18000b16b`
- `0x18000b17d`
- `0x18000b18f`
- `0x18000b1a1`

## callees

- `0x1800079c0`
- `0x18000b0c8`

## pseudocode

```c
__int64 __fastcall _tailMerge_credui_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_credui_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b0c8  mov     [rsp+arg_0], rcx
0x18000b0cd  mov     [rsp+arg_8], rdx
0x18000b0d2  mov     [rsp+arg_10], r8
0x18000b0d7  mov     [rsp+arg_18], r9
0x18000b0dc  sub     rsp, 68h
0x18000b0e0  movdqa  [rsp+68h+var_48], xmm0
0x18000b0e6  movdqa  [rsp+68h+var_38], xmm1
0x18000b0ec  movdqa  [rsp+68h+var_28], xmm2
0x18000b0f2  movdqa  [rsp+68h+var_18], xmm3
0x18000b0f8  mov     rdx, rax
0x18000b0fb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_credui_dll
0x18000b102  call    __delayLoadHelper2
0x18000b107  movdqa  xmm0, [rsp+68h+var_48]
0x18000b10d  movdqa  xmm1, [rsp+68h+var_38]
0x18000b113  movdqa  xmm2, [rsp+68h+var_28]
0x18000b119  movdqa  xmm3, [rsp+68h+var_18]
0x18000b11f  mov     rcx, [rsp+68h+arg_0]
0x18000b124  mov     rdx, [rsp+68h+arg_8]
0x18000b129  mov     r8, [rsp+68h+arg_10]
0x18000b131  mov     r9, [rsp+68h+arg_18]
0x18000b139  add     rsp, 68h
0x18000b13d  jmp     short $+2
0x18000b13f  jmp     rax
```
