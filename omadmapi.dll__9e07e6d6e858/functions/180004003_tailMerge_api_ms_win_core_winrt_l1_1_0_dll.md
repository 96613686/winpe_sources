# __tailMerge_api_ms_win_core_winrt_l1_1_0_dll

- ea: `0x180004003`
- end: `0x18000407c`
- name: `__tailMerge_api_ms_win_core_winrt_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004082`

## callees

- `0x180004003`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004003  mov     [rsp+arg_0], rcx
0x180004008  mov     [rsp+arg_8], rdx
0x18000400d  mov     [rsp+arg_10], r8
0x180004012  mov     [rsp+arg_18], r9
0x180004017  sub     rsp, 68h
0x18000401b  movdqa  [rsp+68h+var_48], xmm0
0x180004021  movdqa  [rsp+68h+var_38], xmm1
0x180004027  movdqa  [rsp+68h+var_28], xmm2
0x18000402d  movdqa  [rsp+68h+var_18], xmm3
0x180004033  mov     rdx, rax
0x180004036  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll
0x18000403d  call    __delayLoadHelper2
0x180004042  movdqa  xmm0, [rsp+68h+var_48]
0x180004048  movdqa  xmm1, [rsp+68h+var_38]
0x18000404e  movdqa  xmm2, [rsp+68h+var_28]
0x180004054  movdqa  xmm3, [rsp+68h+var_18]
0x18000405a  mov     rcx, [rsp+68h+arg_0]
0x18000405f  mov     rdx, [rsp+68h+arg_8]
0x180004064  mov     r8, [rsp+68h+arg_10]
0x18000406c  mov     r9, [rsp+68h+arg_18]
0x180004074  add     rsp, 68h
0x180004078  jmp     short $+2
0x18000407a  jmp     rax
```
