# __tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll

- ea: `0x140002ea5`
- end: `0x140002f1e`
- name: `__tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002f24`

## callees

- `0x140002ea5`
- `0x14000fd50`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resources_languageoverlay_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002ea5  mov     [rsp+arg_0], rcx
0x140002eaa  mov     [rsp+arg_8], rdx
0x140002eaf  mov     [rsp+arg_10], r8
0x140002eb4  mov     [rsp+arg_18], r9
0x140002eb9  sub     rsp, 68h
0x140002ebd  movdqa  [rsp+68h+var_48], xmm0
0x140002ec3  movdqa  [rsp+68h+var_38], xmm1
0x140002ec9  movdqa  [rsp+68h+var_28], xmm2
0x140002ecf  movdqa  [rsp+68h+var_18], xmm3
0x140002ed5  mov     rdx, rax
0x140002ed8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resources_languageoverlay_l1_1_4_dll
0x140002edf  call    __delayLoadHelper2
0x140002ee4  movdqa  xmm0, [rsp+68h+var_48]
0x140002eea  movdqa  xmm1, [rsp+68h+var_38]
0x140002ef0  movdqa  xmm2, [rsp+68h+var_28]
0x140002ef6  movdqa  xmm3, [rsp+68h+var_18]
0x140002efc  mov     rcx, [rsp+68h+arg_0]
0x140002f01  mov     rdx, [rsp+68h+arg_8]
0x140002f06  mov     r8, [rsp+68h+arg_10]
0x140002f0e  mov     r9, [rsp+68h+arg_18]
0x140002f16  add     rsp, 68h
0x140002f1a  jmp     short $+2
0x140002f1c  jmp     rax
```
