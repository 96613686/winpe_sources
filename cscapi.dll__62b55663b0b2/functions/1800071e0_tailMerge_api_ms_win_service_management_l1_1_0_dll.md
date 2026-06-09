# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x1800071e0`
- end: `0x180007259`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000725f`
- `0x180007271`
- `0x180007283`
- `0x180007295`

## callees

- `0x180006080`
- `0x1800071e0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800071e0  mov     [rsp+arg_0], rcx
0x1800071e5  mov     [rsp+arg_8], rdx
0x1800071ea  mov     [rsp+arg_10], r8
0x1800071ef  mov     [rsp+arg_18], r9
0x1800071f4  sub     rsp, 68h
0x1800071f8  movdqa  [rsp+68h+var_48], xmm0
0x1800071fe  movdqa  [rsp+68h+var_38], xmm1
0x180007204  movdqa  [rsp+68h+var_28], xmm2
0x18000720a  movdqa  [rsp+68h+var_18], xmm3
0x180007210  mov     rdx, rax
0x180007213  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x18000721a  call    __delayLoadHelper2
0x18000721f  movdqa  xmm0, [rsp+68h+var_48]
0x180007225  movdqa  xmm1, [rsp+68h+var_38]
0x18000722b  movdqa  xmm2, [rsp+68h+var_28]
0x180007231  movdqa  xmm3, [rsp+68h+var_18]
0x180007237  mov     rcx, [rsp+68h+arg_0]
0x18000723c  mov     rdx, [rsp+68h+arg_8]
0x180007241  mov     r8, [rsp+68h+arg_10]
0x180007249  mov     r9, [rsp+68h+arg_18]
0x180007251  add     rsp, 68h
0x180007255  jmp     short $+2
0x180007257  jmp     rax
```
