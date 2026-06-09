# __tailMerge_oleaut32_dll

- ea: `0x18000200a`
- end: `0x180002083`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002089`

## callees

- `0x18000200a`
- `0x180006a30`

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
0x18000200a  mov     [rsp+arg_0], rcx
0x18000200f  mov     [rsp+arg_8], rdx
0x180002014  mov     [rsp+arg_10], r8
0x180002019  mov     [rsp+arg_18], r9
0x18000201e  sub     rsp, 68h
0x180002022  movdqa  [rsp+68h+var_48], xmm0
0x180002028  movdqa  [rsp+68h+var_38], xmm1
0x18000202e  movdqa  [rsp+68h+var_28], xmm2
0x180002034  movdqa  [rsp+68h+var_18], xmm3
0x18000203a  mov     rdx, rax
0x18000203d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180002044  call    __delayLoadHelper2
0x180002049  movdqa  xmm0, [rsp+68h+var_48]
0x18000204f  movdqa  xmm1, [rsp+68h+var_38]
0x180002055  movdqa  xmm2, [rsp+68h+var_28]
0x18000205b  movdqa  xmm3, [rsp+68h+var_18]
0x180002061  mov     rcx, [rsp+68h+arg_0]
0x180002066  mov     rdx, [rsp+68h+arg_8]
0x18000206b  mov     r8, [rsp+68h+arg_10]
0x180002073  mov     r9, [rsp+68h+arg_18]
0x18000207b  add     rsp, 68h
0x18000207f  jmp     short $+2
0x180002081  jmp     rax
```
