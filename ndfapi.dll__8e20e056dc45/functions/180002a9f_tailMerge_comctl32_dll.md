# __tailMerge_comctl32_dll

- ea: `0x180002a9f`
- end: `0x180002b18`
- name: `__tailMerge_comctl32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b1e`
- `0x180002b30`

## callees

- `0x180002a9f`
- `0x18001f560`

## pseudocode

```c
__int64 __fastcall _tailMerge_comctl32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_comctl32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a9f  mov     [rsp+arg_0], rcx
0x180002aa4  mov     [rsp+arg_8], rdx
0x180002aa9  mov     [rsp+arg_10], r8
0x180002aae  mov     [rsp+arg_18], r9
0x180002ab3  sub     rsp, 68h
0x180002ab7  movdqa  [rsp+68h+var_48], xmm0
0x180002abd  movdqa  [rsp+68h+var_38], xmm1
0x180002ac3  movdqa  [rsp+68h+var_28], xmm2
0x180002ac9  movdqa  [rsp+68h+var_18], xmm3
0x180002acf  mov     rdx, rax
0x180002ad2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comctl32_dll
0x180002ad9  call    __delayLoadHelper2
0x180002ade  movdqa  xmm0, [rsp+68h+var_48]
0x180002ae4  movdqa  xmm1, [rsp+68h+var_38]
0x180002aea  movdqa  xmm2, [rsp+68h+var_28]
0x180002af0  movdqa  xmm3, [rsp+68h+var_18]
0x180002af6  mov     rcx, [rsp+68h+arg_0]
0x180002afb  mov     rdx, [rsp+68h+arg_8]
0x180002b00  mov     r8, [rsp+68h+arg_10]
0x180002b08  mov     r9, [rsp+68h+arg_18]
0x180002b10  add     rsp, 68h
0x180002b14  jmp     short $+2
0x180002b16  jmp     rax
```
