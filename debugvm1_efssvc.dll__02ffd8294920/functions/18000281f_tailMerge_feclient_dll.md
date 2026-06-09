# __tailMerge_feclient_dll

- ea: `0x18000281f`
- end: `0x180002898`
- name: `__tailMerge_feclient_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000289e`

## callees

- `0x18000281f`
- `0x180007e40`

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
0x18000281f  mov     [rsp+arg_0], rcx
0x180002824  mov     [rsp+arg_8], rdx
0x180002829  mov     [rsp+arg_10], r8
0x18000282e  mov     [rsp+arg_18], r9
0x180002833  sub     rsp, 68h
0x180002837  movdqa  [rsp+68h+var_48], xmm0
0x18000283d  movdqa  [rsp+68h+var_38], xmm1
0x180002843  movdqa  [rsp+68h+var_28], xmm2
0x180002849  movdqa  [rsp+68h+var_18], xmm3
0x18000284f  mov     rdx, rax
0x180002852  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_feclient_dll
0x180002859  call    __delayLoadHelper2
0x18000285e  movdqa  xmm0, [rsp+68h+var_48]
0x180002864  movdqa  xmm1, [rsp+68h+var_38]
0x18000286a  movdqa  xmm2, [rsp+68h+var_28]
0x180002870  movdqa  xmm3, [rsp+68h+var_18]
0x180002876  mov     rcx, [rsp+68h+arg_0]
0x18000287b  mov     rdx, [rsp+68h+arg_8]
0x180002880  mov     r8, [rsp+68h+arg_10]
0x180002888  mov     r9, [rsp+68h+arg_18]
0x180002890  add     rsp, 68h
0x180002894  jmp     short $+2
0x180002896  jmp     rax
```
