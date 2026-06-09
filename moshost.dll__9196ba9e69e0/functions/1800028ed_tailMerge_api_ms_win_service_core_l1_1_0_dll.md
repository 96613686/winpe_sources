# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x1800028ed`
- end: `0x180002966`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000296c`
- `0x18000297e`

## callees

- `0x1800028ed`
- `0x18000c580`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028ed  mov     [rsp+arg_0], rcx
0x1800028f2  mov     [rsp+arg_8], rdx
0x1800028f7  mov     [rsp+arg_10], r8
0x1800028fc  mov     [rsp+arg_18], r9
0x180002901  sub     rsp, 68h
0x180002905  movdqa  [rsp+68h+var_48], xmm0
0x18000290b  movdqa  [rsp+68h+var_38], xmm1
0x180002911  movdqa  [rsp+68h+var_28], xmm2
0x180002917  movdqa  [rsp+68h+var_18], xmm3
0x18000291d  mov     rdx, rax
0x180002920  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x180002927  call    __delayLoadHelper2
0x18000292c  movdqa  xmm0, [rsp+68h+var_48]
0x180002932  movdqa  xmm1, [rsp+68h+var_38]
0x180002938  movdqa  xmm2, [rsp+68h+var_28]
0x18000293e  movdqa  xmm3, [rsp+68h+var_18]
0x180002944  mov     rcx, [rsp+68h+arg_0]
0x180002949  mov     rdx, [rsp+68h+arg_8]
0x18000294e  mov     r8, [rsp+68h+arg_10]
0x180002956  mov     r9, [rsp+68h+arg_18]
0x18000295e  add     rsp, 68h
0x180002962  jmp     short $+2
0x180002964  jmp     rax
```
