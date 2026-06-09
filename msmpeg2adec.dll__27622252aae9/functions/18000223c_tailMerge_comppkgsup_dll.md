# __tailMerge_comppkgsup_dll

- ea: `0x18000223c`
- end: `0x1800022b5`
- name: `__tailMerge_comppkgsup_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022bb`

## callees

- `0x18000223c`
- `0x1800734c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_comppkgsup_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_comppkgsup_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000223c  mov     [rsp+arg_0], rcx
0x180002241  mov     [rsp+arg_8], rdx
0x180002246  mov     [rsp+arg_10], r8
0x18000224b  mov     [rsp+arg_18], r9
0x180002250  sub     rsp, 68h
0x180002254  movdqa  [rsp+68h+var_48], xmm0
0x18000225a  movdqa  [rsp+68h+var_38], xmm1
0x180002260  movdqa  [rsp+68h+var_28], xmm2
0x180002266  movdqa  [rsp+68h+var_18], xmm3
0x18000226c  mov     rdx, rax
0x18000226f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comppkgsup_dll
0x180002276  call    __delayLoadHelper2
0x18000227b  movdqa  xmm0, [rsp+68h+var_48]
0x180002281  movdqa  xmm1, [rsp+68h+var_38]
0x180002287  movdqa  xmm2, [rsp+68h+var_28]
0x18000228d  movdqa  xmm3, [rsp+68h+var_18]
0x180002293  mov     rcx, [rsp+68h+arg_0]
0x180002298  mov     rdx, [rsp+68h+arg_8]
0x18000229d  mov     r8, [rsp+68h+arg_10]
0x1800022a5  mov     r9, [rsp+68h+arg_18]
0x1800022ad  add     rsp, 68h
0x1800022b1  jmp     short $+2
0x1800022b3  jmp     rax
```
