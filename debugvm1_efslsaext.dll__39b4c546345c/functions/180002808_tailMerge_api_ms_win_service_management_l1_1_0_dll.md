# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180002808`
- end: `0x180002881`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002887`
- `0x180002899`
- `0x1800028ab`
- `0x1800028bd`

## callees

- `0x180002808`
- `0x180007f20`

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
0x180002808  mov     [rsp+arg_0], rcx
0x18000280d  mov     [rsp+arg_8], rdx
0x180002812  mov     [rsp+arg_10], r8
0x180002817  mov     [rsp+arg_18], r9
0x18000281c  sub     rsp, 68h
0x180002820  movdqa  [rsp+68h+var_48], xmm0
0x180002826  movdqa  [rsp+68h+var_38], xmm1
0x18000282c  movdqa  [rsp+68h+var_28], xmm2
0x180002832  movdqa  [rsp+68h+var_18], xmm3
0x180002838  mov     rdx, rax
0x18000283b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180002842  call    __delayLoadHelper2
0x180002847  movdqa  xmm0, [rsp+68h+var_48]
0x18000284d  movdqa  xmm1, [rsp+68h+var_38]
0x180002853  movdqa  xmm2, [rsp+68h+var_28]
0x180002859  movdqa  xmm3, [rsp+68h+var_18]
0x18000285f  mov     rcx, [rsp+68h+arg_0]
0x180002864  mov     rdx, [rsp+68h+arg_8]
0x180002869  mov     r8, [rsp+68h+arg_10]
0x180002871  mov     r9, [rsp+68h+arg_18]
0x180002879  add     rsp, 68h
0x18000287d  jmp     short $+2
0x18000287f  jmp     rax
```
