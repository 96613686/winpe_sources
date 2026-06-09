# __tailMerge_api_ms_win_storage_reserve_l1_1_0_dll

- ea: `0x1400033ea`
- end: `0x140003463`
- name: `__tailMerge_api_ms_win_storage_reserve_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003469`

## callees

- `0x1400033ea`
- `0x140017530`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_storage_reserve_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_storage_reserve_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400033ea  mov     [rsp+arg_0], rcx
0x1400033ef  mov     [rsp+arg_8], rdx
0x1400033f4  mov     [rsp+arg_10], r8
0x1400033f9  mov     [rsp+arg_18], r9
0x1400033fe  sub     rsp, 68h
0x140003402  movdqa  [rsp+68h+var_48], xmm0
0x140003408  movdqa  [rsp+68h+var_38], xmm1
0x14000340e  movdqa  [rsp+68h+var_28], xmm2
0x140003414  movdqa  [rsp+68h+var_18], xmm3
0x14000341a  mov     rdx, rax
0x14000341d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_storage_reserve_l1_1_0_dll
0x140003424  call    __delayLoadHelper2
0x140003429  movdqa  xmm0, [rsp+68h+var_48]
0x14000342f  movdqa  xmm1, [rsp+68h+var_38]
0x140003435  movdqa  xmm2, [rsp+68h+var_28]
0x14000343b  movdqa  xmm3, [rsp+68h+var_18]
0x140003441  mov     rcx, [rsp+68h+arg_0]
0x140003446  mov     rdx, [rsp+68h+arg_8]
0x14000344b  mov     r8, [rsp+68h+arg_10]
0x140003453  mov     r9, [rsp+68h+arg_18]
0x14000345b  add     rsp, 68h
0x14000345f  jmp     short $+2
0x140003461  jmp     rax
```
