# __tailMerge_oleaut32_dll

- ea: `0x180020af0`
- end: `0x180020b69`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020b6f`
- `0x180020b81`
- `0x180020c1e`
- `0x180020c30`
- `0x180020c42`

## callees

- `0x180018b30`
- `0x180020af0`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180020af0  mov     [rsp+arg_0], rcx
0x180020af5  mov     [rsp+arg_8], rdx
0x180020afa  mov     [rsp+arg_10], r8
0x180020aff  mov     [rsp+arg_18], r9
0x180020b04  sub     rsp, 68h
0x180020b08  movdqa  [rsp+68h+var_48], xmm0
0x180020b0e  movdqa  [rsp+68h+var_38], xmm1
0x180020b14  movdqa  [rsp+68h+var_28], xmm2
0x180020b1a  movdqa  [rsp+68h+var_18], xmm3
0x180020b20  mov     rdx, rax
0x180020b23  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180020b2a  call    __delayLoadHelper2
0x180020b2f  movdqa  xmm0, [rsp+68h+var_48]
0x180020b35  movdqa  xmm1, [rsp+68h+var_38]
0x180020b3b  movdqa  xmm2, [rsp+68h+var_28]
0x180020b41  movdqa  xmm3, [rsp+68h+var_18]
0x180020b47  mov     rcx, [rsp+68h+arg_0]
0x180020b4c  mov     rdx, [rsp+68h+arg_8]
0x180020b51  mov     r8, [rsp+68h+arg_10]
0x180020b59  mov     r9, [rsp+68h+arg_18]
0x180020b61  add     rsp, 68h
0x180020b65  jmp     short $+2
0x180020b67  jmp     rax
```
