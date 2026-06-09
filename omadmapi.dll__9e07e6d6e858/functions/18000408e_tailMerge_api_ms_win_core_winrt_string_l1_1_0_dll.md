# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x18000408e`
- end: `0x180004107`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000410d`
- `0x18000411f`
- `0x180004131`

## callees

- `0x18000408e`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000408e  mov     [rsp+arg_0], rcx
0x180004093  mov     [rsp+arg_8], rdx
0x180004098  mov     [rsp+arg_10], r8
0x18000409d  mov     [rsp+arg_18], r9
0x1800040a2  sub     rsp, 68h
0x1800040a6  movdqa  [rsp+68h+var_48], xmm0
0x1800040ac  movdqa  [rsp+68h+var_38], xmm1
0x1800040b2  movdqa  [rsp+68h+var_28], xmm2
0x1800040b8  movdqa  [rsp+68h+var_18], xmm3
0x1800040be  mov     rdx, rax
0x1800040c1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x1800040c8  call    __delayLoadHelper2
0x1800040cd  movdqa  xmm0, [rsp+68h+var_48]
0x1800040d3  movdqa  xmm1, [rsp+68h+var_38]
0x1800040d9  movdqa  xmm2, [rsp+68h+var_28]
0x1800040df  movdqa  xmm3, [rsp+68h+var_18]
0x1800040e5  mov     rcx, [rsp+68h+arg_0]
0x1800040ea  mov     rdx, [rsp+68h+arg_8]
0x1800040ef  mov     r8, [rsp+68h+arg_10]
0x1800040f7  mov     r9, [rsp+68h+arg_18]
0x1800040ff  add     rsp, 68h
0x180004103  jmp     short $+2
0x180004105  jmp     rax
```
