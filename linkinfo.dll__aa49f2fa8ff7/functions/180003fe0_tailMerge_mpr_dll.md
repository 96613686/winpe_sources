# __tailMerge_mpr_dll

- ea: `0x180003fe0`
- end: `0x180004059`
- name: `__tailMerge_mpr_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000405f`
- `0x18000410e`
- `0x180004120`
- `0x180004132`
- `0x180004144`
- `0x180004156`
- `0x180004168`
- `0x18000417a`
- `0x18000418c`

## callees

- `0x1800036d0`
- `0x180003fe0`

## pseudocode

```c
__int64 __fastcall _tailMerge_mpr_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_mpr_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003fe0  mov     [rsp+arg_0], rcx
0x180003fe5  mov     [rsp+arg_8], rdx
0x180003fea  mov     [rsp+arg_10], r8
0x180003fef  mov     [rsp+arg_18], r9
0x180003ff4  sub     rsp, 68h
0x180003ff8  movdqa  [rsp+68h+var_48], xmm0
0x180003ffe  movdqa  [rsp+68h+var_38], xmm1
0x180004004  movdqa  [rsp+68h+var_28], xmm2
0x18000400a  movdqa  [rsp+68h+var_18], xmm3
0x180004010  mov     rdx, rax
0x180004013  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mpr_dll
0x18000401a  call    __delayLoadHelper2
0x18000401f  movdqa  xmm0, [rsp+68h+var_48]
0x180004025  movdqa  xmm1, [rsp+68h+var_38]
0x18000402b  movdqa  xmm2, [rsp+68h+var_28]
0x180004031  movdqa  xmm3, [rsp+68h+var_18]
0x180004037  mov     rcx, [rsp+68h+arg_0]
0x18000403c  mov     rdx, [rsp+68h+arg_8]
0x180004041  mov     r8, [rsp+68h+arg_10]
0x180004049  mov     r9, [rsp+68h+arg_18]
0x180004051  add     rsp, 68h
0x180004055  jmp     short $+2
0x180004057  jmp     rax
```
