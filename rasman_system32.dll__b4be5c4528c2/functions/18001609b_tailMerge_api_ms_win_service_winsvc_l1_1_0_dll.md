# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x18001609b`
- end: `0x180016114`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001611a`
- `0x18001612c`
- `0x180016150`
- `0x1800161ed`
- `0x1800162ae`

## callees

- `0x180014ae0`
- `0x18001609b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001609b  mov     [rsp+arg_0], rcx
0x1800160a0  mov     [rsp+arg_8], rdx
0x1800160a5  mov     [rsp+arg_10], r8
0x1800160aa  mov     [rsp+arg_18], r9
0x1800160af  sub     rsp, 68h
0x1800160b3  movdqa  [rsp+68h+var_48], xmm0
0x1800160b9  movdqa  [rsp+68h+var_38], xmm1
0x1800160bf  movdqa  [rsp+68h+var_28], xmm2
0x1800160c5  movdqa  [rsp+68h+var_18], xmm3
0x1800160cb  mov     rdx, rax
0x1800160ce  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x1800160d5  call    __delayLoadHelper2
0x1800160da  movdqa  xmm0, [rsp+68h+var_48]
0x1800160e0  movdqa  xmm1, [rsp+68h+var_38]
0x1800160e6  movdqa  xmm2, [rsp+68h+var_28]
0x1800160ec  movdqa  xmm3, [rsp+68h+var_18]
0x1800160f2  mov     rcx, [rsp+68h+arg_0]
0x1800160f7  mov     rdx, [rsp+68h+arg_8]
0x1800160fc  mov     r8, [rsp+68h+arg_10]
0x180016104  mov     r9, [rsp+68h+arg_18]
0x18001610c  add     rsp, 68h
0x180016110  jmp     short $+2
0x180016112  jmp     rax
```
