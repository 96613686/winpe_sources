# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x18001615c`
- end: `0x1800161d5`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800161db`

## callees

- `0x180014ae0`
- `0x18001615c`

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
0x18001615c  mov     [rsp+arg_0], rcx
0x180016161  mov     [rsp+arg_8], rdx
0x180016166  mov     [rsp+arg_10], r8
0x18001616b  mov     [rsp+arg_18], r9
0x180016170  sub     rsp, 68h
0x180016174  movdqa  [rsp+68h+var_48], xmm0
0x18001617a  movdqa  [rsp+68h+var_38], xmm1
0x180016180  movdqa  [rsp+68h+var_28], xmm2
0x180016186  movdqa  [rsp+68h+var_18], xmm3
0x18001618c  mov     rdx, rax
0x18001618f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180016196  call    __delayLoadHelper2
0x18001619b  movdqa  xmm0, [rsp+68h+var_48]
0x1800161a1  movdqa  xmm1, [rsp+68h+var_38]
0x1800161a7  movdqa  xmm2, [rsp+68h+var_28]
0x1800161ad  movdqa  xmm3, [rsp+68h+var_18]
0x1800161b3  mov     rcx, [rsp+68h+arg_0]
0x1800161b8  mov     rdx, [rsp+68h+arg_8]
0x1800161bd  mov     r8, [rsp+68h+arg_10]
0x1800161c5  mov     r9, [rsp+68h+arg_18]
0x1800161cd  add     rsp, 68h
0x1800161d1  jmp     short $+2
0x1800161d3  jmp     rax
```
