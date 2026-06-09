# __tailMerge_api_ms_win_eventing_obsolete_l1_1_0_dll

- ea: `0x18001637b`
- end: `0x1800163f4`
- name: `__tailMerge_api_ms_win_eventing_obsolete_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800163fa`

## callees

- `0x180014ae0`
- `0x18001637b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventing_obsolete_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_obsolete_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001637b  mov     [rsp+arg_0], rcx
0x180016380  mov     [rsp+arg_8], rdx
0x180016385  mov     [rsp+arg_10], r8
0x18001638a  mov     [rsp+arg_18], r9
0x18001638f  sub     rsp, 68h
0x180016393  movdqa  [rsp+68h+var_48], xmm0
0x180016399  movdqa  [rsp+68h+var_38], xmm1
0x18001639f  movdqa  [rsp+68h+var_28], xmm2
0x1800163a5  movdqa  [rsp+68h+var_18], xmm3
0x1800163ab  mov     rdx, rax
0x1800163ae  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_obsolete_l1_1_0_dll
0x1800163b5  call    __delayLoadHelper2
0x1800163ba  movdqa  xmm0, [rsp+68h+var_48]
0x1800163c0  movdqa  xmm1, [rsp+68h+var_38]
0x1800163c6  movdqa  xmm2, [rsp+68h+var_28]
0x1800163cc  movdqa  xmm3, [rsp+68h+var_18]
0x1800163d2  mov     rcx, [rsp+68h+arg_0]
0x1800163d7  mov     rdx, [rsp+68h+arg_8]
0x1800163dc  mov     r8, [rsp+68h+arg_10]
0x1800163e4  mov     r9, [rsp+68h+arg_18]
0x1800163ec  add     rsp, 68h
0x1800163f0  jmp     short $+2
0x1800163f2  jmp     rax
```
