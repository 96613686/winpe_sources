# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x140002f91`
- end: `0x14000300a`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003010`
- `0x140003078`
- `0x14000308a`

## callees

- `0x140002f91`
- `0x140019490`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002f91  mov     [rsp+arg_0], rcx
0x140002f96  mov     [rsp+arg_8], rdx
0x140002f9b  mov     [rsp+arg_10], r8
0x140002fa0  mov     [rsp+arg_18], r9
0x140002fa5  sub     rsp, 68h
0x140002fa9  movdqa  [rsp+68h+var_48], xmm0
0x140002faf  movdqa  [rsp+68h+var_38], xmm1
0x140002fb5  movdqa  [rsp+68h+var_28], xmm2
0x140002fbb  movdqa  [rsp+68h+var_18], xmm3
0x140002fc1  mov     rdx, rax
0x140002fc4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x140002fcb  call    __delayLoadHelper2
0x140002fd0  movdqa  xmm0, [rsp+68h+var_48]
0x140002fd6  movdqa  xmm1, [rsp+68h+var_38]
0x140002fdc  movdqa  xmm2, [rsp+68h+var_28]
0x140002fe2  movdqa  xmm3, [rsp+68h+var_18]
0x140002fe8  mov     rcx, [rsp+68h+arg_0]
0x140002fed  mov     rdx, [rsp+68h+arg_8]
0x140002ff2  mov     r8, [rsp+68h+arg_10]
0x140002ffa  mov     r9, [rsp+68h+arg_18]
0x140003002  add     rsp, 68h
0x140003006  jmp     short $+2
0x140003008  jmp     rax
```
