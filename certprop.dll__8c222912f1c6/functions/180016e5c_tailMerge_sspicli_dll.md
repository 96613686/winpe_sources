# __tailMerge_sspicli_dll

- ea: `0x180016e5c`
- end: `0x180016ed5`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016edb`
- `0x180016eff`
- `0x180016f11`
- `0x180016f23`

## callees

- `0x18000e1a0`
- `0x180016e5c`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180016e5c  mov     [rsp+arg_0], rcx
0x180016e61  mov     [rsp+arg_8], rdx
0x180016e66  mov     [rsp+arg_10], r8
0x180016e6b  mov     [rsp+arg_18], r9
0x180016e70  sub     rsp, 68h
0x180016e74  movdqa  [rsp+68h+var_48], xmm0
0x180016e7a  movdqa  [rsp+68h+var_38], xmm1
0x180016e80  movdqa  [rsp+68h+var_28], xmm2
0x180016e86  movdqa  [rsp+68h+var_18], xmm3
0x180016e8c  mov     rdx, rax
0x180016e8f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180016e96  call    __delayLoadHelper2
0x180016e9b  movdqa  xmm0, [rsp+68h+var_48]
0x180016ea1  movdqa  xmm1, [rsp+68h+var_38]
0x180016ea7  movdqa  xmm2, [rsp+68h+var_28]
0x180016ead  movdqa  xmm3, [rsp+68h+var_18]
0x180016eb3  mov     rcx, [rsp+68h+arg_0]
0x180016eb8  mov     rdx, [rsp+68h+arg_8]
0x180016ebd  mov     r8, [rsp+68h+arg_10]
0x180016ec5  mov     r9, [rsp+68h+arg_18]
0x180016ecd  add     rsp, 68h
0x180016ed1  jmp     short $+2
0x180016ed3  jmp     rax
```
