# __tailMerge_ole32_dll

- ea: `0x18000b25c`
- end: `0x18000b2d5`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b2db`

## callees

- `0x1800079c0`
- `0x18000b25c`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b25c  mov     [rsp+arg_0], rcx
0x18000b261  mov     [rsp+arg_8], rdx
0x18000b266  mov     [rsp+arg_10], r8
0x18000b26b  mov     [rsp+arg_18], r9
0x18000b270  sub     rsp, 68h
0x18000b274  movdqa  [rsp+68h+var_48], xmm0
0x18000b27a  movdqa  [rsp+68h+var_38], xmm1
0x18000b280  movdqa  [rsp+68h+var_28], xmm2
0x18000b286  movdqa  [rsp+68h+var_18], xmm3
0x18000b28c  mov     rdx, rax
0x18000b28f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x18000b296  call    __delayLoadHelper2
0x18000b29b  movdqa  xmm0, [rsp+68h+var_48]
0x18000b2a1  movdqa  xmm1, [rsp+68h+var_38]
0x18000b2a7  movdqa  xmm2, [rsp+68h+var_28]
0x18000b2ad  movdqa  xmm3, [rsp+68h+var_18]
0x18000b2b3  mov     rcx, [rsp+68h+arg_0]
0x18000b2b8  mov     rdx, [rsp+68h+arg_8]
0x18000b2bd  mov     r8, [rsp+68h+arg_10]
0x18000b2c5  mov     r9, [rsp+68h+arg_18]
0x18000b2cd  add     rsp, 68h
0x18000b2d1  jmp     short $+2
0x18000b2d3  jmp     rax
```
