# __tailMerge_ws2_32_dll

- ea: `0x140001dfe`
- end: `0x140001e77`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001e7d`

## callees

- `0x140001dfe`
- `0x14000f930`

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
0x140001dfe  mov     [rsp+arg_0], rcx
0x140001e03  mov     [rsp+arg_8], rdx
0x140001e08  mov     [rsp+arg_10], r8
0x140001e0d  mov     [rsp+arg_18], r9
0x140001e12  sub     rsp, 68h
0x140001e16  movdqa  [rsp+68h+var_48], xmm0
0x140001e1c  movdqa  [rsp+68h+var_38], xmm1
0x140001e22  movdqa  [rsp+68h+var_28], xmm2
0x140001e28  movdqa  [rsp+68h+var_18], xmm3
0x140001e2e  mov     rdx, rax
0x140001e31  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x140001e38  call    __delayLoadHelper2
0x140001e3d  movdqa  xmm0, [rsp+68h+var_48]
0x140001e43  movdqa  xmm1, [rsp+68h+var_38]
0x140001e49  movdqa  xmm2, [rsp+68h+var_28]
0x140001e4f  movdqa  xmm3, [rsp+68h+var_18]
0x140001e55  mov     rcx, [rsp+68h+arg_0]
0x140001e5a  mov     rdx, [rsp+68h+arg_8]
0x140001e5f  mov     r8, [rsp+68h+arg_10]
0x140001e67  mov     r9, [rsp+68h+arg_18]
0x140001e6f  add     rsp, 68h
0x140001e73  jmp     short $+2
0x140001e75  jmp     rax
```
