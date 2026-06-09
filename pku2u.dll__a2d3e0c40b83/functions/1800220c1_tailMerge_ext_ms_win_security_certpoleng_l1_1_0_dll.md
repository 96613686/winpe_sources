# __tailMerge_ext_ms_win_security_certpoleng_l1_1_0_dll

- ea: `0x1800220c1`
- end: `0x18002213a`
- name: `__tailMerge_ext_ms_win_security_certpoleng_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022140`
- `0x180022152`
- `0x180022164`
- `0x180022176`
- `0x180022188`
- `0x18002219a`
- `0x1800221ac`
- `0x1800221be`
- `0x1800221d0`

## callees

- `0x18001a6d0`
- `0x1800220c1`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_certpoleng_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_certpoleng_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800220c1  mov     [rsp+arg_0], rcx
0x1800220c6  mov     [rsp+arg_8], rdx
0x1800220cb  mov     [rsp+arg_10], r8
0x1800220d0  mov     [rsp+arg_18], r9
0x1800220d5  sub     rsp, 68h
0x1800220d9  movdqa  [rsp+68h+var_48], xmm0
0x1800220df  movdqa  [rsp+68h+var_38], xmm1
0x1800220e5  movdqa  [rsp+68h+var_28], xmm2
0x1800220eb  movdqa  [rsp+68h+var_18], xmm3
0x1800220f1  mov     rdx, rax
0x1800220f4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_certpoleng_l1_1_0_dll
0x1800220fb  call    __delayLoadHelper2
0x180022100  movdqa  xmm0, [rsp+68h+var_48]
0x180022106  movdqa  xmm1, [rsp+68h+var_38]
0x18002210c  movdqa  xmm2, [rsp+68h+var_28]
0x180022112  movdqa  xmm3, [rsp+68h+var_18]
0x180022118  mov     rcx, [rsp+68h+arg_0]
0x18002211d  mov     rdx, [rsp+68h+arg_8]
0x180022122  mov     r8, [rsp+68h+arg_10]
0x18002212a  mov     r9, [rsp+68h+arg_18]
0x180022132  add     rsp, 68h
0x180022136  jmp     short $+2
0x180022138  jmp     rax
```
