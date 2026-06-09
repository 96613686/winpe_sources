# __tailMerge_msi_dll

- ea: `0x1400038d0`
- end: `0x140003949`
- name: `__tailMerge_msi_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000394f`
- `0x140003961`
- `0x140003973`
- `0x140003985`
- `0x140003997`
- `0x1400039a9`
- `0x1400039bb`
- `0x1400039cd`
- `0x1400039df`
- `0x1400039f1`
- `0x140003a03`
- `0x140003a15`
- `0x140003a27`
- `0x140003a39`
- `0x140003a4b`
- `0x140003a5d`
- `0x140003a6f`
- `0x140003a81`

## callees

- `0x1400038d0`
- `0x1400096a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_msi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_msi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400038d0  mov     [rsp+arg_0], rcx
0x1400038d5  mov     [rsp+arg_8], rdx
0x1400038da  mov     [rsp+arg_10], r8
0x1400038df  mov     [rsp+arg_18], r9
0x1400038e4  sub     rsp, 68h
0x1400038e8  movdqa  [rsp+68h+var_48], xmm0
0x1400038ee  movdqa  [rsp+68h+var_38], xmm1
0x1400038f4  movdqa  [rsp+68h+var_28], xmm2
0x1400038fa  movdqa  [rsp+68h+var_18], xmm3
0x140003900  mov     rdx, rax
0x140003903  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_msi_dll
0x14000390a  call    __delayLoadHelper2
0x14000390f  movdqa  xmm0, [rsp+68h+var_48]
0x140003915  movdqa  xmm1, [rsp+68h+var_38]
0x14000391b  movdqa  xmm2, [rsp+68h+var_28]
0x140003921  movdqa  xmm3, [rsp+68h+var_18]
0x140003927  mov     rcx, [rsp+68h+arg_0]
0x14000392c  mov     rdx, [rsp+68h+arg_8]
0x140003931  mov     r8, [rsp+68h+arg_10]
0x140003939  mov     r9, [rsp+68h+arg_18]
0x140003941  add     rsp, 68h
0x140003945  jmp     short $+2
0x140003947  jmp     rax
```
