# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x180020c4e`
- end: `0x180020cc7`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020ccd`

## callees

- `0x180018b30`
- `0x180020c4e`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180020c4e  mov     [rsp+arg_0], rcx
0x180020c53  mov     [rsp+arg_8], rdx
0x180020c58  mov     [rsp+arg_10], r8
0x180020c5d  mov     [rsp+arg_18], r9
0x180020c62  sub     rsp, 68h
0x180020c66  movdqa  [rsp+68h+var_48], xmm0
0x180020c6c  movdqa  [rsp+68h+var_38], xmm1
0x180020c72  movdqa  [rsp+68h+var_28], xmm2
0x180020c78  movdqa  [rsp+68h+var_18], xmm3
0x180020c7e  mov     rdx, rax
0x180020c81  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x180020c88  call    __delayLoadHelper2
0x180020c8d  movdqa  xmm0, [rsp+68h+var_48]
0x180020c93  movdqa  xmm1, [rsp+68h+var_38]
0x180020c99  movdqa  xmm2, [rsp+68h+var_28]
0x180020c9f  movdqa  xmm3, [rsp+68h+var_18]
0x180020ca5  mov     rcx, [rsp+68h+arg_0]
0x180020caa  mov     rdx, [rsp+68h+arg_8]
0x180020caf  mov     r8, [rsp+68h+arg_10]
0x180020cb7  mov     r9, [rsp+68h+arg_18]
0x180020cbf  add     rsp, 68h
0x180020cc3  jmp     short $+2
0x180020cc5  jmp     rax
```
