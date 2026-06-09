# __tailMerge_bcrypt_dll

- ea: `0x180002260`
- end: `0x1800022d9`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022df`
- `0x1800022f1`
- `0x18000232c`
- `0x18000233e`
- `0x180002350`
- `0x180002362`

## callees

- `0x180002260`
- `0x180007e40`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002260  mov     [rsp+arg_0], rcx
0x180002265  mov     [rsp+arg_8], rdx
0x18000226a  mov     [rsp+arg_10], r8
0x18000226f  mov     [rsp+arg_18], r9
0x180002274  sub     rsp, 68h
0x180002278  movdqa  [rsp+68h+var_48], xmm0
0x18000227e  movdqa  [rsp+68h+var_38], xmm1
0x180002284  movdqa  [rsp+68h+var_28], xmm2
0x18000228a  movdqa  [rsp+68h+var_18], xmm3
0x180002290  mov     rdx, rax
0x180002293  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18000229a  call    __delayLoadHelper2
0x18000229f  movdqa  xmm0, [rsp+68h+var_48]
0x1800022a5  movdqa  xmm1, [rsp+68h+var_38]
0x1800022ab  movdqa  xmm2, [rsp+68h+var_28]
0x1800022b1  movdqa  xmm3, [rsp+68h+var_18]
0x1800022b7  mov     rcx, [rsp+68h+arg_0]
0x1800022bc  mov     rdx, [rsp+68h+arg_8]
0x1800022c1  mov     r8, [rsp+68h+arg_10]
0x1800022c9  mov     r9, [rsp+68h+arg_18]
0x1800022d1  add     rsp, 68h
0x1800022d5  jmp     short $+2
0x1800022d7  jmp     rax
```
