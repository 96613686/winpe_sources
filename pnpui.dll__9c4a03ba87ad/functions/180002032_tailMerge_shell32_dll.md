# __tailMerge_shell32_dll

- ea: `0x180002032`
- end: `0x1800020ab`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020b1`

## callees

- `0x180002032`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002032  mov     [rsp+arg_0], rcx
0x180002037  mov     [rsp+arg_8], rdx
0x18000203c  mov     [rsp+arg_10], r8
0x180002041  mov     [rsp+arg_18], r9
0x180002046  sub     rsp, 68h
0x18000204a  movdqa  [rsp+68h+var_48], xmm0
0x180002050  movdqa  [rsp+68h+var_38], xmm1
0x180002056  movdqa  [rsp+68h+var_28], xmm2
0x18000205c  movdqa  [rsp+68h+var_18], xmm3
0x180002062  mov     rdx, rax
0x180002065  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x18000206c  call    __delayLoadHelper2
0x180002071  movdqa  xmm0, [rsp+68h+var_48]
0x180002077  movdqa  xmm1, [rsp+68h+var_38]
0x18000207d  movdqa  xmm2, [rsp+68h+var_28]
0x180002083  movdqa  xmm3, [rsp+68h+var_18]
0x180002089  mov     rcx, [rsp+68h+arg_0]
0x18000208e  mov     rdx, [rsp+68h+arg_8]
0x180002093  mov     r8, [rsp+68h+arg_10]
0x18000209b  mov     r9, [rsp+68h+arg_18]
0x1800020a3  add     rsp, 68h
0x1800020a7  jmp     short $+2
0x1800020a9  jmp     rax
```
