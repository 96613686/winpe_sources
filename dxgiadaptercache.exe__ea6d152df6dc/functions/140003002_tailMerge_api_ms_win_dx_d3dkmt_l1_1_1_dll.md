# __tailMerge_api_ms_win_dx_d3dkmt_l1_1_1_dll

- ea: `0x140003002`
- end: `0x14000307b`
- name: `__tailMerge_api_ms_win_dx_d3dkmt_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003081`

## callees

- `0x140003002`
- `0x140011270`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_dx_d3dkmt_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_dx_d3dkmt_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003002  mov     [rsp+arg_0], rcx
0x140003007  mov     [rsp+arg_8], rdx
0x14000300c  mov     [rsp+arg_10], r8
0x140003011  mov     [rsp+arg_18], r9
0x140003016  sub     rsp, 68h
0x14000301a  movdqa  [rsp+68h+var_48], xmm0
0x140003020  movdqa  [rsp+68h+var_38], xmm1
0x140003026  movdqa  [rsp+68h+var_28], xmm2
0x14000302c  movdqa  [rsp+68h+var_18], xmm3
0x140003032  mov     rdx, rax
0x140003035  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_dx_d3dkmt_l1_1_1_dll
0x14000303c  call    __delayLoadHelper2
0x140003041  movdqa  xmm0, [rsp+68h+var_48]
0x140003047  movdqa  xmm1, [rsp+68h+var_38]
0x14000304d  movdqa  xmm2, [rsp+68h+var_28]
0x140003053  movdqa  xmm3, [rsp+68h+var_18]
0x140003059  mov     rcx, [rsp+68h+arg_0]
0x14000305e  mov     rdx, [rsp+68h+arg_8]
0x140003063  mov     r8, [rsp+68h+arg_10]
0x14000306b  mov     r9, [rsp+68h+arg_18]
0x140003073  add     rsp, 68h
0x140003077  jmp     short $+2
0x140003079  jmp     rax
```
