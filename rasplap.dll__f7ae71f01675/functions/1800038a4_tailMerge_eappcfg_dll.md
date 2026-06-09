# __tailMerge_eappcfg_dll

- ea: `0x1800038a4`
- end: `0x18000391d`
- name: `__tailMerge_eappcfg_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003923`
- `0x180003935`
- `0x180003947`
- `0x180003959`

## callees

- `0x1800015c0`
- `0x1800038a4`

## pseudocode

```c
__int64 __fastcall _tailMerge_eappcfg_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_eappcfg_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800038a4  mov     [rsp+arg_0], rcx
0x1800038a9  mov     [rsp+arg_8], rdx
0x1800038ae  mov     [rsp+arg_10], r8
0x1800038b3  mov     [rsp+arg_18], r9
0x1800038b8  sub     rsp, 68h
0x1800038bc  movdqa  [rsp+68h+var_48], xmm0
0x1800038c2  movdqa  [rsp+68h+var_38], xmm1
0x1800038c8  movdqa  [rsp+68h+var_28], xmm2
0x1800038ce  movdqa  [rsp+68h+var_18], xmm3
0x1800038d4  mov     rdx, rax
0x1800038d7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_eappcfg_dll
0x1800038de  call    __delayLoadHelper2
0x1800038e3  movdqa  xmm0, [rsp+68h+var_48]
0x1800038e9  movdqa  xmm1, [rsp+68h+var_38]
0x1800038ef  movdqa  xmm2, [rsp+68h+var_28]
0x1800038f5  movdqa  xmm3, [rsp+68h+var_18]
0x1800038fb  mov     rcx, [rsp+68h+arg_0]
0x180003900  mov     rdx, [rsp+68h+arg_8]
0x180003905  mov     r8, [rsp+68h+arg_10]
0x18000390d  mov     r9, [rsp+68h+arg_18]
0x180003915  add     rsp, 68h
0x180003919  jmp     short $+2
0x18000391b  jmp     rax
```
