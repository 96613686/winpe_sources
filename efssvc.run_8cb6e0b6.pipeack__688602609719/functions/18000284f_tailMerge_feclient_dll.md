# __tailMerge_feclient_dll

- ea: `0x18000284f`
- end: `0x1800028c8`
- name: `__tailMerge_feclient_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800028ce`

## callees

- `0x18000284f`
- `0x180008790`

## pseudocode

```c
__int64 __fastcall _tailMerge_feclient_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_feclient_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000284f  mov     [rsp+arg_0], rcx
0x180002854  mov     [rsp+arg_8], rdx
0x180002859  mov     [rsp+arg_10], r8
0x18000285e  mov     [rsp+arg_18], r9
0x180002863  sub     rsp, 68h
0x180002867  movdqa  [rsp+68h+var_48], xmm0
0x18000286d  movdqa  [rsp+68h+var_38], xmm1
0x180002873  movdqa  [rsp+68h+var_28], xmm2
0x180002879  movdqa  [rsp+68h+var_18], xmm3
0x18000287f  mov     rdx, rax
0x180002882  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_feclient_dll
0x180002889  call    __delayLoadHelper2
0x18000288e  movdqa  xmm0, [rsp+68h+var_48]
0x180002894  movdqa  xmm1, [rsp+68h+var_38]
0x18000289a  movdqa  xmm2, [rsp+68h+var_28]
0x1800028a0  movdqa  xmm3, [rsp+68h+var_18]
0x1800028a6  mov     rcx, [rsp+68h+arg_0]
0x1800028ab  mov     rdx, [rsp+68h+arg_8]
0x1800028b0  mov     r8, [rsp+68h+arg_10]
0x1800028b8  mov     r9, [rsp+68h+arg_18]
0x1800028c0  add     rsp, 68h
0x1800028c4  jmp     short $+2
0x1800028c6  jmp     rax
```
