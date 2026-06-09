# __tailMerge_profapi_dll

- ea: `0x18000f0ea`
- end: `0x18000f163`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f169`
- `0x18000f17b`

## callees

- `0x18000bd20`
- `0x18000f0ea`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f0ea  mov     [rsp+arg_0], rcx
0x18000f0ef  mov     [rsp+arg_8], rdx
0x18000f0f4  mov     [rsp+arg_10], r8
0x18000f0f9  mov     [rsp+arg_18], r9
0x18000f0fe  sub     rsp, 68h
0x18000f102  movdqa  [rsp+68h+var_48], xmm0
0x18000f108  movdqa  [rsp+68h+var_38], xmm1
0x18000f10e  movdqa  [rsp+68h+var_28], xmm2
0x18000f114  movdqa  [rsp+68h+var_18], xmm3
0x18000f11a  mov     rdx, rax
0x18000f11d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x18000f124  call    __delayLoadHelper2
0x18000f129  movdqa  xmm0, [rsp+68h+var_48]
0x18000f12f  movdqa  xmm1, [rsp+68h+var_38]
0x18000f135  movdqa  xmm2, [rsp+68h+var_28]
0x18000f13b  movdqa  xmm3, [rsp+68h+var_18]
0x18000f141  mov     rcx, [rsp+68h+arg_0]
0x18000f146  mov     rdx, [rsp+68h+arg_8]
0x18000f14b  mov     r8, [rsp+68h+arg_10]
0x18000f153  mov     r9, [rsp+68h+arg_18]
0x18000f15b  add     rsp, 68h
0x18000f15f  jmp     short $+2
0x18000f161  jmp     rax
```
