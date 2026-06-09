# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x1800157bc`
- end: `0x180015835`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001583b`

## callees

- `0x180014230`
- `0x1800157bc`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800157bc  mov     [rsp+arg_0], rcx
0x1800157c1  mov     [rsp+arg_8], rdx
0x1800157c6  mov     [rsp+arg_10], r8
0x1800157cb  mov     [rsp+arg_18], r9
0x1800157d0  sub     rsp, 68h
0x1800157d4  movdqa  [rsp+68h+var_48], xmm0
0x1800157da  movdqa  [rsp+68h+var_38], xmm1
0x1800157e0  movdqa  [rsp+68h+var_28], xmm2
0x1800157e6  movdqa  [rsp+68h+var_18], xmm3
0x1800157ec  mov     rdx, rax
0x1800157ef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x1800157f6  call    __delayLoadHelper2
0x1800157fb  movdqa  xmm0, [rsp+68h+var_48]
0x180015801  movdqa  xmm1, [rsp+68h+var_38]
0x180015807  movdqa  xmm2, [rsp+68h+var_28]
0x18001580d  movdqa  xmm3, [rsp+68h+var_18]
0x180015813  mov     rcx, [rsp+68h+arg_0]
0x180015818  mov     rdx, [rsp+68h+arg_8]
0x18001581d  mov     r8, [rsp+68h+arg_10]
0x180015825  mov     r9, [rsp+68h+arg_18]
0x18001582d  add     rsp, 68h
0x180015831  jmp     short $+2
0x180015833  jmp     rax
```
