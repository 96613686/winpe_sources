# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x140001fca`
- end: `0x140002043`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140002049`

## callees

- `0x140001fca`
- `0x1400072a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001fca  mov     [rsp+arg_0], rcx
0x140001fcf  mov     [rsp+arg_8], rdx
0x140001fd4  mov     [rsp+arg_10], r8
0x140001fd9  mov     [rsp+arg_18], r9
0x140001fde  sub     rsp, 68h
0x140001fe2  movdqa  [rsp+68h+var_48], xmm0
0x140001fe8  movdqa  [rsp+68h+var_38], xmm1
0x140001fee  movdqa  [rsp+68h+var_28], xmm2
0x140001ff4  movdqa  [rsp+68h+var_18], xmm3
0x140001ffa  mov     rdx, rax
0x140001ffd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x140002004  call    __delayLoadHelper2
0x140002009  movdqa  xmm0, [rsp+68h+var_48]
0x14000200f  movdqa  xmm1, [rsp+68h+var_38]
0x140002015  movdqa  xmm2, [rsp+68h+var_28]
0x14000201b  movdqa  xmm3, [rsp+68h+var_18]
0x140002021  mov     rcx, [rsp+68h+arg_0]
0x140002026  mov     rdx, [rsp+68h+arg_8]
0x14000202b  mov     r8, [rsp+68h+arg_10]
0x140002033  mov     r9, [rsp+68h+arg_18]
0x14000203b  add     rsp, 68h
0x14000203f  jmp     short $+2
0x140002041  jmp     rax
```
