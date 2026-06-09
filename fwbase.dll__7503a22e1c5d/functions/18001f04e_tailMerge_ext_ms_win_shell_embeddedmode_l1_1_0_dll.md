# __tailMerge_ext_ms_win_shell_embeddedmode_l1_1_0_dll

- ea: `0x18001f04e`
- end: `0x18001f0c7`
- name: `__tailMerge_ext_ms_win_shell_embeddedmode_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f0cd`

## callees

- `0x180013080`
- `0x18001f04e`

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
0x18001f04e  mov     [rsp+arg_0], rcx
0x18001f053  mov     [rsp+arg_8], rdx
0x18001f058  mov     [rsp+arg_10], r8
0x18001f05d  mov     [rsp+arg_18], r9
0x18001f062  sub     rsp, 68h
0x18001f066  movdqa  [rsp+68h+var_48], xmm0
0x18001f06c  movdqa  [rsp+68h+var_38], xmm1
0x18001f072  movdqa  [rsp+68h+var_28], xmm2
0x18001f078  movdqa  [rsp+68h+var_18], xmm3
0x18001f07e  mov     rdx, rax
0x18001f081  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_embeddedmode_l1_1_0_dll
0x18001f088  call    __delayLoadHelper2
0x18001f08d  movdqa  xmm0, [rsp+68h+var_48]
0x18001f093  movdqa  xmm1, [rsp+68h+var_38]
0x18001f099  movdqa  xmm2, [rsp+68h+var_28]
0x18001f09f  movdqa  xmm3, [rsp+68h+var_18]
0x18001f0a5  mov     rcx, [rsp+68h+arg_0]
0x18001f0aa  mov     rdx, [rsp+68h+arg_8]
0x18001f0af  mov     r8, [rsp+68h+arg_10]
0x18001f0b7  mov     r9, [rsp+68h+arg_18]
0x18001f0bf  add     rsp, 68h
0x18001f0c3  jmp     short $+2
0x18001f0c5  jmp     rax
```
