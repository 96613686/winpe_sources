# __tailMerge_crypt32_dll

- ea: `0x1800018c0`
- end: `0x180001939`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000193f`
- `0x180001951`
- `0x180001963`
- `0x180001975`

## callees

- `0x1800018c0`
- `0x180003d10`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800018c0  mov     [rsp+arg_0], rcx
0x1800018c5  mov     [rsp+arg_8], rdx
0x1800018ca  mov     [rsp+arg_10], r8
0x1800018cf  mov     [rsp+arg_18], r9
0x1800018d4  sub     rsp, 68h
0x1800018d8  movdqa  [rsp+68h+var_48], xmm0
0x1800018de  movdqa  [rsp+68h+var_38], xmm1
0x1800018e4  movdqa  [rsp+68h+var_28], xmm2
0x1800018ea  movdqa  [rsp+68h+var_18], xmm3
0x1800018f0  mov     rdx, rax
0x1800018f3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x1800018fa  call    __delayLoadHelper2
0x1800018ff  movdqa  xmm0, [rsp+68h+var_48]
0x180001905  movdqa  xmm1, [rsp+68h+var_38]
0x18000190b  movdqa  xmm2, [rsp+68h+var_28]
0x180001911  movdqa  xmm3, [rsp+68h+var_18]
0x180001917  mov     rcx, [rsp+68h+arg_0]
0x18000191c  mov     rdx, [rsp+68h+arg_8]
0x180001921  mov     r8, [rsp+68h+arg_10]
0x180001929  mov     r9, [rsp+68h+arg_18]
0x180001931  add     rsp, 68h
0x180001935  jmp     short $+2
0x180001937  jmp     rax
```
