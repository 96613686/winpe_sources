# __tailMerge_ws2_32_dll

- ea: `0x18000d9c6`
- end: `0x18000da3f`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000da45`
- `0x18000daf4`
- `0x18000db06`
- `0x18000db18`
- `0x18000db2a`
- `0x18000db3c`
- `0x18000db4e`
- `0x18000db60`
- `0x18000db72`
- `0x18000db84`
- `0x18000db96`
- `0x18000dba8`
- `0x18000dc45`

## callees

- `0x18000bd60`
- `0x18000d9c6`

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
0x18000d9c6  mov     [rsp+arg_0], rcx
0x18000d9cb  mov     [rsp+arg_8], rdx
0x18000d9d0  mov     [rsp+arg_10], r8
0x18000d9d5  mov     [rsp+arg_18], r9
0x18000d9da  sub     rsp, 68h
0x18000d9de  movdqa  [rsp+68h+var_48], xmm0
0x18000d9e4  movdqa  [rsp+68h+var_38], xmm1
0x18000d9ea  movdqa  [rsp+68h+var_28], xmm2
0x18000d9f0  movdqa  [rsp+68h+var_18], xmm3
0x18000d9f6  mov     rdx, rax
0x18000d9f9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18000da00  call    __delayLoadHelper2
0x18000da05  movdqa  xmm0, [rsp+68h+var_48]
0x18000da0b  movdqa  xmm1, [rsp+68h+var_38]
0x18000da11  movdqa  xmm2, [rsp+68h+var_28]
0x18000da17  movdqa  xmm3, [rsp+68h+var_18]
0x18000da1d  mov     rcx, [rsp+68h+arg_0]
0x18000da22  mov     rdx, [rsp+68h+arg_8]
0x18000da27  mov     r8, [rsp+68h+arg_10]
0x18000da2f  mov     r9, [rsp+68h+arg_18]
0x18000da37  add     rsp, 68h
0x18000da3b  jmp     short $+2
0x18000da3d  jmp     rax
```
