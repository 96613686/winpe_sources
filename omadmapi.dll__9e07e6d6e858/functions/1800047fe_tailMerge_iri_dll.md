# __tailMerge_iri_dll

- ea: `0x1800047fe`
- end: `0x180004877`
- name: `__tailMerge_iri_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000487d`
- `0x18000488f`
- `0x1800048a1`
- `0x1800048b3`
- `0x1800048c5`
- `0x1800048d7`

## callees

- `0x1800047fe`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_iri_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_iri_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800047fe  mov     [rsp+arg_0], rcx
0x180004803  mov     [rsp+arg_8], rdx
0x180004808  mov     [rsp+arg_10], r8
0x18000480d  mov     [rsp+arg_18], r9
0x180004812  sub     rsp, 68h
0x180004816  movdqa  [rsp+68h+var_48], xmm0
0x18000481c  movdqa  [rsp+68h+var_38], xmm1
0x180004822  movdqa  [rsp+68h+var_28], xmm2
0x180004828  movdqa  [rsp+68h+var_18], xmm3
0x18000482e  mov     rdx, rax
0x180004831  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iri_dll
0x180004838  call    __delayLoadHelper2
0x18000483d  movdqa  xmm0, [rsp+68h+var_48]
0x180004843  movdqa  xmm1, [rsp+68h+var_38]
0x180004849  movdqa  xmm2, [rsp+68h+var_28]
0x18000484f  movdqa  xmm3, [rsp+68h+var_18]
0x180004855  mov     rcx, [rsp+68h+arg_0]
0x18000485a  mov     rdx, [rsp+68h+arg_8]
0x18000485f  mov     r8, [rsp+68h+arg_10]
0x180004867  mov     r9, [rsp+68h+arg_18]
0x18000486f  add     rsp, 68h
0x180004873  jmp     short $+2
0x180004875  jmp     rax
```
