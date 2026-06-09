# __tailMerge_oleaut32_dll

- ea: `0x18000bb07`
- end: `0x18000bb80`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bb86`
- `0x18000bb98`

## callees

- `0x1800089e0`
- `0x18000bb07`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000bb07  mov     [rsp+arg_0], rcx
0x18000bb0c  mov     [rsp+arg_8], rdx
0x18000bb11  mov     [rsp+arg_10], r8
0x18000bb16  mov     [rsp+arg_18], r9
0x18000bb1b  sub     rsp, 68h
0x18000bb1f  movdqa  [rsp+68h+var_48], xmm0
0x18000bb25  movdqa  [rsp+68h+var_38], xmm1
0x18000bb2b  movdqa  [rsp+68h+var_28], xmm2
0x18000bb31  movdqa  [rsp+68h+var_18], xmm3
0x18000bb37  mov     rdx, rax
0x18000bb3a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000bb41  call    __delayLoadHelper2
0x18000bb46  movdqa  xmm0, [rsp+68h+var_48]
0x18000bb4c  movdqa  xmm1, [rsp+68h+var_38]
0x18000bb52  movdqa  xmm2, [rsp+68h+var_28]
0x18000bb58  movdqa  xmm3, [rsp+68h+var_18]
0x18000bb5e  mov     rcx, [rsp+68h+arg_0]
0x18000bb63  mov     rdx, [rsp+68h+arg_8]
0x18000bb68  mov     r8, [rsp+68h+arg_10]
0x18000bb70  mov     r9, [rsp+68h+arg_18]
0x18000bb78  add     rsp, 68h
0x18000bb7c  jmp     short $+2
0x18000bb7e  jmp     rax
```
