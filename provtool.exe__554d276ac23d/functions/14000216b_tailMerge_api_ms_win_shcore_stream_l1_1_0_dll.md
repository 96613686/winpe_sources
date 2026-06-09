# __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll

- ea: `0x14000216b`
- end: `0x1400021e4`
- name: `__tailMerge_api_ms_win_shcore_stream_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400021ea`

## callees

- `0x14000216b`
- `0x14000dd40`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_stream_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000216b  mov     [rsp+arg_0], rcx
0x140002170  mov     [rsp+arg_8], rdx
0x140002175  mov     [rsp+arg_10], r8
0x14000217a  mov     [rsp+arg_18], r9
0x14000217f  sub     rsp, 68h
0x140002183  movdqa  [rsp+68h+var_48], xmm0
0x140002189  movdqa  [rsp+68h+var_38], xmm1
0x14000218f  movdqa  [rsp+68h+var_28], xmm2
0x140002195  movdqa  [rsp+68h+var_18], xmm3
0x14000219b  mov     rdx, rax
0x14000219e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_stream_l1_1_0_dll
0x1400021a5  call    __delayLoadHelper2
0x1400021aa  movdqa  xmm0, [rsp+68h+var_48]
0x1400021b0  movdqa  xmm1, [rsp+68h+var_38]
0x1400021b6  movdqa  xmm2, [rsp+68h+var_28]
0x1400021bc  movdqa  xmm3, [rsp+68h+var_18]
0x1400021c2  mov     rcx, [rsp+68h+arg_0]
0x1400021c7  mov     rdx, [rsp+68h+arg_8]
0x1400021cc  mov     r8, [rsp+68h+arg_10]
0x1400021d4  mov     r9, [rsp+68h+arg_18]
0x1400021dc  add     rsp, 68h
0x1400021e0  jmp     short $+2
0x1400021e2  jmp     rax
```
