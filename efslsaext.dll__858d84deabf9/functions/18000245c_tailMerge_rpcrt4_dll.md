# __tailMerge_rpcrt4_dll

- ea: `0x18000245c`
- end: `0x1800024d5`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800024db`
- `0x1800024fc`
- `0x18000251c`
- `0x18000252e`
- `0x180002540`
- `0x180002552`
- `0x180002564`
- `0x180002576`
- `0x180002588`
- `0x18000259a`
- `0x18000274d`
- `0x18000275f`
- `0x1800028cf`
- `0x1800028e1`
- `0x1800028f3`
- `0x180002905`
- `0x180002917`
- `0x180002929`
- `0x18000293b`
- `0x1800029ea`
- `0x1800029fc`

## callees

- `0x18000245c`
- `0x180007f20`

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
0x18000245c  mov     [rsp+arg_0], rcx
0x180002461  mov     [rsp+arg_8], rdx
0x180002466  mov     [rsp+arg_10], r8
0x18000246b  mov     [rsp+arg_18], r9
0x180002470  sub     rsp, 68h
0x180002474  movdqa  [rsp+68h+var_48], xmm0
0x18000247a  movdqa  [rsp+68h+var_38], xmm1
0x180002480  movdqa  [rsp+68h+var_28], xmm2
0x180002486  movdqa  [rsp+68h+var_18], xmm3
0x18000248c  mov     rdx, rax
0x18000248f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180002496  call    __delayLoadHelper2
0x18000249b  movdqa  xmm0, [rsp+68h+var_48]
0x1800024a1  movdqa  xmm1, [rsp+68h+var_38]
0x1800024a7  movdqa  xmm2, [rsp+68h+var_28]
0x1800024ad  movdqa  xmm3, [rsp+68h+var_18]
0x1800024b3  mov     rcx, [rsp+68h+arg_0]
0x1800024b8  mov     rdx, [rsp+68h+arg_8]
0x1800024bd  mov     r8, [rsp+68h+arg_10]
0x1800024c5  mov     r9, [rsp+68h+arg_18]
0x1800024cd  add     rsp, 68h
0x1800024d1  jmp     short $+2
0x1800024d3  jmp     rax
```
