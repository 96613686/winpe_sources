# __tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll

- ea: `0x1800044b6`
- end: `0x18000452f`
- name: `__tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004535`

## callees

- `0x1800025a0`
- `0x1800044b6`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800044b6  mov     [rsp+arg_0], rcx
0x1800044bb  mov     [rsp+arg_8], rdx
0x1800044c0  mov     [rsp+arg_10], r8
0x1800044c5  mov     [rsp+arg_18], r9
0x1800044ca  sub     rsp, 68h
0x1800044ce  movdqa  [rsp+68h+var_48], xmm0
0x1800044d4  movdqa  [rsp+68h+var_38], xmm1
0x1800044da  movdqa  [rsp+68h+var_28], xmm2
0x1800044e0  movdqa  [rsp+68h+var_18], xmm3
0x1800044e6  mov     rdx, rax
0x1800044e9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll
0x1800044f0  call    __delayLoadHelper2
0x1800044f5  movdqa  xmm0, [rsp+68h+var_48]
0x1800044fb  movdqa  xmm1, [rsp+68h+var_38]
0x180004501  movdqa  xmm2, [rsp+68h+var_28]
0x180004507  movdqa  xmm3, [rsp+68h+var_18]
0x18000450d  mov     rcx, [rsp+68h+arg_0]
0x180004512  mov     rdx, [rsp+68h+arg_8]
0x180004517  mov     r8, [rsp+68h+arg_10]
0x18000451f  mov     r9, [rsp+68h+arg_18]
0x180004527  add     rsp, 68h
0x18000452b  jmp     short $+2
0x18000452d  jmp     rax
```
