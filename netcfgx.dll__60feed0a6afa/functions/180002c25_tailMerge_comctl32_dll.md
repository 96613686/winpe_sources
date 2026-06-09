# __tailMerge_comctl32_dll

- ea: `0x180002c25`
- end: `0x180002c9e`
- name: `__tailMerge_comctl32_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ca4`
- `0x180002ee4`
- `0x180002ef6`
- `0x180003011`

## callees

- `0x180002c25`
- `0x180011dd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_comctl32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_comctl32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002c25  mov     [rsp+arg_0], rcx
0x180002c2a  mov     [rsp+arg_8], rdx
0x180002c2f  mov     [rsp+arg_10], r8
0x180002c34  mov     [rsp+arg_18], r9
0x180002c39  sub     rsp, 68h
0x180002c3d  movdqa  [rsp+68h+var_48], xmm0
0x180002c43  movdqa  [rsp+68h+var_38], xmm1
0x180002c49  movdqa  [rsp+68h+var_28], xmm2
0x180002c4f  movdqa  [rsp+68h+var_18], xmm3
0x180002c55  mov     rdx, rax
0x180002c58  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comctl32_dll
0x180002c5f  call    __delayLoadHelper2
0x180002c64  movdqa  xmm0, [rsp+68h+var_48]
0x180002c6a  movdqa  xmm1, [rsp+68h+var_38]
0x180002c70  movdqa  xmm2, [rsp+68h+var_28]
0x180002c76  movdqa  xmm3, [rsp+68h+var_18]
0x180002c7c  mov     rcx, [rsp+68h+arg_0]
0x180002c81  mov     rdx, [rsp+68h+arg_8]
0x180002c86  mov     r8, [rsp+68h+arg_10]
0x180002c8e  mov     r9, [rsp+68h+arg_18]
0x180002c96  add     rsp, 68h
0x180002c9a  jmp     short $+2
0x180002c9c  jmp     rax
```
