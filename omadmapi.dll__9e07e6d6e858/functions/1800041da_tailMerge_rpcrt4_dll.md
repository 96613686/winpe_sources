# __tailMerge_rpcrt4_dll

- ea: `0x1800041da`
- end: `0x180004253`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004259`
- `0x180004dee`

## callees

- `0x1800041da`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800041da  mov     [rsp+arg_0], rcx
0x1800041df  mov     [rsp+arg_8], rdx
0x1800041e4  mov     [rsp+arg_10], r8
0x1800041e9  mov     [rsp+arg_18], r9
0x1800041ee  sub     rsp, 68h
0x1800041f2  movdqa  [rsp+68h+var_48], xmm0
0x1800041f8  movdqa  [rsp+68h+var_38], xmm1
0x1800041fe  movdqa  [rsp+68h+var_28], xmm2
0x180004204  movdqa  [rsp+68h+var_18], xmm3
0x18000420a  mov     rdx, rax
0x18000420d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180004214  call    __delayLoadHelper2
0x180004219  movdqa  xmm0, [rsp+68h+var_48]
0x18000421f  movdqa  xmm1, [rsp+68h+var_38]
0x180004225  movdqa  xmm2, [rsp+68h+var_28]
0x18000422b  movdqa  xmm3, [rsp+68h+var_18]
0x180004231  mov     rcx, [rsp+68h+arg_0]
0x180004236  mov     rdx, [rsp+68h+arg_8]
0x18000423b  mov     r8, [rsp+68h+arg_10]
0x180004243  mov     r9, [rsp+68h+arg_18]
0x18000424b  add     rsp, 68h
0x18000424f  jmp     short $+2
0x180004251  jmp     rax
```
