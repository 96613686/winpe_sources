# __tailMerge_netutils_dll

- ea: `0x18000ac4f`
- end: `0x18000acc8`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000acce`

## callees

- `0x1800079c0`
- `0x18000ac4f`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ac4f  mov     [rsp+arg_0], rcx
0x18000ac54  mov     [rsp+arg_8], rdx
0x18000ac59  mov     [rsp+arg_10], r8
0x18000ac5e  mov     [rsp+arg_18], r9
0x18000ac63  sub     rsp, 68h
0x18000ac67  movdqa  [rsp+68h+var_48], xmm0
0x18000ac6d  movdqa  [rsp+68h+var_38], xmm1
0x18000ac73  movdqa  [rsp+68h+var_28], xmm2
0x18000ac79  movdqa  [rsp+68h+var_18], xmm3
0x18000ac7f  mov     rdx, rax
0x18000ac82  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18000ac89  call    __delayLoadHelper2
0x18000ac8e  movdqa  xmm0, [rsp+68h+var_48]
0x18000ac94  movdqa  xmm1, [rsp+68h+var_38]
0x18000ac9a  movdqa  xmm2, [rsp+68h+var_28]
0x18000aca0  movdqa  xmm3, [rsp+68h+var_18]
0x18000aca6  mov     rcx, [rsp+68h+arg_0]
0x18000acab  mov     rdx, [rsp+68h+arg_8]
0x18000acb0  mov     r8, [rsp+68h+arg_10]
0x18000acb8  mov     r9, [rsp+68h+arg_18]
0x18000acc0  add     rsp, 68h
0x18000acc4  jmp     short $+2
0x18000acc6  jmp     rax
```
