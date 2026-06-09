# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x1800156fb`
- end: `0x180015774`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001577a`
- `0x18001578c`
- `0x1800157b0`
- `0x18001584d`
- `0x18001590e`

## callees

- `0x180014230`
- `0x1800156fb`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800156fb  mov     [rsp+arg_0], rcx
0x180015700  mov     [rsp+arg_8], rdx
0x180015705  mov     [rsp+arg_10], r8
0x18001570a  mov     [rsp+arg_18], r9
0x18001570f  sub     rsp, 68h
0x180015713  movdqa  [rsp+68h+var_48], xmm0
0x180015719  movdqa  [rsp+68h+var_38], xmm1
0x18001571f  movdqa  [rsp+68h+var_28], xmm2
0x180015725  movdqa  [rsp+68h+var_18], xmm3
0x18001572b  mov     rdx, rax
0x18001572e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x180015735  call    __delayLoadHelper2
0x18001573a  movdqa  xmm0, [rsp+68h+var_48]
0x180015740  movdqa  xmm1, [rsp+68h+var_38]
0x180015746  movdqa  xmm2, [rsp+68h+var_28]
0x18001574c  movdqa  xmm3, [rsp+68h+var_18]
0x180015752  mov     rcx, [rsp+68h+arg_0]
0x180015757  mov     rdx, [rsp+68h+arg_8]
0x18001575c  mov     r8, [rsp+68h+arg_10]
0x180015764  mov     r9, [rsp+68h+arg_18]
0x18001576c  add     rsp, 68h
0x180015770  jmp     short $+2
0x180015772  jmp     rax
```
