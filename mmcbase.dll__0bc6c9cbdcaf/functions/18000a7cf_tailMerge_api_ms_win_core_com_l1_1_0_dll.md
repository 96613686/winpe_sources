# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000a7cf`
- end: `0x18000a848`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a84e`
- `0x18000a860`
- `0x18000a872`
- `0x18000a884`

## callees

- `0x180006bb0`
- `0x18000a7cf`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a7cf  mov     [rsp+arg_0], rcx
0x18000a7d4  mov     [rsp+arg_8], rdx
0x18000a7d9  mov     [rsp+arg_10], r8
0x18000a7de  mov     [rsp+arg_18], r9
0x18000a7e3  sub     rsp, 68h
0x18000a7e7  movdqa  [rsp+68h+var_48], xmm0
0x18000a7ed  movdqa  [rsp+68h+var_38], xmm1
0x18000a7f3  movdqa  [rsp+68h+var_28], xmm2
0x18000a7f9  movdqa  [rsp+68h+var_18], xmm3
0x18000a7ff  mov     rdx, rax
0x18000a802  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000a809  call    __delayLoadHelper2
0x18000a80e  movdqa  xmm0, [rsp+68h+var_48]
0x18000a814  movdqa  xmm1, [rsp+68h+var_38]
0x18000a81a  movdqa  xmm2, [rsp+68h+var_28]
0x18000a820  movdqa  xmm3, [rsp+68h+var_18]
0x18000a826  mov     rcx, [rsp+68h+arg_0]
0x18000a82b  mov     rdx, [rsp+68h+arg_8]
0x18000a830  mov     r8, [rsp+68h+arg_10]
0x18000a838  mov     r9, [rsp+68h+arg_18]
0x18000a840  add     rsp, 68h
0x18000a844  jmp     short $+2
0x18000a846  jmp     rax
```
