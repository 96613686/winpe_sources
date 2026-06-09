# __tailMerge_bcrypt_dll

- ea: `0x180002290`
- end: `0x180002309`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000230f`
- `0x180002321`
- `0x18000235c`
- `0x18000236e`
- `0x180002380`
- `0x180002392`

## callees

- `0x180002290`
- `0x180008790`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002290  mov     [rsp+arg_0], rcx
0x180002295  mov     [rsp+arg_8], rdx
0x18000229a  mov     [rsp+arg_10], r8
0x18000229f  mov     [rsp+arg_18], r9
0x1800022a4  sub     rsp, 68h
0x1800022a8  movdqa  [rsp+68h+var_48], xmm0
0x1800022ae  movdqa  [rsp+68h+var_38], xmm1
0x1800022b4  movdqa  [rsp+68h+var_28], xmm2
0x1800022ba  movdqa  [rsp+68h+var_18], xmm3
0x1800022c0  mov     rdx, rax
0x1800022c3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800022ca  call    __delayLoadHelper2
0x1800022cf  movdqa  xmm0, [rsp+68h+var_48]
0x1800022d5  movdqa  xmm1, [rsp+68h+var_38]
0x1800022db  movdqa  xmm2, [rsp+68h+var_28]
0x1800022e1  movdqa  xmm3, [rsp+68h+var_18]
0x1800022e7  mov     rcx, [rsp+68h+arg_0]
0x1800022ec  mov     rdx, [rsp+68h+arg_8]
0x1800022f1  mov     r8, [rsp+68h+arg_10]
0x1800022f9  mov     r9, [rsp+68h+arg_18]
0x180002301  add     rsp, 68h
0x180002305  jmp     short $+2
0x180002307  jmp     rax
```
