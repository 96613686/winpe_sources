# __tailMerge_dmpushproxy_dll

- ea: `0x1800048e3`
- end: `0x18000495c`
- name: `__tailMerge_dmpushproxy_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004962`

## callees

- `0x1800048e3`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmpushproxy_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_dmpushproxy_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800048e3  mov     [rsp+arg_0], rcx
0x1800048e8  mov     [rsp+arg_8], rdx
0x1800048ed  mov     [rsp+arg_10], r8
0x1800048f2  mov     [rsp+arg_18], r9
0x1800048f7  sub     rsp, 68h
0x1800048fb  movdqa  [rsp+68h+var_48], xmm0
0x180004901  movdqa  [rsp+68h+var_38], xmm1
0x180004907  movdqa  [rsp+68h+var_28], xmm2
0x18000490d  movdqa  [rsp+68h+var_18], xmm3
0x180004913  mov     rdx, rax
0x180004916  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmpushproxy_dll
0x18000491d  call    __delayLoadHelper2
0x180004922  movdqa  xmm0, [rsp+68h+var_48]
0x180004928  movdqa  xmm1, [rsp+68h+var_38]
0x18000492e  movdqa  xmm2, [rsp+68h+var_28]
0x180004934  movdqa  xmm3, [rsp+68h+var_18]
0x18000493a  mov     rcx, [rsp+68h+arg_0]
0x18000493f  mov     rdx, [rsp+68h+arg_8]
0x180004944  mov     r8, [rsp+68h+arg_10]
0x18000494c  mov     r9, [rsp+68h+arg_18]
0x180004954  add     rsp, 68h
0x180004958  jmp     short $+2
0x18000495a  jmp     rax
```
