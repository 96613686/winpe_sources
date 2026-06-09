# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000a9db`
- end: `0x18000aa54`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aa5a`
- `0x18000ac77`
- `0x18000ac89`

## callees

- `0x180009170`
- `0x18000a9db`

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
0x18000a9db  mov     [rsp+arg_0], rcx
0x18000a9e0  mov     [rsp+arg_8], rdx
0x18000a9e5  mov     [rsp+arg_10], r8
0x18000a9ea  mov     [rsp+arg_18], r9
0x18000a9ef  sub     rsp, 68h
0x18000a9f3  movdqa  [rsp+68h+var_48], xmm0
0x18000a9f9  movdqa  [rsp+68h+var_38], xmm1
0x18000a9ff  movdqa  [rsp+68h+var_28], xmm2
0x18000aa05  movdqa  [rsp+68h+var_18], xmm3
0x18000aa0b  mov     rdx, rax
0x18000aa0e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000aa15  call    __delayLoadHelper2
0x18000aa1a  movdqa  xmm0, [rsp+68h+var_48]
0x18000aa20  movdqa  xmm1, [rsp+68h+var_38]
0x18000aa26  movdqa  xmm2, [rsp+68h+var_28]
0x18000aa2c  movdqa  xmm3, [rsp+68h+var_18]
0x18000aa32  mov     rcx, [rsp+68h+arg_0]
0x18000aa37  mov     rdx, [rsp+68h+arg_8]
0x18000aa3c  mov     r8, [rsp+68h+arg_10]
0x18000aa44  mov     r9, [rsp+68h+arg_18]
0x18000aa4c  add     rsp, 68h
0x18000aa50  jmp     short $+2
0x18000aa52  jmp     rax
```
