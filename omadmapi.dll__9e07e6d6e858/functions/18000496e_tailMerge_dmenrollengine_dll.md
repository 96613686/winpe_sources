# __tailMerge_dmenrollengine_dll

- ea: `0x18000496e`
- end: `0x1800049e7`
- name: `__tailMerge_dmenrollengine_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800049ed`
- `0x180004e00`

## callees

- `0x18000496e`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmenrollengine_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_dmenrollengine_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000496e  mov     [rsp+arg_0], rcx
0x180004973  mov     [rsp+arg_8], rdx
0x180004978  mov     [rsp+arg_10], r8
0x18000497d  mov     [rsp+arg_18], r9
0x180004982  sub     rsp, 68h
0x180004986  movdqa  [rsp+68h+var_48], xmm0
0x18000498c  movdqa  [rsp+68h+var_38], xmm1
0x180004992  movdqa  [rsp+68h+var_28], xmm2
0x180004998  movdqa  [rsp+68h+var_18], xmm3
0x18000499e  mov     rdx, rax
0x1800049a1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmenrollengine_dll
0x1800049a8  call    __delayLoadHelper2
0x1800049ad  movdqa  xmm0, [rsp+68h+var_48]
0x1800049b3  movdqa  xmm1, [rsp+68h+var_38]
0x1800049b9  movdqa  xmm2, [rsp+68h+var_28]
0x1800049bf  movdqa  xmm3, [rsp+68h+var_18]
0x1800049c5  mov     rcx, [rsp+68h+arg_0]
0x1800049ca  mov     rdx, [rsp+68h+arg_8]
0x1800049cf  mov     r8, [rsp+68h+arg_10]
0x1800049d7  mov     r9, [rsp+68h+arg_18]
0x1800049df  add     rsp, 68h
0x1800049e3  jmp     short $+2
0x1800049e5  jmp     rax
```
