# __tailMerge_wldap32_dll

- ea: `0x18001bfd1`
- end: `0x18001c04a`
- name: `__tailMerge_wldap32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c050`
- `0x18001c1ae`
- `0x18001c1c0`
- `0x18001c1d2`
- `0x18001c1e4`
- `0x18001c1f6`
- `0x18001c208`
- `0x18001c21a`
- `0x18001c22c`
- `0x18001c23e`
- `0x18001c250`
- `0x18001c262`
- `0x18001c274`
- `0x18001c286`
- `0x18001c298`
- `0x18001c2aa`
- `0x18001c2bc`
- `0x18001c2ce`
- `0x18001c2e0`
- `0x18001c2f2`

## callees

- `0x1800187e0`
- `0x18001bfd1`

## pseudocode

```c
__int64 __fastcall _tailMerge_wldap32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wldap32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001bfd1  mov     [rsp+arg_0], rcx
0x18001bfd6  mov     [rsp+arg_8], rdx
0x18001bfdb  mov     [rsp+arg_10], r8
0x18001bfe0  mov     [rsp+arg_18], r9
0x18001bfe5  sub     rsp, 68h
0x18001bfe9  movdqa  [rsp+68h+var_48], xmm0
0x18001bfef  movdqa  [rsp+68h+var_38], xmm1
0x18001bff5  movdqa  [rsp+68h+var_28], xmm2
0x18001bffb  movdqa  [rsp+68h+var_18], xmm3
0x18001c001  mov     rdx, rax
0x18001c004  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wldap32_dll
0x18001c00b  call    __delayLoadHelper2
0x18001c010  movdqa  xmm0, [rsp+68h+var_48]
0x18001c016  movdqa  xmm1, [rsp+68h+var_38]
0x18001c01c  movdqa  xmm2, [rsp+68h+var_28]
0x18001c022  movdqa  xmm3, [rsp+68h+var_18]
0x18001c028  mov     rcx, [rsp+68h+arg_0]
0x18001c02d  mov     rdx, [rsp+68h+arg_8]
0x18001c032  mov     r8, [rsp+68h+arg_10]
0x18001c03a  mov     r9, [rsp+68h+arg_18]
0x18001c042  add     rsp, 68h
0x18001c046  jmp     short $+2
0x18001c048  jmp     rax
```
