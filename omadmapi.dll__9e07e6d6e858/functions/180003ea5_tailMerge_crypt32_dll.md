# __tailMerge_crypt32_dll

- ea: `0x180003ea5`
- end: `0x180003f1e`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003f24`
- `0x180003f36`
- `0x180003f48`

## callees

- `0x180003ea5`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003ea5  mov     [rsp+arg_0], rcx
0x180003eaa  mov     [rsp+arg_8], rdx
0x180003eaf  mov     [rsp+arg_10], r8
0x180003eb4  mov     [rsp+arg_18], r9
0x180003eb9  sub     rsp, 68h
0x180003ebd  movdqa  [rsp+68h+var_48], xmm0
0x180003ec3  movdqa  [rsp+68h+var_38], xmm1
0x180003ec9  movdqa  [rsp+68h+var_28], xmm2
0x180003ecf  movdqa  [rsp+68h+var_18], xmm3
0x180003ed5  mov     rdx, rax
0x180003ed8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180003edf  call    __delayLoadHelper2
0x180003ee4  movdqa  xmm0, [rsp+68h+var_48]
0x180003eea  movdqa  xmm1, [rsp+68h+var_38]
0x180003ef0  movdqa  xmm2, [rsp+68h+var_28]
0x180003ef6  movdqa  xmm3, [rsp+68h+var_18]
0x180003efc  mov     rcx, [rsp+68h+arg_0]
0x180003f01  mov     rdx, [rsp+68h+arg_8]
0x180003f06  mov     r8, [rsp+68h+arg_10]
0x180003f0e  mov     r9, [rsp+68h+arg_18]
0x180003f16  add     rsp, 68h
0x180003f1a  jmp     short $+2
0x180003f1c  jmp     rax
```
