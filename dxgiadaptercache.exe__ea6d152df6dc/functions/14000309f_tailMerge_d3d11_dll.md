# __tailMerge_d3d11_dll

- ea: `0x14000309f`
- end: `0x140003118`
- name: `__tailMerge_d3d11_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000311e`

## callees

- `0x14000309f`
- `0x140011270`

## pseudocode

```c
__int64 __fastcall _tailMerge_d3d11_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_d3d11_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000309f  mov     [rsp+arg_0], rcx
0x1400030a4  mov     [rsp+arg_8], rdx
0x1400030a9  mov     [rsp+arg_10], r8
0x1400030ae  mov     [rsp+arg_18], r9
0x1400030b3  sub     rsp, 68h
0x1400030b7  movdqa  [rsp+68h+var_48], xmm0
0x1400030bd  movdqa  [rsp+68h+var_38], xmm1
0x1400030c3  movdqa  [rsp+68h+var_28], xmm2
0x1400030c9  movdqa  [rsp+68h+var_18], xmm3
0x1400030cf  mov     rdx, rax
0x1400030d2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_d3d11_dll
0x1400030d9  call    __delayLoadHelper2
0x1400030de  movdqa  xmm0, [rsp+68h+var_48]
0x1400030e4  movdqa  xmm1, [rsp+68h+var_38]
0x1400030ea  movdqa  xmm2, [rsp+68h+var_28]
0x1400030f0  movdqa  xmm3, [rsp+68h+var_18]
0x1400030f6  mov     rcx, [rsp+68h+arg_0]
0x1400030fb  mov     rdx, [rsp+68h+arg_8]
0x140003100  mov     r8, [rsp+68h+arg_10]
0x140003108  mov     r9, [rsp+68h+arg_18]
0x140003110  add     rsp, 68h
0x140003114  jmp     short $+2
0x140003116  jmp     rax
```
