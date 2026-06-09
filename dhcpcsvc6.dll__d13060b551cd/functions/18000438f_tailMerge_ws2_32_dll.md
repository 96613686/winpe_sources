# __tailMerge_ws2_32_dll

- ea: `0x18000438f`
- end: `0x180004408`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000440e`
- `0x180004420`
- `0x180004432`

## callees

- `0x1800025a0`
- `0x18000438f`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000438f  mov     [rsp+arg_0], rcx
0x180004394  mov     [rsp+arg_8], rdx
0x180004399  mov     [rsp+arg_10], r8
0x18000439e  mov     [rsp+arg_18], r9
0x1800043a3  sub     rsp, 68h
0x1800043a7  movdqa  [rsp+68h+var_48], xmm0
0x1800043ad  movdqa  [rsp+68h+var_38], xmm1
0x1800043b3  movdqa  [rsp+68h+var_28], xmm2
0x1800043b9  movdqa  [rsp+68h+var_18], xmm3
0x1800043bf  mov     rdx, rax
0x1800043c2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x1800043c9  call    __delayLoadHelper2
0x1800043ce  movdqa  xmm0, [rsp+68h+var_48]
0x1800043d4  movdqa  xmm1, [rsp+68h+var_38]
0x1800043da  movdqa  xmm2, [rsp+68h+var_28]
0x1800043e0  movdqa  xmm3, [rsp+68h+var_18]
0x1800043e6  mov     rcx, [rsp+68h+arg_0]
0x1800043eb  mov     rdx, [rsp+68h+arg_8]
0x1800043f0  mov     r8, [rsp+68h+arg_10]
0x1800043f8  mov     r9, [rsp+68h+arg_18]
0x180004400  add     rsp, 68h
0x180004404  jmp     short $+2
0x180004406  jmp     rax
```
