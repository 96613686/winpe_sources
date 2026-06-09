# __tailMerge_ws2_32_dll

- ea: `0x180016010`
- end: `0x180016089`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001608f`
- `0x18001613e`
- `0x1800161ff`

## callees

- `0x180014ae0`
- `0x180016010`

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
0x180016010  mov     [rsp+arg_0], rcx
0x180016015  mov     [rsp+arg_8], rdx
0x18001601a  mov     [rsp+arg_10], r8
0x18001601f  mov     [rsp+arg_18], r9
0x180016024  sub     rsp, 68h
0x180016028  movdqa  [rsp+68h+var_48], xmm0
0x18001602e  movdqa  [rsp+68h+var_38], xmm1
0x180016034  movdqa  [rsp+68h+var_28], xmm2
0x18001603a  movdqa  [rsp+68h+var_18], xmm3
0x180016040  mov     rdx, rax
0x180016043  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18001604a  call    __delayLoadHelper2
0x18001604f  movdqa  xmm0, [rsp+68h+var_48]
0x180016055  movdqa  xmm1, [rsp+68h+var_38]
0x18001605b  movdqa  xmm2, [rsp+68h+var_28]
0x180016061  movdqa  xmm3, [rsp+68h+var_18]
0x180016067  mov     rcx, [rsp+68h+arg_0]
0x18001606c  mov     rdx, [rsp+68h+arg_8]
0x180016071  mov     r8, [rsp+68h+arg_10]
0x180016079  mov     r9, [rsp+68h+arg_18]
0x180016081  add     rsp, 68h
0x180016085  jmp     short $+2
0x180016087  jmp     rax
```
