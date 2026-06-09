# __tailMerge_wkscli_dll

- ea: `0x1800035c4`
- end: `0x18000363d`
- name: `__tailMerge_wkscli_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003643`

## callees

- `0x1800015c0`
- `0x1800035c4`

## pseudocode

```c
__int64 __fastcall _tailMerge_wkscli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wkscli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800035c4  mov     [rsp+arg_0], rcx
0x1800035c9  mov     [rsp+arg_8], rdx
0x1800035ce  mov     [rsp+arg_10], r8
0x1800035d3  mov     [rsp+arg_18], r9
0x1800035d8  sub     rsp, 68h
0x1800035dc  movdqa  [rsp+68h+var_48], xmm0
0x1800035e2  movdqa  [rsp+68h+var_38], xmm1
0x1800035e8  movdqa  [rsp+68h+var_28], xmm2
0x1800035ee  movdqa  [rsp+68h+var_18], xmm3
0x1800035f4  mov     rdx, rax
0x1800035f7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wkscli_dll
0x1800035fe  call    __delayLoadHelper2
0x180003603  movdqa  xmm0, [rsp+68h+var_48]
0x180003609  movdqa  xmm1, [rsp+68h+var_38]
0x18000360f  movdqa  xmm2, [rsp+68h+var_28]
0x180003615  movdqa  xmm3, [rsp+68h+var_18]
0x18000361b  mov     rcx, [rsp+68h+arg_0]
0x180003620  mov     rdx, [rsp+68h+arg_8]
0x180003625  mov     r8, [rsp+68h+arg_10]
0x18000362d  mov     r9, [rsp+68h+arg_18]
0x180003635  add     rsp, 68h
0x180003639  jmp     short $+2
0x18000363b  jmp     rax
```
