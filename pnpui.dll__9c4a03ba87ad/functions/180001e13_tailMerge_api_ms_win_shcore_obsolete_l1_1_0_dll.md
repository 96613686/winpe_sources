# __tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll

- ea: `0x180001e13`
- end: `0x180001e8c`
- name: `__tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e92`

## callees

- `0x180001e13`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_obsolete_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e13  mov     [rsp+arg_0], rcx
0x180001e18  mov     [rsp+arg_8], rdx
0x180001e1d  mov     [rsp+arg_10], r8
0x180001e22  mov     [rsp+arg_18], r9
0x180001e27  sub     rsp, 68h
0x180001e2b  movdqa  [rsp+68h+var_48], xmm0
0x180001e31  movdqa  [rsp+68h+var_38], xmm1
0x180001e37  movdqa  [rsp+68h+var_28], xmm2
0x180001e3d  movdqa  [rsp+68h+var_18], xmm3
0x180001e43  mov     rdx, rax
0x180001e46  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_obsolete_l1_1_0_dll
0x180001e4d  call    __delayLoadHelper2
0x180001e52  movdqa  xmm0, [rsp+68h+var_48]
0x180001e58  movdqa  xmm1, [rsp+68h+var_38]
0x180001e5e  movdqa  xmm2, [rsp+68h+var_28]
0x180001e64  movdqa  xmm3, [rsp+68h+var_18]
0x180001e6a  mov     rcx, [rsp+68h+arg_0]
0x180001e6f  mov     rdx, [rsp+68h+arg_8]
0x180001e74  mov     r8, [rsp+68h+arg_10]
0x180001e7c  mov     r9, [rsp+68h+arg_18]
0x180001e84  add     rsp, 68h
0x180001e88  jmp     short $+2
0x180001e8a  jmp     rax
```
