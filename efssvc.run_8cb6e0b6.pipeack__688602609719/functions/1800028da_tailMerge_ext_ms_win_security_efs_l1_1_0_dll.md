# __tailMerge_ext_ms_win_security_efs_l1_1_0_dll

- ea: `0x1800028da`
- end: `0x180002953`
- name: `__tailMerge_ext_ms_win_security_efs_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002959`

## callees

- `0x1800028da`
- `0x180008790`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_efs_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_efs_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028da  mov     [rsp+arg_0], rcx
0x1800028df  mov     [rsp+arg_8], rdx
0x1800028e4  mov     [rsp+arg_10], r8
0x1800028e9  mov     [rsp+arg_18], r9
0x1800028ee  sub     rsp, 68h
0x1800028f2  movdqa  [rsp+68h+var_48], xmm0
0x1800028f8  movdqa  [rsp+68h+var_38], xmm1
0x1800028fe  movdqa  [rsp+68h+var_28], xmm2
0x180002904  movdqa  [rsp+68h+var_18], xmm3
0x18000290a  mov     rdx, rax
0x18000290d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_efs_l1_1_0_dll
0x180002914  call    __delayLoadHelper2
0x180002919  movdqa  xmm0, [rsp+68h+var_48]
0x18000291f  movdqa  xmm1, [rsp+68h+var_38]
0x180002925  movdqa  xmm2, [rsp+68h+var_28]
0x18000292b  movdqa  xmm3, [rsp+68h+var_18]
0x180002931  mov     rcx, [rsp+68h+arg_0]
0x180002936  mov     rdx, [rsp+68h+arg_8]
0x18000293b  mov     r8, [rsp+68h+arg_10]
0x180002943  mov     r9, [rsp+68h+arg_18]
0x18000294b  add     rsp, 68h
0x18000294f  jmp     short $+2
0x180002951  jmp     rax
```
