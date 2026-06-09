# __tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll

- ea: `0x180014739`
- end: `0x1800147b2`
- name: `__tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800147b8`
- `0x180014820`
- `0x180014832`
- `0x180014844`
- `0x180014856`
- `0x18001499c`

## callees

- `0x18000d890`
- `0x180014739`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_raschapext_eap_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180014739  mov     [rsp+arg_0], rcx
0x18001473e  mov     [rsp+arg_8], rdx
0x180014743  mov     [rsp+arg_10], r8
0x180014748  mov     [rsp+arg_18], r9
0x18001474d  sub     rsp, 68h
0x180014751  movdqa  [rsp+68h+var_48], xmm0
0x180014757  movdqa  [rsp+68h+var_38], xmm1
0x18001475d  movdqa  [rsp+68h+var_28], xmm2
0x180014763  movdqa  [rsp+68h+var_18], xmm3
0x180014769  mov     rdx, rax
0x18001476c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_raschapext_eap_l1_1_0_dll
0x180014773  call    __delayLoadHelper2
0x180014778  movdqa  xmm0, [rsp+68h+var_48]
0x18001477e  movdqa  xmm1, [rsp+68h+var_38]
0x180014784  movdqa  xmm2, [rsp+68h+var_28]
0x18001478a  movdqa  xmm3, [rsp+68h+var_18]
0x180014790  mov     rcx, [rsp+68h+arg_0]
0x180014795  mov     rdx, [rsp+68h+arg_8]
0x18001479a  mov     r8, [rsp+68h+arg_10]
0x1800147a2  mov     r9, [rsp+68h+arg_18]
0x1800147aa  add     rsp, 68h
0x1800147ae  jmp     short $+2
0x1800147b0  jmp     rax
```
