# __tailMerge_dmcmnutils_dll

- ea: `0x1800045f9`
- end: `0x180004672`
- name: `__tailMerge_dmcmnutils_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004678`
- `0x18000468a`
- `0x18000469c`
- `0x1800046ae`
- `0x1800046c0`
- `0x1800046d2`
- `0x1800046e4`
- `0x1800046f6`
- `0x180004708`
- `0x18000471a`
- `0x18000472c`
- `0x18000473e`
- `0x180004750`
- `0x180004762`
- `0x180004774`
- `0x180004786`
- `0x180004798`
- `0x1800047aa`
- `0x1800047bc`
- `0x1800047ce`
- `0x1800047e0`
- `0x1800047f2`

## callees

- `0x1800045f9`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmcmnutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_dmcmnutils_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800045f9  mov     [rsp+arg_0], rcx
0x1800045fe  mov     [rsp+arg_8], rdx
0x180004603  mov     [rsp+arg_10], r8
0x180004608  mov     [rsp+arg_18], r9
0x18000460d  sub     rsp, 68h
0x180004611  movdqa  [rsp+68h+var_48], xmm0
0x180004617  movdqa  [rsp+68h+var_38], xmm1
0x18000461d  movdqa  [rsp+68h+var_28], xmm2
0x180004623  movdqa  [rsp+68h+var_18], xmm3
0x180004629  mov     rdx, rax
0x18000462c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmcmnutils_dll
0x180004633  call    __delayLoadHelper2
0x180004638  movdqa  xmm0, [rsp+68h+var_48]
0x18000463e  movdqa  xmm1, [rsp+68h+var_38]
0x180004644  movdqa  xmm2, [rsp+68h+var_28]
0x18000464a  movdqa  xmm3, [rsp+68h+var_18]
0x180004650  mov     rcx, [rsp+68h+arg_0]
0x180004655  mov     rdx, [rsp+68h+arg_8]
0x18000465a  mov     r8, [rsp+68h+arg_10]
0x180004662  mov     r9, [rsp+68h+arg_18]
0x18000466a  add     rsp, 68h
0x18000466e  jmp     short $+2
0x180004670  jmp     rax
```
