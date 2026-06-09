# __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll

- ea: `0x18000211d`
- end: `0x180002196`
- name: `__tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000219c`
- `0x1800021ae`
- `0x1800021c0`
- `0x18000225d`
- `0x18000226f`

## callees

- `0x18000211d`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000211d  mov     [rsp+arg_0], rcx
0x180002122  mov     [rsp+arg_8], rdx
0x180002127  mov     [rsp+arg_10], r8
0x18000212c  mov     [rsp+arg_18], r9
0x180002131  sub     rsp, 68h
0x180002135  movdqa  [rsp+68h+var_48], xmm0
0x18000213b  movdqa  [rsp+68h+var_38], xmm1
0x180002141  movdqa  [rsp+68h+var_28], xmm2
0x180002147  movdqa  [rsp+68h+var_18], xmm3
0x18000214d  mov     rdx, rax
0x180002150  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll
0x180002157  call    __delayLoadHelper2
0x18000215c  movdqa  xmm0, [rsp+68h+var_48]
0x180002162  movdqa  xmm1, [rsp+68h+var_38]
0x180002168  movdqa  xmm2, [rsp+68h+var_28]
0x18000216e  movdqa  xmm3, [rsp+68h+var_18]
0x180002174  mov     rcx, [rsp+68h+arg_0]
0x180002179  mov     rdx, [rsp+68h+arg_8]
0x18000217e  mov     r8, [rsp+68h+arg_10]
0x180002186  mov     r9, [rsp+68h+arg_18]
0x18000218e  add     rsp, 68h
0x180002192  jmp     short $+2
0x180002194  jmp     rax
```
