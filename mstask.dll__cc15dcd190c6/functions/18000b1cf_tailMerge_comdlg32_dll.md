# __tailMerge_comdlg32_dll

- ea: `0x18000b1cf`
- end: `0x18000b248`
- name: `__tailMerge_comdlg32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b24e`

## callees

- `0x180009170`
- `0x18000b1cf`

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
0x18000b1cf  mov     [rsp+arg_0], rcx
0x18000b1d4  mov     [rsp+arg_8], rdx
0x18000b1d9  mov     [rsp+arg_10], r8
0x18000b1de  mov     [rsp+arg_18], r9
0x18000b1e3  sub     rsp, 68h
0x18000b1e7  movdqa  [rsp+68h+var_48], xmm0
0x18000b1ed  movdqa  [rsp+68h+var_38], xmm1
0x18000b1f3  movdqa  [rsp+68h+var_28], xmm2
0x18000b1f9  movdqa  [rsp+68h+var_18], xmm3
0x18000b1ff  mov     rdx, rax
0x18000b202  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comdlg32_dll
0x18000b209  call    __delayLoadHelper2
0x18000b20e  movdqa  xmm0, [rsp+68h+var_48]
0x18000b214  movdqa  xmm1, [rsp+68h+var_38]
0x18000b21a  movdqa  xmm2, [rsp+68h+var_28]
0x18000b220  movdqa  xmm3, [rsp+68h+var_18]
0x18000b226  mov     rcx, [rsp+68h+arg_0]
0x18000b22b  mov     rdx, [rsp+68h+arg_8]
0x18000b230  mov     r8, [rsp+68h+arg_10]
0x18000b238  mov     r9, [rsp+68h+arg_18]
0x18000b240  add     rsp, 68h
0x18000b244  jmp     short $+2
0x18000b246  jmp     rax
```
