# __tailMerge_ext_ms_win_shell_embeddedmode_l1_1_0_dll

- ea: `0x180002046`
- end: `0x1800020bf`
- name: `__tailMerge_ext_ms_win_shell_embeddedmode_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020c5`

## callees

- `0x180002046`
- `0x180006940`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell_embeddedmode_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_embeddedmode_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002046  mov     [rsp+arg_0], rcx
0x18000204b  mov     [rsp+arg_8], rdx
0x180002050  mov     [rsp+arg_10], r8
0x180002055  mov     [rsp+arg_18], r9
0x18000205a  sub     rsp, 68h
0x18000205e  movdqa  [rsp+68h+var_48], xmm0
0x180002064  movdqa  [rsp+68h+var_38], xmm1
0x18000206a  movdqa  [rsp+68h+var_28], xmm2
0x180002070  movdqa  [rsp+68h+var_18], xmm3
0x180002076  mov     rdx, rax
0x180002079  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_embeddedmode_l1_1_0_dll
0x180002080  call    __delayLoadHelper2
0x180002085  movdqa  xmm0, [rsp+68h+var_48]
0x18000208b  movdqa  xmm1, [rsp+68h+var_38]
0x180002091  movdqa  xmm2, [rsp+68h+var_28]
0x180002097  movdqa  xmm3, [rsp+68h+var_18]
0x18000209d  mov     rcx, [rsp+68h+arg_0]
0x1800020a2  mov     rdx, [rsp+68h+arg_8]
0x1800020a7  mov     r8, [rsp+68h+arg_10]
0x1800020af  mov     r9, [rsp+68h+arg_18]
0x1800020b7  add     rsp, 68h
0x1800020bb  jmp     short $+2
0x1800020bd  jmp     rax
```
