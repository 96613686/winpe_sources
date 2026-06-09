# __tailMerge_ws2_32_dll

- ea: `0x180015670`
- end: `0x1800156e9`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800156ef`
- `0x18001579e`
- `0x18001585f`

## callees

- `0x180014230`
- `0x180015670`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015670  mov     [rsp+arg_0], rcx
0x180015675  mov     [rsp+arg_8], rdx
0x18001567a  mov     [rsp+arg_10], r8
0x18001567f  mov     [rsp+arg_18], r9
0x180015684  sub     rsp, 68h
0x180015688  movdqa  [rsp+68h+var_48], xmm0
0x18001568e  movdqa  [rsp+68h+var_38], xmm1
0x180015694  movdqa  [rsp+68h+var_28], xmm2
0x18001569a  movdqa  [rsp+68h+var_18], xmm3
0x1800156a0  mov     rdx, rax
0x1800156a3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x1800156aa  call    __delayLoadHelper2
0x1800156af  movdqa  xmm0, [rsp+68h+var_48]
0x1800156b5  movdqa  xmm1, [rsp+68h+var_38]
0x1800156bb  movdqa  xmm2, [rsp+68h+var_28]
0x1800156c1  movdqa  xmm3, [rsp+68h+var_18]
0x1800156c7  mov     rcx, [rsp+68h+arg_0]
0x1800156cc  mov     rdx, [rsp+68h+arg_8]
0x1800156d1  mov     r8, [rsp+68h+arg_10]
0x1800156d9  mov     r9, [rsp+68h+arg_18]
0x1800156e1  add     rsp, 68h
0x1800156e5  jmp     short $+2
0x1800156e7  jmp     rax
```
