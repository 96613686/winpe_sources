# __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll

- ea: `0x180005b32`
- end: `0x180005bab`
- name: `__tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005bb1`

## callees

- `0x180004100`
- `0x180005b32`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005b32  mov     [rsp+arg_0], rcx
0x180005b37  mov     [rsp+arg_8], rdx
0x180005b3c  mov     [rsp+arg_10], r8
0x180005b41  mov     [rsp+arg_18], r9
0x180005b46  sub     rsp, 68h
0x180005b4a  movdqa  [rsp+68h+var_48], xmm0
0x180005b50  movdqa  [rsp+68h+var_38], xmm1
0x180005b56  movdqa  [rsp+68h+var_28], xmm2
0x180005b5c  movdqa  [rsp+68h+var_18], xmm3
0x180005b62  mov     rdx, rax
0x180005b65  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll
0x180005b6c  call    __delayLoadHelper2
0x180005b71  movdqa  xmm0, [rsp+68h+var_48]
0x180005b77  movdqa  xmm1, [rsp+68h+var_38]
0x180005b7d  movdqa  xmm2, [rsp+68h+var_28]
0x180005b83  movdqa  xmm3, [rsp+68h+var_18]
0x180005b89  mov     rcx, [rsp+68h+arg_0]
0x180005b8e  mov     rdx, [rsp+68h+arg_8]
0x180005b93  mov     r8, [rsp+68h+arg_10]
0x180005b9b  mov     r9, [rsp+68h+arg_18]
0x180005ba3  add     rsp, 68h
0x180005ba7  jmp     short $+2
0x180005ba9  jmp     rax
```
