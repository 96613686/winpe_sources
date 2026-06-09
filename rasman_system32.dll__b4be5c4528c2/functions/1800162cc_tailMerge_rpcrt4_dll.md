# __tailMerge_rpcrt4_dll

- ea: `0x1800162cc`
- end: `0x180016345`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001634b`
- `0x18001635d`
- `0x18001636f`
- `0x1800166b6`
- `0x1800166c8`
- `0x1800166da`
- `0x1800166ec`
- `0x1800166fe`

## callees

- `0x180014ae0`
- `0x1800162cc`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800162cc  mov     [rsp+arg_0], rcx
0x1800162d1  mov     [rsp+arg_8], rdx
0x1800162d6  mov     [rsp+arg_10], r8
0x1800162db  mov     [rsp+arg_18], r9
0x1800162e0  sub     rsp, 68h
0x1800162e4  movdqa  [rsp+68h+var_48], xmm0
0x1800162ea  movdqa  [rsp+68h+var_38], xmm1
0x1800162f0  movdqa  [rsp+68h+var_28], xmm2
0x1800162f6  movdqa  [rsp+68h+var_18], xmm3
0x1800162fc  mov     rdx, rax
0x1800162ff  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180016306  call    __delayLoadHelper2
0x18001630b  movdqa  xmm0, [rsp+68h+var_48]
0x180016311  movdqa  xmm1, [rsp+68h+var_38]
0x180016317  movdqa  xmm2, [rsp+68h+var_28]
0x18001631d  movdqa  xmm3, [rsp+68h+var_18]
0x180016323  mov     rcx, [rsp+68h+arg_0]
0x180016328  mov     rdx, [rsp+68h+arg_8]
0x18001632d  mov     r8, [rsp+68h+arg_10]
0x180016335  mov     r9, [rsp+68h+arg_18]
0x18001633d  add     rsp, 68h
0x180016341  jmp     short $+2
0x180016343  jmp     rax
```
