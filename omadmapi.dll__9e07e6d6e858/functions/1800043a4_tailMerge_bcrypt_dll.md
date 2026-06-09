# __tailMerge_bcrypt_dll

- ea: `0x1800043a4`
- end: `0x18000441d`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004423`
- `0x180004435`
- `0x180004447`
- `0x180004459`
- `0x18000446b`
- `0x18000447d`

## callees

- `0x1800043a4`
- `0x1800223d0`

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
0x1800043a4  mov     [rsp+arg_0], rcx
0x1800043a9  mov     [rsp+arg_8], rdx
0x1800043ae  mov     [rsp+arg_10], r8
0x1800043b3  mov     [rsp+arg_18], r9
0x1800043b8  sub     rsp, 68h
0x1800043bc  movdqa  [rsp+68h+var_48], xmm0
0x1800043c2  movdqa  [rsp+68h+var_38], xmm1
0x1800043c8  movdqa  [rsp+68h+var_28], xmm2
0x1800043ce  movdqa  [rsp+68h+var_18], xmm3
0x1800043d4  mov     rdx, rax
0x1800043d7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800043de  call    __delayLoadHelper2
0x1800043e3  movdqa  xmm0, [rsp+68h+var_48]
0x1800043e9  movdqa  xmm1, [rsp+68h+var_38]
0x1800043ef  movdqa  xmm2, [rsp+68h+var_28]
0x1800043f5  movdqa  xmm3, [rsp+68h+var_18]
0x1800043fb  mov     rcx, [rsp+68h+arg_0]
0x180004400  mov     rdx, [rsp+68h+arg_8]
0x180004405  mov     r8, [rsp+68h+arg_10]
0x18000440d  mov     r9, [rsp+68h+arg_18]
0x180004415  add     rsp, 68h
0x180004419  jmp     short $+2
0x18000441b  jmp     rax
```
