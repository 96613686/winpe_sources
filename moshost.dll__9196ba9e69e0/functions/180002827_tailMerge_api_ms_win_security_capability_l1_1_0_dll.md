# __tailMerge_api_ms_win_security_capability_l1_1_0_dll

- ea: `0x180002827`
- end: `0x1800028a0`
- name: `__tailMerge_api_ms_win_security_capability_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800028a6`

## callees

- `0x180002827`
- `0x18000c580`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_capability_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_capability_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002827  mov     [rsp+arg_0], rcx
0x18000282c  mov     [rsp+arg_8], rdx
0x180002831  mov     [rsp+arg_10], r8
0x180002836  mov     [rsp+arg_18], r9
0x18000283b  sub     rsp, 68h
0x18000283f  movdqa  [rsp+68h+var_48], xmm0
0x180002845  movdqa  [rsp+68h+var_38], xmm1
0x18000284b  movdqa  [rsp+68h+var_28], xmm2
0x180002851  movdqa  [rsp+68h+var_18], xmm3
0x180002857  mov     rdx, rax
0x18000285a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_capability_l1_1_0_dll
0x180002861  call    __delayLoadHelper2
0x180002866  movdqa  xmm0, [rsp+68h+var_48]
0x18000286c  movdqa  xmm1, [rsp+68h+var_38]
0x180002872  movdqa  xmm2, [rsp+68h+var_28]
0x180002878  movdqa  xmm3, [rsp+68h+var_18]
0x18000287e  mov     rcx, [rsp+68h+arg_0]
0x180002883  mov     rdx, [rsp+68h+arg_8]
0x180002888  mov     r8, [rsp+68h+arg_10]
0x180002890  mov     r9, [rsp+68h+arg_18]
0x180002898  add     rsp, 68h
0x18000289c  jmp     short $+2
0x18000289e  jmp     rax
```
