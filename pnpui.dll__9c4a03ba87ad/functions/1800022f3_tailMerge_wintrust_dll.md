# __tailMerge_wintrust_dll

- ea: `0x1800022f3`
- end: `0x18000236c`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002372`
- `0x180002384`
- `0x180002396`
- `0x1800023a8`

## callees

- `0x1800022f3`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wintrust_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022f3  mov     [rsp+arg_0], rcx
0x1800022f8  mov     [rsp+arg_8], rdx
0x1800022fd  mov     [rsp+arg_10], r8
0x180002302  mov     [rsp+arg_18], r9
0x180002307  sub     rsp, 68h
0x18000230b  movdqa  [rsp+68h+var_48], xmm0
0x180002311  movdqa  [rsp+68h+var_38], xmm1
0x180002317  movdqa  [rsp+68h+var_28], xmm2
0x18000231d  movdqa  [rsp+68h+var_18], xmm3
0x180002323  mov     rdx, rax
0x180002326  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x18000232d  call    __delayLoadHelper2
0x180002332  movdqa  xmm0, [rsp+68h+var_48]
0x180002338  movdqa  xmm1, [rsp+68h+var_38]
0x18000233e  movdqa  xmm2, [rsp+68h+var_28]
0x180002344  movdqa  xmm3, [rsp+68h+var_18]
0x18000234a  mov     rcx, [rsp+68h+arg_0]
0x18000234f  mov     rdx, [rsp+68h+arg_8]
0x180002354  mov     r8, [rsp+68h+arg_10]
0x18000235c  mov     r9, [rsp+68h+arg_18]
0x180002364  add     rsp, 68h
0x180002368  jmp     short $+2
0x18000236a  jmp     rax
```
