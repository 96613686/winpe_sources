# __tailMerge_ext_ms_win_core_dhcp6client_l1_1_0_dll

- ea: `0x18001ab26`
- end: `0x18001ab9f`
- name: `__tailMerge_ext_ms_win_core_dhcp6client_l1_1_0_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001aba5`
- `0x18001abb7`

## callees

- `0x18000f880`
- `0x18001ab26`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_dhcp6client_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_dhcp6client_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001ab26  mov     [rsp+arg_0], rcx
0x18001ab2b  mov     [rsp+arg_8], rdx
0x18001ab30  mov     [rsp+arg_10], r8
0x18001ab35  mov     [rsp+arg_18], r9
0x18001ab3a  sub     rsp, 68h
0x18001ab3e  movdqa  [rsp+68h+var_48], xmm0
0x18001ab44  movdqa  [rsp+68h+var_38], xmm1
0x18001ab4a  movdqa  [rsp+68h+var_28], xmm2
0x18001ab50  movdqa  [rsp+68h+var_18], xmm3
0x18001ab56  mov     rdx, rax
0x18001ab59  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_dhcp6client_l1_1_0_dll
0x18001ab60  call    __delayLoadHelper2
0x18001ab65  movdqa  xmm0, [rsp+68h+var_48]
0x18001ab6b  movdqa  xmm1, [rsp+68h+var_38]
0x18001ab71  movdqa  xmm2, [rsp+68h+var_28]
0x18001ab77  movdqa  xmm3, [rsp+68h+var_18]
0x18001ab7d  mov     rcx, [rsp+68h+arg_0]
0x18001ab82  mov     rdx, [rsp+68h+arg_8]
0x18001ab87  mov     r8, [rsp+68h+arg_10]
0x18001ab8f  mov     r9, [rsp+68h+arg_18]
0x18001ab97  add     rsp, 68h
0x18001ab9b  jmp     short $+2
0x18001ab9d  jmp     rax
```
