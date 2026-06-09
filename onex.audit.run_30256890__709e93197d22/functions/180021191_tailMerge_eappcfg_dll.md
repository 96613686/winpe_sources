# __tailMerge_eappcfg_dll

- ea: `0x180021191`
- end: `0x18002120a`
- name: `__tailMerge_eappcfg_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021210`
- `0x180021222`
- `0x180021234`
- `0x180021246`
- `0x180021258`
- `0x18002126a`
- `0x18002127c`
- `0x18002128e`

## callees

- `0x180018b30`
- `0x180021191`

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
0x180021191  mov     [rsp+arg_0], rcx
0x180021196  mov     [rsp+arg_8], rdx
0x18002119b  mov     [rsp+arg_10], r8
0x1800211a0  mov     [rsp+arg_18], r9
0x1800211a5  sub     rsp, 68h
0x1800211a9  movdqa  [rsp+68h+var_48], xmm0
0x1800211af  movdqa  [rsp+68h+var_38], xmm1
0x1800211b5  movdqa  [rsp+68h+var_28], xmm2
0x1800211bb  movdqa  [rsp+68h+var_18], xmm3
0x1800211c1  mov     rdx, rax
0x1800211c4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_eappcfg_dll
0x1800211cb  call    __delayLoadHelper2
0x1800211d0  movdqa  xmm0, [rsp+68h+var_48]
0x1800211d6  movdqa  xmm1, [rsp+68h+var_38]
0x1800211dc  movdqa  xmm2, [rsp+68h+var_28]
0x1800211e2  movdqa  xmm3, [rsp+68h+var_18]
0x1800211e8  mov     rcx, [rsp+68h+arg_0]
0x1800211ed  mov     rdx, [rsp+68h+arg_8]
0x1800211f2  mov     r8, [rsp+68h+arg_10]
0x1800211fa  mov     r9, [rsp+68h+arg_18]
0x180021202  add     rsp, 68h
0x180021206  jmp     short $+2
0x180021208  jmp     rax
```
