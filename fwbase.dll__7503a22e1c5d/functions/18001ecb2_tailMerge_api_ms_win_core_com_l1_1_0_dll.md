# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18001ecb2`
- end: `0x18001ed2b`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ed31`
- `0x18001ed43`

## callees

- `0x180013080`
- `0x18001ecb2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001ecb2  mov     [rsp+arg_0], rcx
0x18001ecb7  mov     [rsp+arg_8], rdx
0x18001ecbc  mov     [rsp+arg_10], r8
0x18001ecc1  mov     [rsp+arg_18], r9
0x18001ecc6  sub     rsp, 68h
0x18001ecca  movdqa  [rsp+68h+var_48], xmm0
0x18001ecd0  movdqa  [rsp+68h+var_38], xmm1
0x18001ecd6  movdqa  [rsp+68h+var_28], xmm2
0x18001ecdc  movdqa  [rsp+68h+var_18], xmm3
0x18001ece2  mov     rdx, rax
0x18001ece5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18001ecec  call    __delayLoadHelper2
0x18001ecf1  movdqa  xmm0, [rsp+68h+var_48]
0x18001ecf7  movdqa  xmm1, [rsp+68h+var_38]
0x18001ecfd  movdqa  xmm2, [rsp+68h+var_28]
0x18001ed03  movdqa  xmm3, [rsp+68h+var_18]
0x18001ed09  mov     rcx, [rsp+68h+arg_0]
0x18001ed0e  mov     rdx, [rsp+68h+arg_8]
0x18001ed13  mov     r8, [rsp+68h+arg_10]
0x18001ed1b  mov     r9, [rsp+68h+arg_18]
0x18001ed23  add     rsp, 68h
0x18001ed27  jmp     short $+2
0x18001ed29  jmp     rax
```
