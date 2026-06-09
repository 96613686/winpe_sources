# __tailMerge_api_ms_win_service_management_l2_1_0_dll

- ea: `0x1800072a1`
- end: `0x18000731a`
- name: `__tailMerge_api_ms_win_service_management_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180007320`
- `0x180007332`
- `0x180007344`

## callees

- `0x180006080`
- `0x1800072a1`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800072a1  mov     [rsp+arg_0], rcx
0x1800072a6  mov     [rsp+arg_8], rdx
0x1800072ab  mov     [rsp+arg_10], r8
0x1800072b0  mov     [rsp+arg_18], r9
0x1800072b5  sub     rsp, 68h
0x1800072b9  movdqa  [rsp+68h+var_48], xmm0
0x1800072bf  movdqa  [rsp+68h+var_38], xmm1
0x1800072c5  movdqa  [rsp+68h+var_28], xmm2
0x1800072cb  movdqa  [rsp+68h+var_18], xmm3
0x1800072d1  mov     rdx, rax
0x1800072d4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll
0x1800072db  call    __delayLoadHelper2
0x1800072e0  movdqa  xmm0, [rsp+68h+var_48]
0x1800072e6  movdqa  xmm1, [rsp+68h+var_38]
0x1800072ec  movdqa  xmm2, [rsp+68h+var_28]
0x1800072f2  movdqa  xmm3, [rsp+68h+var_18]
0x1800072f8  mov     rcx, [rsp+68h+arg_0]
0x1800072fd  mov     rdx, [rsp+68h+arg_8]
0x180007302  mov     r8, [rsp+68h+arg_10]
0x18000730a  mov     r9, [rsp+68h+arg_18]
0x180007312  add     rsp, 68h
0x180007316  jmp     short $+2
0x180007318  jmp     rax
```
