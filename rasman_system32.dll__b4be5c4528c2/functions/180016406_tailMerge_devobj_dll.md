# __tailMerge_devobj_dll

- ea: `0x180016406`
- end: `0x18001647f`
- name: `__tailMerge_devobj_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016485`
- `0x180016497`
- `0x1800164a9`
- `0x1800164bb`

## callees

- `0x180014ae0`
- `0x180016406`

## pseudocode

```c
__int64 __fastcall _tailMerge_devobj_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_devobj_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180016406  mov     [rsp+arg_0], rcx
0x18001640b  mov     [rsp+arg_8], rdx
0x180016410  mov     [rsp+arg_10], r8
0x180016415  mov     [rsp+arg_18], r9
0x18001641a  sub     rsp, 68h
0x18001641e  movdqa  [rsp+68h+var_48], xmm0
0x180016424  movdqa  [rsp+68h+var_38], xmm1
0x18001642a  movdqa  [rsp+68h+var_28], xmm2
0x180016430  movdqa  [rsp+68h+var_18], xmm3
0x180016436  mov     rdx, rax
0x180016439  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_devobj_dll
0x180016440  call    __delayLoadHelper2
0x180016445  movdqa  xmm0, [rsp+68h+var_48]
0x18001644b  movdqa  xmm1, [rsp+68h+var_38]
0x180016451  movdqa  xmm2, [rsp+68h+var_28]
0x180016457  movdqa  xmm3, [rsp+68h+var_18]
0x18001645d  mov     rcx, [rsp+68h+arg_0]
0x180016462  mov     rdx, [rsp+68h+arg_8]
0x180016467  mov     r8, [rsp+68h+arg_10]
0x18001646f  mov     r9, [rsp+68h+arg_18]
0x180016477  add     rsp, 68h
0x18001647b  jmp     short $+2
0x18001647d  jmp     rax
```
