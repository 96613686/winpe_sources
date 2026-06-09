# __tailMerge_user32_dll

- ea: `0x180006535`
- end: `0x1800065ae`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800065b4`
- `0x1800065c6`

## callees

- `0x1800046b0`
- `0x180006535`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006535  mov     [rsp+arg_0], rcx
0x18000653a  mov     [rsp+arg_8], rdx
0x18000653f  mov     [rsp+arg_10], r8
0x180006544  mov     [rsp+arg_18], r9
0x180006549  sub     rsp, 68h
0x18000654d  movdqa  [rsp+68h+var_48], xmm0
0x180006553  movdqa  [rsp+68h+var_38], xmm1
0x180006559  movdqa  [rsp+68h+var_28], xmm2
0x18000655f  movdqa  [rsp+68h+var_18], xmm3
0x180006565  mov     rdx, rax
0x180006568  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x18000656f  call    __delayLoadHelper2
0x180006574  movdqa  xmm0, [rsp+68h+var_48]
0x18000657a  movdqa  xmm1, [rsp+68h+var_38]
0x180006580  movdqa  xmm2, [rsp+68h+var_28]
0x180006586  movdqa  xmm3, [rsp+68h+var_18]
0x18000658c  mov     rcx, [rsp+68h+arg_0]
0x180006591  mov     rdx, [rsp+68h+arg_8]
0x180006596  mov     r8, [rsp+68h+arg_10]
0x18000659e  mov     r9, [rsp+68h+arg_18]
0x1800065a6  add     rsp, 68h
0x1800065aa  jmp     short $+2
0x1800065ac  jmp     rax
```
