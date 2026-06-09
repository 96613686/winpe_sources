# __tailMerge_declaredconfiguration_dll

- ea: `0x1800049f9`
- end: `0x180004a72`
- name: `__tailMerge_declaredconfiguration_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004a78`

## callees

- `0x1800049f9`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_declaredconfiguration_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_declaredconfiguration_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800049f9  mov     [rsp+arg_0], rcx
0x1800049fe  mov     [rsp+arg_8], rdx
0x180004a03  mov     [rsp+arg_10], r8
0x180004a08  mov     [rsp+arg_18], r9
0x180004a0d  sub     rsp, 68h
0x180004a11  movdqa  [rsp+68h+var_48], xmm0
0x180004a17  movdqa  [rsp+68h+var_38], xmm1
0x180004a1d  movdqa  [rsp+68h+var_28], xmm2
0x180004a23  movdqa  [rsp+68h+var_18], xmm3
0x180004a29  mov     rdx, rax
0x180004a2c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_declaredconfiguration_dll
0x180004a33  call    __delayLoadHelper2
0x180004a38  movdqa  xmm0, [rsp+68h+var_48]
0x180004a3e  movdqa  xmm1, [rsp+68h+var_38]
0x180004a44  movdqa  xmm2, [rsp+68h+var_28]
0x180004a4a  movdqa  xmm3, [rsp+68h+var_18]
0x180004a50  mov     rcx, [rsp+68h+arg_0]
0x180004a55  mov     rdx, [rsp+68h+arg_8]
0x180004a5a  mov     r8, [rsp+68h+arg_10]
0x180004a62  mov     r9, [rsp+68h+arg_18]
0x180004a6a  add     rsp, 68h
0x180004a6e  jmp     short $+2
0x180004a70  jmp     rax
```
