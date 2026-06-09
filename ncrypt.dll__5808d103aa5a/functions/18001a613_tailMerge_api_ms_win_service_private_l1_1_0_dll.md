# __tailMerge_api_ms_win_service_private_l1_1_0_dll

- ea: `0x18001a613`
- end: `0x18001a68c`
- name: `__tailMerge_api_ms_win_service_private_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001a692`

## callees

- `0x180015c10`
- `0x18001a613`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_private_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a613  mov     [rsp+arg_0], rcx
0x18001a618  mov     [rsp+arg_8], rdx
0x18001a61d  mov     [rsp+arg_10], r8
0x18001a622  mov     [rsp+arg_18], r9
0x18001a627  sub     rsp, 68h
0x18001a62b  movdqa  [rsp+68h+var_48], xmm0
0x18001a631  movdqa  [rsp+68h+var_38], xmm1
0x18001a637  movdqa  [rsp+68h+var_28], xmm2
0x18001a63d  movdqa  [rsp+68h+var_18], xmm3
0x18001a643  mov     rdx, rax
0x18001a646  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_0_dll
0x18001a64d  call    __delayLoadHelper2
0x18001a652  movdqa  xmm0, [rsp+68h+var_48]
0x18001a658  movdqa  xmm1, [rsp+68h+var_38]
0x18001a65e  movdqa  xmm2, [rsp+68h+var_28]
0x18001a664  movdqa  xmm3, [rsp+68h+var_18]
0x18001a66a  mov     rcx, [rsp+68h+arg_0]
0x18001a66f  mov     rdx, [rsp+68h+arg_8]
0x18001a674  mov     r8, [rsp+68h+arg_10]
0x18001a67c  mov     r9, [rsp+68h+arg_18]
0x18001a684  add     rsp, 68h
0x18001a688  jmp     short $+2
0x18001a68a  jmp     rax
```
