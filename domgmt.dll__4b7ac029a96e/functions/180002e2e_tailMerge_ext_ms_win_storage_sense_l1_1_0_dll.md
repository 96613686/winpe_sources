# __tailMerge_ext_ms_win_storage_sense_l1_1_0_dll

- ea: `0x180002e2e`
- end: `0x180002ea7`
- name: `__tailMerge_ext_ms_win_storage_sense_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ead`
- `0x180002ebf`
- `0x180002ed1`

## callees

- `0x180002e2e`
- `0x18000d4b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_storage_sense_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_storage_sense_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002e2e  mov     [rsp+arg_0], rcx
0x180002e33  mov     [rsp+arg_8], rdx
0x180002e38  mov     [rsp+arg_10], r8
0x180002e3d  mov     [rsp+arg_18], r9
0x180002e42  sub     rsp, 68h
0x180002e46  movdqa  [rsp+68h+var_48], xmm0
0x180002e4c  movdqa  [rsp+68h+var_38], xmm1
0x180002e52  movdqa  [rsp+68h+var_28], xmm2
0x180002e58  movdqa  [rsp+68h+var_18], xmm3
0x180002e5e  mov     rdx, rax
0x180002e61  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_storage_sense_l1_1_0_dll
0x180002e68  call    __delayLoadHelper2
0x180002e6d  movdqa  xmm0, [rsp+68h+var_48]
0x180002e73  movdqa  xmm1, [rsp+68h+var_38]
0x180002e79  movdqa  xmm2, [rsp+68h+var_28]
0x180002e7f  movdqa  xmm3, [rsp+68h+var_18]
0x180002e85  mov     rcx, [rsp+68h+arg_0]
0x180002e8a  mov     rdx, [rsp+68h+arg_8]
0x180002e8f  mov     r8, [rsp+68h+arg_10]
0x180002e97  mov     r9, [rsp+68h+arg_18]
0x180002e9f  add     rsp, 68h
0x180002ea3  jmp     short $+2
0x180002ea5  jmp     rax
```
