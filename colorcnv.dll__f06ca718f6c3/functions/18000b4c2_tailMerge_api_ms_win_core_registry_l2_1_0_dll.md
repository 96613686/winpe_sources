# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x18000b4c2`
- end: `0x18000b53b`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b541`
- `0x18000b553`
- `0x18000bc47`

## callees

- `0x1800089e0`
- `0x18000b4c2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_registry_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b4c2  mov     [rsp+arg_0], rcx
0x18000b4c7  mov     [rsp+arg_8], rdx
0x18000b4cc  mov     [rsp+arg_10], r8
0x18000b4d1  mov     [rsp+arg_18], r9
0x18000b4d6  sub     rsp, 68h
0x18000b4da  movdqa  [rsp+68h+var_48], xmm0
0x18000b4e0  movdqa  [rsp+68h+var_38], xmm1
0x18000b4e6  movdqa  [rsp+68h+var_28], xmm2
0x18000b4ec  movdqa  [rsp+68h+var_18], xmm3
0x18000b4f2  mov     rdx, rax
0x18000b4f5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x18000b4fc  call    __delayLoadHelper2
0x18000b501  movdqa  xmm0, [rsp+68h+var_48]
0x18000b507  movdqa  xmm1, [rsp+68h+var_38]
0x18000b50d  movdqa  xmm2, [rsp+68h+var_28]
0x18000b513  movdqa  xmm3, [rsp+68h+var_18]
0x18000b519  mov     rcx, [rsp+68h+arg_0]
0x18000b51e  mov     rdx, [rsp+68h+arg_8]
0x18000b523  mov     r8, [rsp+68h+arg_10]
0x18000b52b  mov     r9, [rsp+68h+arg_18]
0x18000b533  add     rsp, 68h
0x18000b537  jmp     short $+2
0x18000b539  jmp     rax
```
