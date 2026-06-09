# __tailMerge_dmcmnutils_dll

- ea: `0x180002b24`
- end: `0x180002b9d`
- name: `__tailMerge_dmcmnutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ba3`

## callees

- `0x180002b24`
- `0x180011ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmcmnutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dmcmnutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b24  mov     [rsp+arg_0], rcx
0x180002b29  mov     [rsp+arg_8], rdx
0x180002b2e  mov     [rsp+arg_10], r8
0x180002b33  mov     [rsp+arg_18], r9
0x180002b38  sub     rsp, 68h
0x180002b3c  movdqa  [rsp+68h+var_48], xmm0
0x180002b42  movdqa  [rsp+68h+var_38], xmm1
0x180002b48  movdqa  [rsp+68h+var_28], xmm2
0x180002b4e  movdqa  [rsp+68h+var_18], xmm3
0x180002b54  mov     rdx, rax
0x180002b57  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmcmnutils_dll
0x180002b5e  call    __delayLoadHelper2
0x180002b63  movdqa  xmm0, [rsp+68h+var_48]
0x180002b69  movdqa  xmm1, [rsp+68h+var_38]
0x180002b6f  movdqa  xmm2, [rsp+68h+var_28]
0x180002b75  movdqa  xmm3, [rsp+68h+var_18]
0x180002b7b  mov     rcx, [rsp+68h+arg_0]
0x180002b80  mov     rdx, [rsp+68h+arg_8]
0x180002b85  mov     r8, [rsp+68h+arg_10]
0x180002b8d  mov     r9, [rsp+68h+arg_18]
0x180002b95  add     rsp, 68h
0x180002b99  jmp     short $+2
0x180002b9b  jmp     rax
```
