# __tailMerge_sspicli_dll

- ea: `0x1800061b8`
- end: `0x180006231`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006237`

## callees

- `0x1800046b0`
- `0x1800061b8`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800061b8  mov     [rsp+arg_0], rcx
0x1800061bd  mov     [rsp+arg_8], rdx
0x1800061c2  mov     [rsp+arg_10], r8
0x1800061c7  mov     [rsp+arg_18], r9
0x1800061cc  sub     rsp, 68h
0x1800061d0  movdqa  [rsp+68h+var_48], xmm0
0x1800061d6  movdqa  [rsp+68h+var_38], xmm1
0x1800061dc  movdqa  [rsp+68h+var_28], xmm2
0x1800061e2  movdqa  [rsp+68h+var_18], xmm3
0x1800061e8  mov     rdx, rax
0x1800061eb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x1800061f2  call    __delayLoadHelper2
0x1800061f7  movdqa  xmm0, [rsp+68h+var_48]
0x1800061fd  movdqa  xmm1, [rsp+68h+var_38]
0x180006203  movdqa  xmm2, [rsp+68h+var_28]
0x180006209  movdqa  xmm3, [rsp+68h+var_18]
0x18000620f  mov     rcx, [rsp+68h+arg_0]
0x180006214  mov     rdx, [rsp+68h+arg_8]
0x180006219  mov     r8, [rsp+68h+arg_10]
0x180006221  mov     r9, [rsp+68h+arg_18]
0x180006229  add     rsp, 68h
0x18000622d  jmp     short $+2
0x18000622f  jmp     rax
```
