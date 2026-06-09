# __tailMerge_ext_ms_win_eventing_rundown_l1_1_0_dll

- ea: `0x180001f3e`
- end: `0x180001fb7`
- name: `__tailMerge_ext_ms_win_eventing_rundown_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001fbd`
- `0x180001fcf`

## callees

- `0x180001f3e`
- `0x180015660`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_eventing_rundown_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_eventing_rundown_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f3e  mov     [rsp+arg_0], rcx
0x180001f43  mov     [rsp+arg_8], rdx
0x180001f48  mov     [rsp+arg_10], r8
0x180001f4d  mov     [rsp+arg_18], r9
0x180001f52  sub     rsp, 68h
0x180001f56  movdqa  [rsp+68h+var_48], xmm0
0x180001f5c  movdqa  [rsp+68h+var_38], xmm1
0x180001f62  movdqa  [rsp+68h+var_28], xmm2
0x180001f68  movdqa  [rsp+68h+var_18], xmm3
0x180001f6e  mov     rdx, rax
0x180001f71  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_eventing_rundown_l1_1_0_dll
0x180001f78  call    __delayLoadHelper2
0x180001f7d  movdqa  xmm0, [rsp+68h+var_48]
0x180001f83  movdqa  xmm1, [rsp+68h+var_38]
0x180001f89  movdqa  xmm2, [rsp+68h+var_28]
0x180001f8f  movdqa  xmm3, [rsp+68h+var_18]
0x180001f95  mov     rcx, [rsp+68h+arg_0]
0x180001f9a  mov     rdx, [rsp+68h+arg_8]
0x180001f9f  mov     r8, [rsp+68h+arg_10]
0x180001fa7  mov     r9, [rsp+68h+arg_18]
0x180001faf  add     rsp, 68h
0x180001fb3  jmp     short $+2
0x180001fb5  jmp     rax
```
