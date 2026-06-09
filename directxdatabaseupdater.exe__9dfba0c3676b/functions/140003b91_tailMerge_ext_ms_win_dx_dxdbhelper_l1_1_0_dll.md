# __tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll

- ea: `0x140003b91`
- end: `0x140003c0a`
- name: `__tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003c10`

## callees

- `0x140003b91`
- `0x1400183b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_dx_dxdbhelper_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_dx_dxdbhelper_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003b91  mov     [rsp+arg_0], rcx
0x140003b96  mov     [rsp+arg_8], rdx
0x140003b9b  mov     [rsp+arg_10], r8
0x140003ba0  mov     [rsp+arg_18], r9
0x140003ba5  sub     rsp, 68h
0x140003ba9  movdqa  [rsp+68h+var_48], xmm0
0x140003baf  movdqa  [rsp+68h+var_38], xmm1
0x140003bb5  movdqa  [rsp+68h+var_28], xmm2
0x140003bbb  movdqa  [rsp+68h+var_18], xmm3
0x140003bc1  mov     rdx, rax
0x140003bc4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_dx_dxdbhelper_l1_1_0_dll
0x140003bcb  call    __delayLoadHelper2
0x140003bd0  movdqa  xmm0, [rsp+68h+var_48]
0x140003bd6  movdqa  xmm1, [rsp+68h+var_38]
0x140003bdc  movdqa  xmm2, [rsp+68h+var_28]
0x140003be2  movdqa  xmm3, [rsp+68h+var_18]
0x140003be8  mov     rcx, [rsp+68h+arg_0]
0x140003bed  mov     rdx, [rsp+68h+arg_8]
0x140003bf2  mov     r8, [rsp+68h+arg_10]
0x140003bfa  mov     r9, [rsp+68h+arg_18]
0x140003c02  add     rsp, 68h
0x140003c06  jmp     short $+2
0x140003c08  jmp     rax
```
