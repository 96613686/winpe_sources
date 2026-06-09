# __tailMerge_api_ms_win_service_management_l2_1_0_dll

- ea: `0x18000acfd`
- end: `0x18000ad76`
- name: `__tailMerge_api_ms_win_service_management_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000ad7c`

## callees

- `0x180001530`
- `0x18000acfd`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000acfd  mov     [rsp+arg_0], rcx
0x18000ad02  mov     [rsp+arg_8], rdx
0x18000ad07  mov     [rsp+arg_10], r8
0x18000ad0c  mov     [rsp+arg_18], r9
0x18000ad11  sub     rsp, 68h
0x18000ad15  movdqa  [rsp+68h+var_48], xmm0
0x18000ad1b  movdqa  [rsp+68h+var_38], xmm1
0x18000ad21  movdqa  [rsp+68h+var_28], xmm2
0x18000ad27  movdqa  [rsp+68h+var_18], xmm3
0x18000ad2d  mov     rdx, rax
0x18000ad30  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll
0x18000ad37  call    __delayLoadHelper2
0x18000ad3c  movdqa  xmm0, [rsp+68h+var_48]
0x18000ad42  movdqa  xmm1, [rsp+68h+var_38]
0x18000ad48  movdqa  xmm2, [rsp+68h+var_28]
0x18000ad4e  movdqa  xmm3, [rsp+68h+var_18]
0x18000ad54  mov     rcx, [rsp+68h+arg_0]
0x18000ad59  mov     rdx, [rsp+68h+arg_8]
0x18000ad5e  mov     r8, [rsp+68h+arg_10]
0x18000ad66  mov     r9, [rsp+68h+arg_18]
0x18000ad6e  add     rsp, 68h
0x18000ad72  jmp     short $+2
0x18000ad74  jmp     rax
```
