# __tailMerge_ext_ms_win_imm_l1_1_0_dll

- ea: `0x140006732`
- end: `0x1400067ab`
- name: `__tailMerge_ext_ms_win_imm_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400067b1`

## callees

- `0x140003b60`
- `0x140006732`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_imm_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_imm_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140006732  mov     [rsp+arg_0], rcx
0x140006737  mov     [rsp+arg_8], rdx
0x14000673c  mov     [rsp+arg_10], r8
0x140006741  mov     [rsp+arg_18], r9
0x140006746  sub     rsp, 68h
0x14000674a  movdqa  [rsp+68h+var_48], xmm0
0x140006750  movdqa  [rsp+68h+var_38], xmm1
0x140006756  movdqa  [rsp+68h+var_28], xmm2
0x14000675c  movdqa  [rsp+68h+var_18], xmm3
0x140006762  mov     rdx, rax
0x140006765  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_imm_l1_1_0_dll
0x14000676c  call    __delayLoadHelper2
0x140006771  movdqa  xmm0, [rsp+68h+var_48]
0x140006777  movdqa  xmm1, [rsp+68h+var_38]
0x14000677d  movdqa  xmm2, [rsp+68h+var_28]
0x140006783  movdqa  xmm3, [rsp+68h+var_18]
0x140006789  mov     rcx, [rsp+68h+arg_0]
0x14000678e  mov     rdx, [rsp+68h+arg_8]
0x140006793  mov     r8, [rsp+68h+arg_10]
0x14000679b  mov     r9, [rsp+68h+arg_18]
0x1400067a3  add     rsp, 68h
0x1400067a7  jmp     short $+2
0x1400067a9  jmp     rax
```
