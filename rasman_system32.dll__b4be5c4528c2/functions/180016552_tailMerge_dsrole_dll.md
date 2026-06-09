# __tailMerge_dsrole_dll

- ea: `0x180016552`
- end: `0x1800165cb`
- name: `__tailMerge_dsrole_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800165d1`
- `0x1800165e3`

## callees

- `0x180014ae0`
- `0x180016552`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsrole_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dsrole_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180016552  mov     [rsp+arg_0], rcx
0x180016557  mov     [rsp+arg_8], rdx
0x18001655c  mov     [rsp+arg_10], r8
0x180016561  mov     [rsp+arg_18], r9
0x180016566  sub     rsp, 68h
0x18001656a  movdqa  [rsp+68h+var_48], xmm0
0x180016570  movdqa  [rsp+68h+var_38], xmm1
0x180016576  movdqa  [rsp+68h+var_28], xmm2
0x18001657c  movdqa  [rsp+68h+var_18], xmm3
0x180016582  mov     rdx, rax
0x180016585  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsrole_dll
0x18001658c  call    __delayLoadHelper2
0x180016591  movdqa  xmm0, [rsp+68h+var_48]
0x180016597  movdqa  xmm1, [rsp+68h+var_38]
0x18001659d  movdqa  xmm2, [rsp+68h+var_28]
0x1800165a3  movdqa  xmm3, [rsp+68h+var_18]
0x1800165a9  mov     rcx, [rsp+68h+arg_0]
0x1800165ae  mov     rdx, [rsp+68h+arg_8]
0x1800165b3  mov     r8, [rsp+68h+arg_10]
0x1800165bb  mov     r9, [rsp+68h+arg_18]
0x1800165c3  add     rsp, 68h
0x1800165c7  jmp     short $+2
0x1800165c9  jmp     rax
```
