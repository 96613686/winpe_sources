# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180015630`
- end: `0x1800156a9`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800156af`
- `0x1800156c1`

## callees

- `0x180015630`
- `0x18001b550`

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
0x180015630  mov     [rsp+arg_0], rcx
0x180015635  mov     [rsp+arg_8], rdx
0x18001563a  mov     [rsp+arg_10], r8
0x18001563f  mov     [rsp+arg_18], r9
0x180015644  sub     rsp, 68h
0x180015648  movdqa  [rsp+68h+var_48], xmm0
0x18001564e  movdqa  [rsp+68h+var_38], xmm1
0x180015654  movdqa  [rsp+68h+var_28], xmm2
0x18001565a  movdqa  [rsp+68h+var_18], xmm3
0x180015660  mov     rdx, rax
0x180015663  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18001566a  call    __delayLoadHelper2
0x18001566f  movdqa  xmm0, [rsp+68h+var_48]
0x180015675  movdqa  xmm1, [rsp+68h+var_38]
0x18001567b  movdqa  xmm2, [rsp+68h+var_28]
0x180015681  movdqa  xmm3, [rsp+68h+var_18]
0x180015687  mov     rcx, [rsp+68h+arg_0]
0x18001568c  mov     rdx, [rsp+68h+arg_8]
0x180015691  mov     r8, [rsp+68h+arg_10]
0x180015699  mov     r9, [rsp+68h+arg_18]
0x1800156a1  add     rsp, 68h
0x1800156a5  jmp     short $+2
0x1800156a7  jmp     rax
```
