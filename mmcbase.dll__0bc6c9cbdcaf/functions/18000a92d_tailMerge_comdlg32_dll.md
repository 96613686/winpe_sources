# __tailMerge_comdlg32_dll

- ea: `0x18000a92d`
- end: `0x18000a9a6`
- name: `__tailMerge_comdlg32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a9ac`

## callees

- `0x180006bb0`
- `0x18000a92d`

## pseudocode

```c
__int64 __fastcall _tailMerge_comdlg32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_comdlg32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a92d  mov     [rsp+arg_0], rcx
0x18000a932  mov     [rsp+arg_8], rdx
0x18000a937  mov     [rsp+arg_10], r8
0x18000a93c  mov     [rsp+arg_18], r9
0x18000a941  sub     rsp, 68h
0x18000a945  movdqa  [rsp+68h+var_48], xmm0
0x18000a94b  movdqa  [rsp+68h+var_38], xmm1
0x18000a951  movdqa  [rsp+68h+var_28], xmm2
0x18000a957  movdqa  [rsp+68h+var_18], xmm3
0x18000a95d  mov     rdx, rax
0x18000a960  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comdlg32_dll
0x18000a967  call    __delayLoadHelper2
0x18000a96c  movdqa  xmm0, [rsp+68h+var_48]
0x18000a972  movdqa  xmm1, [rsp+68h+var_38]
0x18000a978  movdqa  xmm2, [rsp+68h+var_28]
0x18000a97e  movdqa  xmm3, [rsp+68h+var_18]
0x18000a984  mov     rcx, [rsp+68h+arg_0]
0x18000a989  mov     rdx, [rsp+68h+arg_8]
0x18000a98e  mov     r8, [rsp+68h+arg_10]
0x18000a996  mov     r9, [rsp+68h+arg_18]
0x18000a99e  add     rsp, 68h
0x18000a9a2  jmp     short $+2
0x18000a9a4  jmp     rax
```
