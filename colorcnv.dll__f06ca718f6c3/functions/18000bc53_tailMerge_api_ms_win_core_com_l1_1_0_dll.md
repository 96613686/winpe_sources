# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000bc53`
- end: `0x18000bccc`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bcd2`
- `0x18000bce4`
- `0x18000bcf6`

## callees

- `0x1800089e0`
- `0x18000bc53`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000bc53  mov     [rsp+arg_0], rcx
0x18000bc58  mov     [rsp+arg_8], rdx
0x18000bc5d  mov     [rsp+arg_10], r8
0x18000bc62  mov     [rsp+arg_18], r9
0x18000bc67  sub     rsp, 68h
0x18000bc6b  movdqa  [rsp+68h+var_48], xmm0
0x18000bc71  movdqa  [rsp+68h+var_38], xmm1
0x18000bc77  movdqa  [rsp+68h+var_28], xmm2
0x18000bc7d  movdqa  [rsp+68h+var_18], xmm3
0x18000bc83  mov     rdx, rax
0x18000bc86  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000bc8d  call    __delayLoadHelper2
0x18000bc92  movdqa  xmm0, [rsp+68h+var_48]
0x18000bc98  movdqa  xmm1, [rsp+68h+var_38]
0x18000bc9e  movdqa  xmm2, [rsp+68h+var_28]
0x18000bca4  movdqa  xmm3, [rsp+68h+var_18]
0x18000bcaa  mov     rcx, [rsp+68h+arg_0]
0x18000bcaf  mov     rdx, [rsp+68h+arg_8]
0x18000bcb4  mov     r8, [rsp+68h+arg_10]
0x18000bcbc  mov     r9, [rsp+68h+arg_18]
0x18000bcc4  add     rsp, 68h
0x18000bcc8  jmp     short $+2
0x18000bcca  jmp     rax
```
