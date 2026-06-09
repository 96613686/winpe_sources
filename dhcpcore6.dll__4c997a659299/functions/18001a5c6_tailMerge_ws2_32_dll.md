# __tailMerge_ws2_32_dll

- ea: `0x18001a5c6`
- end: `0x18001a63f`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a645`
- `0x18001a657`
- `0x18001a669`
- `0x18001a67b`
- `0x18001a68d`
- `0x18001a69f`
- `0x18001a6b1`
- `0x18001a6c3`
- `0x18001a6d5`
- `0x18001a6e7`
- `0x18001a6f9`
- `0x18001a70b`
- `0x18001a71d`
- `0x18001a72f`
- `0x18001a741`
- `0x18001a753`
- `0x18001a765`
- `0x18001a777`
- `0x18001a789`
- `0x18001a79b`
- `0x18001a7ad`
- `0x18001a7bf`
- `0x18001a7d1`

## callees

- `0x18000f880`
- `0x18001a5c6`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a5c6  mov     [rsp+arg_0], rcx
0x18001a5cb  mov     [rsp+arg_8], rdx
0x18001a5d0  mov     [rsp+arg_10], r8
0x18001a5d5  mov     [rsp+arg_18], r9
0x18001a5da  sub     rsp, 68h
0x18001a5de  movdqa  [rsp+68h+var_48], xmm0
0x18001a5e4  movdqa  [rsp+68h+var_38], xmm1
0x18001a5ea  movdqa  [rsp+68h+var_28], xmm2
0x18001a5f0  movdqa  [rsp+68h+var_18], xmm3
0x18001a5f6  mov     rdx, rax
0x18001a5f9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18001a600  call    __delayLoadHelper2
0x18001a605  movdqa  xmm0, [rsp+68h+var_48]
0x18001a60b  movdqa  xmm1, [rsp+68h+var_38]
0x18001a611  movdqa  xmm2, [rsp+68h+var_28]
0x18001a617  movdqa  xmm3, [rsp+68h+var_18]
0x18001a61d  mov     rcx, [rsp+68h+arg_0]
0x18001a622  mov     rdx, [rsp+68h+arg_8]
0x18001a627  mov     r8, [rsp+68h+arg_10]
0x18001a62f  mov     r9, [rsp+68h+arg_18]
0x18001a637  add     rsp, 68h
0x18001a63b  jmp     short $+2
0x18001a63d  jmp     rax
```
