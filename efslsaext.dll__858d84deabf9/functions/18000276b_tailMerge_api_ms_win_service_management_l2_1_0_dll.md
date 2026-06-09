# __tailMerge_api_ms_win_service_management_l2_1_0_dll

- ea: `0x18000276b`
- end: `0x1800027e4`
- name: `__tailMerge_api_ms_win_service_management_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800027ea`
- `0x1800027fc`

## callees

- `0x18000276b`
- `0x180007f20`

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
0x18000276b  mov     [rsp+arg_0], rcx
0x180002770  mov     [rsp+arg_8], rdx
0x180002775  mov     [rsp+arg_10], r8
0x18000277a  mov     [rsp+arg_18], r9
0x18000277f  sub     rsp, 68h
0x180002783  movdqa  [rsp+68h+var_48], xmm0
0x180002789  movdqa  [rsp+68h+var_38], xmm1
0x18000278f  movdqa  [rsp+68h+var_28], xmm2
0x180002795  movdqa  [rsp+68h+var_18], xmm3
0x18000279b  mov     rdx, rax
0x18000279e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll
0x1800027a5  call    __delayLoadHelper2
0x1800027aa  movdqa  xmm0, [rsp+68h+var_48]
0x1800027b0  movdqa  xmm1, [rsp+68h+var_38]
0x1800027b6  movdqa  xmm2, [rsp+68h+var_28]
0x1800027bc  movdqa  xmm3, [rsp+68h+var_18]
0x1800027c2  mov     rcx, [rsp+68h+arg_0]
0x1800027c7  mov     rdx, [rsp+68h+arg_8]
0x1800027cc  mov     r8, [rsp+68h+arg_10]
0x1800027d4  mov     r9, [rsp+68h+arg_18]
0x1800027dc  add     rsp, 68h
0x1800027e0  jmp     short $+2
0x1800027e2  jmp     rax
```
