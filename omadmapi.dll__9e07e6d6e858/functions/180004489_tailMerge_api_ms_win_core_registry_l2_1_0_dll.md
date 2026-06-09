# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x180004489`
- end: `0x180004502`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004508`

## callees

- `0x180004489`
- `0x1800223d0`

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
0x180004489  mov     [rsp+arg_0], rcx
0x18000448e  mov     [rsp+arg_8], rdx
0x180004493  mov     [rsp+arg_10], r8
0x180004498  mov     [rsp+arg_18], r9
0x18000449d  sub     rsp, 68h
0x1800044a1  movdqa  [rsp+68h+var_48], xmm0
0x1800044a7  movdqa  [rsp+68h+var_38], xmm1
0x1800044ad  movdqa  [rsp+68h+var_28], xmm2
0x1800044b3  movdqa  [rsp+68h+var_18], xmm3
0x1800044b9  mov     rdx, rax
0x1800044bc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x1800044c3  call    __delayLoadHelper2
0x1800044c8  movdqa  xmm0, [rsp+68h+var_48]
0x1800044ce  movdqa  xmm1, [rsp+68h+var_38]
0x1800044d4  movdqa  xmm2, [rsp+68h+var_28]
0x1800044da  movdqa  xmm3, [rsp+68h+var_18]
0x1800044e0  mov     rcx, [rsp+68h+arg_0]
0x1800044e5  mov     rdx, [rsp+68h+arg_8]
0x1800044ea  mov     r8, [rsp+68h+arg_10]
0x1800044f2  mov     r9, [rsp+68h+arg_18]
0x1800044fa  add     rsp, 68h
0x1800044fe  jmp     short $+2
0x180004500  jmp     rax
```
