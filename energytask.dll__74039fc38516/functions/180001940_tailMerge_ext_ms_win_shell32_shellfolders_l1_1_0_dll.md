# __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll

- ea: `0x180001940`
- end: `0x1800019b9`
- name: `__tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019bf`
- `0x1800019d1`

## callees

- `0x180001940`
- `0x180003480`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001940  mov     [rsp+arg_0], rcx
0x180001945  mov     [rsp+arg_8], rdx
0x18000194a  mov     [rsp+arg_10], r8
0x18000194f  mov     [rsp+arg_18], r9
0x180001954  sub     rsp, 68h
0x180001958  movdqa  [rsp+68h+var_48], xmm0
0x18000195e  movdqa  [rsp+68h+var_38], xmm1
0x180001964  movdqa  [rsp+68h+var_28], xmm2
0x18000196a  movdqa  [rsp+68h+var_18], xmm3
0x180001970  mov     rdx, rax
0x180001973  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll
0x18000197a  call    __delayLoadHelper2
0x18000197f  movdqa  xmm0, [rsp+68h+var_48]
0x180001985  movdqa  xmm1, [rsp+68h+var_38]
0x18000198b  movdqa  xmm2, [rsp+68h+var_28]
0x180001991  movdqa  xmm3, [rsp+68h+var_18]
0x180001997  mov     rcx, [rsp+68h+arg_0]
0x18000199c  mov     rdx, [rsp+68h+arg_8]
0x1800019a1  mov     r8, [rsp+68h+arg_10]
0x1800019a9  mov     r9, [rsp+68h+arg_18]
0x1800019b1  add     rsp, 68h
0x1800019b5  jmp     short $+2
0x1800019b7  jmp     rax
```
