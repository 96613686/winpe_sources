# __tailMerge_dcomp_dll

- ea: `0x18000df40`
- end: `0x18000dfb9`
- name: `__tailMerge_dcomp_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dfbf`

## callees

- `0x180009aa0`
- `0x18000df40`

## pseudocode

```c
__int64 __fastcall _tailMerge_dcomp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dcomp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000df40  mov     [rsp+arg_0], rcx
0x18000df45  mov     [rsp+arg_8], rdx
0x18000df4a  mov     [rsp+arg_10], r8
0x18000df4f  mov     [rsp+arg_18], r9
0x18000df54  sub     rsp, 68h
0x18000df58  movdqa  [rsp+68h+var_48], xmm0
0x18000df5e  movdqa  [rsp+68h+var_38], xmm1
0x18000df64  movdqa  [rsp+68h+var_28], xmm2
0x18000df6a  movdqa  [rsp+68h+var_18], xmm3
0x18000df70  mov     rdx, rax
0x18000df73  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dcomp_dll
0x18000df7a  call    __delayLoadHelper2
0x18000df7f  movdqa  xmm0, [rsp+68h+var_48]
0x18000df85  movdqa  xmm1, [rsp+68h+var_38]
0x18000df8b  movdqa  xmm2, [rsp+68h+var_28]
0x18000df91  movdqa  xmm3, [rsp+68h+var_18]
0x18000df97  mov     rcx, [rsp+68h+arg_0]
0x18000df9c  mov     rdx, [rsp+68h+arg_8]
0x18000dfa1  mov     r8, [rsp+68h+arg_10]
0x18000dfa9  mov     r9, [rsp+68h+arg_18]
0x18000dfb1  add     rsp, 68h
0x18000dfb5  jmp     short $+2
0x18000dfb7  jmp     rax
```
