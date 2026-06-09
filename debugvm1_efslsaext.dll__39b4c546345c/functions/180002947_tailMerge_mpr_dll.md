# __tailMerge_mpr_dll

- ea: `0x180002947`
- end: `0x1800029c0`
- name: `__tailMerge_mpr_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800029c6`
- `0x1800029d8`

## callees

- `0x180002947`
- `0x180007f20`

## pseudocode

```c
__int64 __fastcall _tailMerge_mpr_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mpr_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002947  mov     [rsp+arg_0], rcx
0x18000294c  mov     [rsp+arg_8], rdx
0x180002951  mov     [rsp+arg_10], r8
0x180002956  mov     [rsp+arg_18], r9
0x18000295b  sub     rsp, 68h
0x18000295f  movdqa  [rsp+68h+var_48], xmm0
0x180002965  movdqa  [rsp+68h+var_38], xmm1
0x18000296b  movdqa  [rsp+68h+var_28], xmm2
0x180002971  movdqa  [rsp+68h+var_18], xmm3
0x180002977  mov     rdx, rax
0x18000297a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mpr_dll
0x180002981  call    __delayLoadHelper2
0x180002986  movdqa  xmm0, [rsp+68h+var_48]
0x18000298c  movdqa  xmm1, [rsp+68h+var_38]
0x180002992  movdqa  xmm2, [rsp+68h+var_28]
0x180002998  movdqa  xmm3, [rsp+68h+var_18]
0x18000299e  mov     rcx, [rsp+68h+arg_0]
0x1800029a3  mov     rdx, [rsp+68h+arg_8]
0x1800029a8  mov     r8, [rsp+68h+arg_10]
0x1800029b0  mov     r9, [rsp+68h+arg_18]
0x1800029b8  add     rsp, 68h
0x1800029bc  jmp     short $+2
0x1800029be  jmp     rax
```
