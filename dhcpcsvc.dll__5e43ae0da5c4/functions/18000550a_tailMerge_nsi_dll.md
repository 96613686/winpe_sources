# __tailMerge_nsi_dll

- ea: `0x18000550a`
- end: `0x180005583`
- name: `__tailMerge_nsi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005589`

## callees

- `0x1800030d0`
- `0x18000550a`

## pseudocode

```c
__int64 __fastcall _tailMerge_nsi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_nsi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000550a  mov     [rsp+arg_0], rcx
0x18000550f  mov     [rsp+arg_8], rdx
0x180005514  mov     [rsp+arg_10], r8
0x180005519  mov     [rsp+arg_18], r9
0x18000551e  sub     rsp, 68h
0x180005522  movdqa  [rsp+68h+var_48], xmm0
0x180005528  movdqa  [rsp+68h+var_38], xmm1
0x18000552e  movdqa  [rsp+68h+var_28], xmm2
0x180005534  movdqa  [rsp+68h+var_18], xmm3
0x18000553a  mov     rdx, rax
0x18000553d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_nsi_dll
0x180005544  call    __delayLoadHelper2
0x180005549  movdqa  xmm0, [rsp+68h+var_48]
0x18000554f  movdqa  xmm1, [rsp+68h+var_38]
0x180005555  movdqa  xmm2, [rsp+68h+var_28]
0x18000555b  movdqa  xmm3, [rsp+68h+var_18]
0x180005561  mov     rcx, [rsp+68h+arg_0]
0x180005566  mov     rdx, [rsp+68h+arg_8]
0x18000556b  mov     r8, [rsp+68h+arg_10]
0x180005573  mov     r9, [rsp+68h+arg_18]
0x18000557b  add     rsp, 68h
0x18000557f  jmp     short $+2
0x180005581  jmp     rax
```
