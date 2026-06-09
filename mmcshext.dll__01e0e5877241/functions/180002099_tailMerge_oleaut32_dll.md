# __tailMerge_oleaut32_dll

- ea: `0x180002099`
- end: `0x180002112`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002118`

## callees

- `0x180002099`
- `0x18000a390`

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
0x180002099  mov     [rsp+arg_0], rcx
0x18000209e  mov     [rsp+arg_8], rdx
0x1800020a3  mov     [rsp+arg_10], r8
0x1800020a8  mov     [rsp+arg_18], r9
0x1800020ad  sub     rsp, 68h
0x1800020b1  movdqa  [rsp+68h+var_48], xmm0
0x1800020b7  movdqa  [rsp+68h+var_38], xmm1
0x1800020bd  movdqa  [rsp+68h+var_28], xmm2
0x1800020c3  movdqa  [rsp+68h+var_18], xmm3
0x1800020c9  mov     rdx, rax
0x1800020cc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x1800020d3  call    __delayLoadHelper2
0x1800020d8  movdqa  xmm0, [rsp+68h+var_48]
0x1800020de  movdqa  xmm1, [rsp+68h+var_38]
0x1800020e4  movdqa  xmm2, [rsp+68h+var_28]
0x1800020ea  movdqa  xmm3, [rsp+68h+var_18]
0x1800020f0  mov     rcx, [rsp+68h+arg_0]
0x1800020f5  mov     rdx, [rsp+68h+arg_8]
0x1800020fa  mov     r8, [rsp+68h+arg_10]
0x180002102  mov     r9, [rsp+68h+arg_18]
0x18000210a  add     rsp, 68h
0x18000210e  jmp     short $+2
0x180002110  jmp     rax
```
