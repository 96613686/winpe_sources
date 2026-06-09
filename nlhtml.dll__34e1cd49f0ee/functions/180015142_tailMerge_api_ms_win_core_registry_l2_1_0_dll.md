# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x180015142`
- end: `0x1800151bb`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800151c1`

## callees

- `0x180015142`
- `0x1800231d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_registry_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015142  mov     [rsp+arg_0], rcx
0x180015147  mov     [rsp+arg_8], rdx
0x18001514c  mov     [rsp+arg_10], r8
0x180015151  mov     [rsp+arg_18], r9
0x180015156  sub     rsp, 68h
0x18001515a  movdqa  [rsp+68h+var_48], xmm0
0x180015160  movdqa  [rsp+68h+var_38], xmm1
0x180015166  movdqa  [rsp+68h+var_28], xmm2
0x18001516c  movdqa  [rsp+68h+var_18], xmm3
0x180015172  mov     rdx, rax
0x180015175  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x18001517c  call    __delayLoadHelper2
0x180015181  movdqa  xmm0, [rsp+68h+var_48]
0x180015187  movdqa  xmm1, [rsp+68h+var_38]
0x18001518d  movdqa  xmm2, [rsp+68h+var_28]
0x180015193  movdqa  xmm3, [rsp+68h+var_18]
0x180015199  mov     rcx, [rsp+68h+arg_0]
0x18001519e  mov     rdx, [rsp+68h+arg_8]
0x1800151a3  mov     r8, [rsp+68h+arg_10]
0x1800151ab  mov     r9, [rsp+68h+arg_18]
0x1800151b3  add     rsp, 68h
0x1800151b7  jmp     short $+2
0x1800151b9  jmp     rax
```
