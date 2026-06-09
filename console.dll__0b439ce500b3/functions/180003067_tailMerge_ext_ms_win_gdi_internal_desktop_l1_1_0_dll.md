# __tailMerge_ext_ms_win_gdi_internal_desktop_l1_1_0_dll

- ea: `0x180003067`
- end: `0x1800030e0`
- name: `__tailMerge_ext_ms_win_gdi_internal_desktop_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800030e6`

## callees

- `0x180003067`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_internal_desktop_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_internal_desktop_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003067  mov     [rsp+arg_0], rcx
0x18000306c  mov     [rsp+arg_8], rdx
0x180003071  mov     [rsp+arg_10], r8
0x180003076  mov     [rsp+arg_18], r9
0x18000307b  sub     rsp, 68h
0x18000307f  movdqa  [rsp+68h+var_48], xmm0
0x180003085  movdqa  [rsp+68h+var_38], xmm1
0x18000308b  movdqa  [rsp+68h+var_28], xmm2
0x180003091  movdqa  [rsp+68h+var_18], xmm3
0x180003097  mov     rdx, rax
0x18000309a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_internal_desktop_l1_1_0_dll
0x1800030a1  call    __delayLoadHelper2
0x1800030a6  movdqa  xmm0, [rsp+68h+var_48]
0x1800030ac  movdqa  xmm1, [rsp+68h+var_38]
0x1800030b2  movdqa  xmm2, [rsp+68h+var_28]
0x1800030b8  movdqa  xmm3, [rsp+68h+var_18]
0x1800030be  mov     rcx, [rsp+68h+arg_0]
0x1800030c3  mov     rdx, [rsp+68h+arg_8]
0x1800030c8  mov     r8, [rsp+68h+arg_10]
0x1800030d0  mov     r9, [rsp+68h+arg_18]
0x1800030d8  add     rsp, 68h
0x1800030dc  jmp     short $+2
0x1800030de  jmp     rax
```
