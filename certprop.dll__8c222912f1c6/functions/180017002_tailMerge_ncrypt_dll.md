# __tailMerge_ncrypt_dll

- ea: `0x180017002`
- end: `0x18001707b`
- name: `__tailMerge_ncrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017081`
- `0x180017093`
- `0x1800170a5`
- `0x1800170b7`
- `0x1800170c9`
- `0x1800170db`
- `0x1800170ed`

## callees

- `0x18000e1a0`
- `0x180017002`

## pseudocode

```c
__int64 __fastcall _tailMerge_ncrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ncrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180017002  mov     [rsp+arg_0], rcx
0x180017007  mov     [rsp+arg_8], rdx
0x18001700c  mov     [rsp+arg_10], r8
0x180017011  mov     [rsp+arg_18], r9
0x180017016  sub     rsp, 68h
0x18001701a  movdqa  [rsp+68h+var_48], xmm0
0x180017020  movdqa  [rsp+68h+var_38], xmm1
0x180017026  movdqa  [rsp+68h+var_28], xmm2
0x18001702c  movdqa  [rsp+68h+var_18], xmm3
0x180017032  mov     rdx, rax
0x180017035  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ncrypt_dll
0x18001703c  call    __delayLoadHelper2
0x180017041  movdqa  xmm0, [rsp+68h+var_48]
0x180017047  movdqa  xmm1, [rsp+68h+var_38]
0x18001704d  movdqa  xmm2, [rsp+68h+var_28]
0x180017053  movdqa  xmm3, [rsp+68h+var_18]
0x180017059  mov     rcx, [rsp+68h+arg_0]
0x18001705e  mov     rdx, [rsp+68h+arg_8]
0x180017063  mov     r8, [rsp+68h+arg_10]
0x18001706b  mov     r9, [rsp+68h+arg_18]
0x180017073  add     rsp, 68h
0x180017077  jmp     short $+2
0x180017079  jmp     rax
```
