# __tailMerge_ext_ms_win_appmodel_shellexecute_l1_1_0_dll

- ea: `0x180002fdc`
- end: `0x180003055`
- name: `__tailMerge_ext_ms_win_appmodel_shellexecute_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000305b`

## callees

- `0x180002fdc`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_appmodel_shellexecute_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_appmodel_shellexecute_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002fdc  mov     [rsp+arg_0], rcx
0x180002fe1  mov     [rsp+arg_8], rdx
0x180002fe6  mov     [rsp+arg_10], r8
0x180002feb  mov     [rsp+arg_18], r9
0x180002ff0  sub     rsp, 68h
0x180002ff4  movdqa  [rsp+68h+var_48], xmm0
0x180002ffa  movdqa  [rsp+68h+var_38], xmm1
0x180003000  movdqa  [rsp+68h+var_28], xmm2
0x180003006  movdqa  [rsp+68h+var_18], xmm3
0x18000300c  mov     rdx, rax
0x18000300f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_appmodel_shellexecute_l1_1_0_dll
0x180003016  call    __delayLoadHelper2
0x18000301b  movdqa  xmm0, [rsp+68h+var_48]
0x180003021  movdqa  xmm1, [rsp+68h+var_38]
0x180003027  movdqa  xmm2, [rsp+68h+var_28]
0x18000302d  movdqa  xmm3, [rsp+68h+var_18]
0x180003033  mov     rcx, [rsp+68h+arg_0]
0x180003038  mov     rdx, [rsp+68h+arg_8]
0x18000303d  mov     r8, [rsp+68h+arg_10]
0x180003045  mov     r9, [rsp+68h+arg_18]
0x18000304d  add     rsp, 68h
0x180003051  jmp     short $+2
0x180003053  jmp     rax
```
