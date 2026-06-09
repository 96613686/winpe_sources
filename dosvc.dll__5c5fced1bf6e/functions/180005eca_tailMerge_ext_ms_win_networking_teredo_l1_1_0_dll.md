# __tailMerge_ext_ms_win_networking_teredo_l1_1_0_dll

- ea: `0x180005eca`
- end: `0x180005f43`
- name: `__tailMerge_ext_ms_win_networking_teredo_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005f49`
- `0x180005f5b`

## callees

- `0x1800023e0`
- `0x180005eca`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_networking_teredo_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_networking_teredo_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005eca  mov     [rsp+arg_0], rcx
0x180005ecf  mov     [rsp+arg_8], rdx
0x180005ed4  mov     [rsp+arg_10], r8
0x180005ed9  mov     [rsp+arg_18], r9
0x180005ede  sub     rsp, 68h
0x180005ee2  movdqa  [rsp+68h+var_48], xmm0
0x180005ee8  movdqa  [rsp+68h+var_38], xmm1
0x180005eee  movdqa  [rsp+68h+var_28], xmm2
0x180005ef4  movdqa  [rsp+68h+var_18], xmm3
0x180005efa  mov     rdx, rax
0x180005efd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_networking_teredo_l1_1_0_dll
0x180005f04  call    __delayLoadHelper2
0x180005f09  movdqa  xmm0, [rsp+68h+var_48]
0x180005f0f  movdqa  xmm1, [rsp+68h+var_38]
0x180005f15  movdqa  xmm2, [rsp+68h+var_28]
0x180005f1b  movdqa  xmm3, [rsp+68h+var_18]
0x180005f21  mov     rcx, [rsp+68h+arg_0]
0x180005f26  mov     rdx, [rsp+68h+arg_8]
0x180005f2b  mov     r8, [rsp+68h+arg_10]
0x180005f33  mov     r9, [rsp+68h+arg_18]
0x180005f3b  add     rsp, 68h
0x180005f3f  jmp     short $+2
0x180005f41  jmp     rax
```
