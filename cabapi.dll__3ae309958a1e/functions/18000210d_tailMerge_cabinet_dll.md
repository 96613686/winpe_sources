# __tailMerge_cabinet_dll

- ea: `0x18000210d`
- end: `0x180002186`
- name: `__tailMerge_cabinet_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000218c`
- `0x18000219e`
- `0x1800021b0`
- `0x1800021c2`
- `0x1800021d4`
- `0x1800021e6`
- `0x1800021f8`
- `0x18000220a`
- `0x18000221c`

## callees

- `0x18000210d`
- `0x18000e720`

## pseudocode

```c
__int64 __fastcall _tailMerge_cabinet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((unsigned int *)&_DELAY_IMPORT_DESCRIPTOR_cabinet_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000210d  mov     [rsp+arg_0], rcx
0x180002112  mov     [rsp+arg_8], rdx
0x180002117  mov     [rsp+arg_10], r8
0x18000211c  mov     [rsp+arg_18], r9
0x180002121  sub     rsp, 68h
0x180002125  movdqa  [rsp+68h+var_48], xmm0
0x18000212b  movdqa  [rsp+68h+var_38], xmm1
0x180002131  movdqa  [rsp+68h+var_28], xmm2
0x180002137  movdqa  [rsp+68h+var_18], xmm3
0x18000213d  mov     rdx, rax
0x180002140  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cabinet_dll
0x180002147  call    __delayLoadHelper2
0x18000214c  movdqa  xmm0, [rsp+68h+var_48]
0x180002152  movdqa  xmm1, [rsp+68h+var_38]
0x180002158  movdqa  xmm2, [rsp+68h+var_28]
0x18000215e  movdqa  xmm3, [rsp+68h+var_18]
0x180002164  mov     rcx, [rsp+68h+arg_0]
0x180002169  mov     rdx, [rsp+68h+arg_8]
0x18000216e  mov     r8, [rsp+68h+arg_10]
0x180002176  mov     r9, [rsp+68h+arg_18]
0x18000217e  add     rsp, 68h
0x180002182  jmp     short $+2
0x180002184  jmp     rax
```
