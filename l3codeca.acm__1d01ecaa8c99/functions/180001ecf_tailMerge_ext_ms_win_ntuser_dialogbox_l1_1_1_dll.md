# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll

- ea: `0x180001ecf`
- end: `0x180001f48`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f4e`

## callees

- `0x180001ecf`
- `0x180010f60`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001ecf  mov     [rsp+arg_0], rcx
0x180001ed4  mov     [rsp+arg_8], rdx
0x180001ed9  mov     [rsp+arg_10], r8
0x180001ede  mov     [rsp+arg_18], r9
0x180001ee3  sub     rsp, 68h
0x180001ee7  movdqa  [rsp+68h+var_48], xmm0
0x180001eed  movdqa  [rsp+68h+var_38], xmm1
0x180001ef3  movdqa  [rsp+68h+var_28], xmm2
0x180001ef9  movdqa  [rsp+68h+var_18], xmm3
0x180001eff  mov     rdx, rax
0x180001f02  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_1_dll
0x180001f09  call    __delayLoadHelper2
0x180001f0e  movdqa  xmm0, [rsp+68h+var_48]
0x180001f14  movdqa  xmm1, [rsp+68h+var_38]
0x180001f1a  movdqa  xmm2, [rsp+68h+var_28]
0x180001f20  movdqa  xmm3, [rsp+68h+var_18]
0x180001f26  mov     rcx, [rsp+68h+arg_0]
0x180001f2b  mov     rdx, [rsp+68h+arg_8]
0x180001f30  mov     r8, [rsp+68h+arg_10]
0x180001f38  mov     r9, [rsp+68h+arg_18]
0x180001f40  add     rsp, 68h
0x180001f44  jmp     short $+2
0x180001f46  jmp     rax
```
