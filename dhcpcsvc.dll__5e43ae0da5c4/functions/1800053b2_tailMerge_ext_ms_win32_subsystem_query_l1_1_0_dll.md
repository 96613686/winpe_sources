# __tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll

- ea: `0x1800053b2`
- end: `0x18000542b`
- name: `__tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005431`

## callees

- `0x1800030d0`
- `0x1800053b2`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800053b2  mov     [rsp+arg_0], rcx
0x1800053b7  mov     [rsp+arg_8], rdx
0x1800053bc  mov     [rsp+arg_10], r8
0x1800053c1  mov     [rsp+arg_18], r9
0x1800053c6  sub     rsp, 68h
0x1800053ca  movdqa  [rsp+68h+var_48], xmm0
0x1800053d0  movdqa  [rsp+68h+var_38], xmm1
0x1800053d6  movdqa  [rsp+68h+var_28], xmm2
0x1800053dc  movdqa  [rsp+68h+var_18], xmm3
0x1800053e2  mov     rdx, rax
0x1800053e5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll
0x1800053ec  call    __delayLoadHelper2
0x1800053f1  movdqa  xmm0, [rsp+68h+var_48]
0x1800053f7  movdqa  xmm1, [rsp+68h+var_38]
0x1800053fd  movdqa  xmm2, [rsp+68h+var_28]
0x180005403  movdqa  xmm3, [rsp+68h+var_18]
0x180005409  mov     rcx, [rsp+68h+arg_0]
0x18000540e  mov     rdx, [rsp+68h+arg_8]
0x180005413  mov     r8, [rsp+68h+arg_10]
0x18000541b  mov     r9, [rsp+68h+arg_18]
0x180005423  add     rsp, 68h
0x180005427  jmp     short $+2
0x180005429  jmp     rax
```
