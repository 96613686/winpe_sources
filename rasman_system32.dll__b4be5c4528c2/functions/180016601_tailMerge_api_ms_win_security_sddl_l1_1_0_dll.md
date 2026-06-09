# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180016601`
- end: `0x18001667a`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016680`

## callees

- `0x180014ae0`
- `0x180016601`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180016601  mov     [rsp+arg_0], rcx
0x180016606  mov     [rsp+arg_8], rdx
0x18001660b  mov     [rsp+arg_10], r8
0x180016610  mov     [rsp+arg_18], r9
0x180016615  sub     rsp, 68h
0x180016619  movdqa  [rsp+68h+var_48], xmm0
0x18001661f  movdqa  [rsp+68h+var_38], xmm1
0x180016625  movdqa  [rsp+68h+var_28], xmm2
0x18001662b  movdqa  [rsp+68h+var_18], xmm3
0x180016631  mov     rdx, rax
0x180016634  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18001663b  call    __delayLoadHelper2
0x180016640  movdqa  xmm0, [rsp+68h+var_48]
0x180016646  movdqa  xmm1, [rsp+68h+var_38]
0x18001664c  movdqa  xmm2, [rsp+68h+var_28]
0x180016652  movdqa  xmm3, [rsp+68h+var_18]
0x180016658  mov     rcx, [rsp+68h+arg_0]
0x18001665d  mov     rdx, [rsp+68h+arg_8]
0x180016662  mov     r8, [rsp+68h+arg_10]
0x18001666a  mov     r9, [rsp+68h+arg_18]
0x180016672  add     rsp, 68h
0x180016676  jmp     short $+2
0x180016678  jmp     rax
```
