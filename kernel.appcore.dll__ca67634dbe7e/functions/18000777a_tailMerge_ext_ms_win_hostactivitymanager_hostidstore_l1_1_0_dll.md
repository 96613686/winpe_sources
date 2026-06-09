# __tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll

- ea: `0x18000777a`
- end: `0x1800077f3`
- name: `__tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800077f9`
- `0x18000780b`

## callees

- `0x180005080`
- `0x18000777a`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000777a  mov     [rsp+arg_0], rcx
0x18000777f  mov     [rsp+arg_8], rdx
0x180007784  mov     [rsp+arg_10], r8
0x180007789  mov     [rsp+arg_18], r9
0x18000778e  sub     rsp, 68h
0x180007792  movdqa  [rsp+68h+var_48], xmm0
0x180007798  movdqa  [rsp+68h+var_38], xmm1
0x18000779e  movdqa  [rsp+68h+var_28], xmm2
0x1800077a4  movdqa  [rsp+68h+var_18], xmm3
0x1800077aa  mov     rdx, rax
0x1800077ad  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll
0x1800077b4  call    __delayLoadHelper2
0x1800077b9  movdqa  xmm0, [rsp+68h+var_48]
0x1800077bf  movdqa  xmm1, [rsp+68h+var_38]
0x1800077c5  movdqa  xmm2, [rsp+68h+var_28]
0x1800077cb  movdqa  xmm3, [rsp+68h+var_18]
0x1800077d1  mov     rcx, [rsp+68h+arg_0]
0x1800077d6  mov     rdx, [rsp+68h+arg_8]
0x1800077db  mov     r8, [rsp+68h+arg_10]
0x1800077e3  mov     r9, [rsp+68h+arg_18]
0x1800077eb  add     rsp, 68h
0x1800077ef  jmp     short $+2
0x1800077f1  jmp     rax
```
