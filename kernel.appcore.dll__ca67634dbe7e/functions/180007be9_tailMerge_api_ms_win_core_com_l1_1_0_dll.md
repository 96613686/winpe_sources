# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180007be9`
- end: `0x180007c62`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c68`
- `0x180007c8c`

## callees

- `0x180005080`
- `0x180007be9`

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
0x180007be9  mov     [rsp+arg_0], rcx
0x180007bee  mov     [rsp+arg_8], rdx
0x180007bf3  mov     [rsp+arg_10], r8
0x180007bf8  mov     [rsp+arg_18], r9
0x180007bfd  sub     rsp, 68h
0x180007c01  movdqa  [rsp+68h+var_48], xmm0
0x180007c07  movdqa  [rsp+68h+var_38], xmm1
0x180007c0d  movdqa  [rsp+68h+var_28], xmm2
0x180007c13  movdqa  [rsp+68h+var_18], xmm3
0x180007c19  mov     rdx, rax
0x180007c1c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180007c23  call    __delayLoadHelper2
0x180007c28  movdqa  xmm0, [rsp+68h+var_48]
0x180007c2e  movdqa  xmm1, [rsp+68h+var_38]
0x180007c34  movdqa  xmm2, [rsp+68h+var_28]
0x180007c3a  movdqa  xmm3, [rsp+68h+var_18]
0x180007c40  mov     rcx, [rsp+68h+arg_0]
0x180007c45  mov     rdx, [rsp+68h+arg_8]
0x180007c4a  mov     r8, [rsp+68h+arg_10]
0x180007c52  mov     r9, [rsp+68h+arg_18]
0x180007c5a  add     rsp, 68h
0x180007c5e  jmp     short $+2
0x180007c60  jmp     rax
```
