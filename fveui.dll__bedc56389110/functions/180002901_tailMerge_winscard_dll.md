# __tailMerge_winscard_dll

- ea: `0x180002901`
- end: `0x18000297a`
- name: `__tailMerge_winscard_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002980`
- `0x180002992`
- `0x1800029a4`
- `0x1800029b6`
- `0x1800029c8`
- `0x1800029da`
- `0x1800029ec`

## callees

- `0x180002901`
- `0x18002b720`

## pseudocode

```c
__int64 __fastcall _tailMerge_winscard_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winscard_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002901  mov     [rsp+arg_0], rcx
0x180002906  mov     [rsp+arg_8], rdx
0x18000290b  mov     [rsp+arg_10], r8
0x180002910  mov     [rsp+arg_18], r9
0x180002915  sub     rsp, 68h
0x180002919  movdqa  [rsp+68h+var_48], xmm0
0x18000291f  movdqa  [rsp+68h+var_38], xmm1
0x180002925  movdqa  [rsp+68h+var_28], xmm2
0x18000292b  movdqa  [rsp+68h+var_18], xmm3
0x180002931  mov     rdx, rax
0x180002934  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winscard_dll
0x18000293b  call    __delayLoadHelper2
0x180002940  movdqa  xmm0, [rsp+68h+var_48]
0x180002946  movdqa  xmm1, [rsp+68h+var_38]
0x18000294c  movdqa  xmm2, [rsp+68h+var_28]
0x180002952  movdqa  xmm3, [rsp+68h+var_18]
0x180002958  mov     rcx, [rsp+68h+arg_0]
0x18000295d  mov     rdx, [rsp+68h+arg_8]
0x180002962  mov     r8, [rsp+68h+arg_10]
0x18000296a  mov     r9, [rsp+68h+arg_18]
0x180002972  add     rsp, 68h
0x180002976  jmp     short $+2
0x180002978  jmp     rax
```
