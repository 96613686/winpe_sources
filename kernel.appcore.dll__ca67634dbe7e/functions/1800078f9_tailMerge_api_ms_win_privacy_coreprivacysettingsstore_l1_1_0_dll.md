# __tailMerge_api_ms_win_privacy_coreprivacysettingsstore_l1_1_0_dll

- ea: `0x1800078f9`
- end: `0x180007972`
- name: `__tailMerge_api_ms_win_privacy_coreprivacysettingsstore_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180007978`
- `0x18000798a`

## callees

- `0x180005080`
- `0x1800078f9`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_privacy_coreprivacysettingsstore_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_privacy_coreprivacysettingsstore_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800078f9  mov     [rsp+arg_0], rcx
0x1800078fe  mov     [rsp+arg_8], rdx
0x180007903  mov     [rsp+arg_10], r8
0x180007908  mov     [rsp+arg_18], r9
0x18000790d  sub     rsp, 68h
0x180007911  movdqa  [rsp+68h+var_48], xmm0
0x180007917  movdqa  [rsp+68h+var_38], xmm1
0x18000791d  movdqa  [rsp+68h+var_28], xmm2
0x180007923  movdqa  [rsp+68h+var_18], xmm3
0x180007929  mov     rdx, rax
0x18000792c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_privacy_coreprivacysettingsstore_l1_1_0_dll
0x180007933  call    __delayLoadHelper2
0x180007938  movdqa  xmm0, [rsp+68h+var_48]
0x18000793e  movdqa  xmm1, [rsp+68h+var_38]
0x180007944  movdqa  xmm2, [rsp+68h+var_28]
0x18000794a  movdqa  xmm3, [rsp+68h+var_18]
0x180007950  mov     rcx, [rsp+68h+arg_0]
0x180007955  mov     rdx, [rsp+68h+arg_8]
0x18000795a  mov     r8, [rsp+68h+arg_10]
0x180007962  mov     r9, [rsp+68h+arg_18]
0x18000796a  add     rsp, 68h
0x18000796e  jmp     short $+2
0x180007970  jmp     rax
```
