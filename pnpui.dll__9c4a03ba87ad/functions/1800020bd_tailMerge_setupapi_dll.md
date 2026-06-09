# __tailMerge_setupapi_dll

- ea: `0x1800020bd`
- end: `0x180002136`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000213c`
- `0x18000214e`
- `0x180002160`
- `0x180002172`
- `0x180002184`
- `0x180002196`
- `0x1800021a8`
- `0x1800021ba`
- `0x1800021cc`
- `0x1800021de`
- `0x1800021f0`
- `0x180002202`
- `0x180002214`
- `0x180002226`
- `0x180002238`

## callees

- `0x1800020bd`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_setupapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800020bd  mov     [rsp+arg_0], rcx
0x1800020c2  mov     [rsp+arg_8], rdx
0x1800020c7  mov     [rsp+arg_10], r8
0x1800020cc  mov     [rsp+arg_18], r9
0x1800020d1  sub     rsp, 68h
0x1800020d5  movdqa  [rsp+68h+var_48], xmm0
0x1800020db  movdqa  [rsp+68h+var_38], xmm1
0x1800020e1  movdqa  [rsp+68h+var_28], xmm2
0x1800020e7  movdqa  [rsp+68h+var_18], xmm3
0x1800020ed  mov     rdx, rax
0x1800020f0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x1800020f7  call    __delayLoadHelper2
0x1800020fc  movdqa  xmm0, [rsp+68h+var_48]
0x180002102  movdqa  xmm1, [rsp+68h+var_38]
0x180002108  movdqa  xmm2, [rsp+68h+var_28]
0x18000210e  movdqa  xmm3, [rsp+68h+var_18]
0x180002114  mov     rcx, [rsp+68h+arg_0]
0x180002119  mov     rdx, [rsp+68h+arg_8]
0x18000211e  mov     r8, [rsp+68h+arg_10]
0x180002126  mov     r9, [rsp+68h+arg_18]
0x18000212e  add     rsp, 68h
0x180002132  jmp     short $+2
0x180002134  jmp     rax
```
