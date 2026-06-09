# __tailMerge_api_ms_win_dx_d3dkmt_l1_1_0_dll

- ea: `0x140002e3d`
- end: `0x140002eb6`
- name: `__tailMerge_api_ms_win_dx_d3dkmt_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002ebc`
- `0x140003093`

## callees

- `0x140002e3d`
- `0x140011270`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_dx_d3dkmt_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_dx_d3dkmt_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002e3d  mov     [rsp+arg_0], rcx
0x140002e42  mov     [rsp+arg_8], rdx
0x140002e47  mov     [rsp+arg_10], r8
0x140002e4c  mov     [rsp+arg_18], r9
0x140002e51  sub     rsp, 68h
0x140002e55  movdqa  [rsp+68h+var_48], xmm0
0x140002e5b  movdqa  [rsp+68h+var_38], xmm1
0x140002e61  movdqa  [rsp+68h+var_28], xmm2
0x140002e67  movdqa  [rsp+68h+var_18], xmm3
0x140002e6d  mov     rdx, rax
0x140002e70  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_dx_d3dkmt_l1_1_0_dll
0x140002e77  call    __delayLoadHelper2
0x140002e7c  movdqa  xmm0, [rsp+68h+var_48]
0x140002e82  movdqa  xmm1, [rsp+68h+var_38]
0x140002e88  movdqa  xmm2, [rsp+68h+var_28]
0x140002e8e  movdqa  xmm3, [rsp+68h+var_18]
0x140002e94  mov     rcx, [rsp+68h+arg_0]
0x140002e99  mov     rdx, [rsp+68h+arg_8]
0x140002e9e  mov     r8, [rsp+68h+arg_10]
0x140002ea6  mov     r9, [rsp+68h+arg_18]
0x140002eae  add     rsp, 68h
0x140002eb2  jmp     short $+2
0x140002eb4  jmp     rax
```
