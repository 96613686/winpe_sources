# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x140002abf`
- end: `0x140002b38`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002b3e`
- `0x140002b50`
- `0x140002b62`

## callees

- `0x140002abf`
- `0x140015520`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002abf  mov     [rsp+arg_0], rcx
0x140002ac4  mov     [rsp+arg_8], rdx
0x140002ac9  mov     [rsp+arg_10], r8
0x140002ace  mov     [rsp+arg_18], r9
0x140002ad3  sub     rsp, 68h
0x140002ad7  movdqa  [rsp+68h+var_48], xmm0
0x140002add  movdqa  [rsp+68h+var_38], xmm1
0x140002ae3  movdqa  [rsp+68h+var_28], xmm2
0x140002ae9  movdqa  [rsp+68h+var_18], xmm3
0x140002aef  mov     rdx, rax
0x140002af2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x140002af9  call    __delayLoadHelper2
0x140002afe  movdqa  xmm0, [rsp+68h+var_48]
0x140002b04  movdqa  xmm1, [rsp+68h+var_38]
0x140002b0a  movdqa  xmm2, [rsp+68h+var_28]
0x140002b10  movdqa  xmm3, [rsp+68h+var_18]
0x140002b16  mov     rcx, [rsp+68h+arg_0]
0x140002b1b  mov     rdx, [rsp+68h+arg_8]
0x140002b20  mov     r8, [rsp+68h+arg_10]
0x140002b28  mov     r9, [rsp+68h+arg_18]
0x140002b30  add     rsp, 68h
0x140002b34  jmp     short $+2
0x140002b36  jmp     rax
```
