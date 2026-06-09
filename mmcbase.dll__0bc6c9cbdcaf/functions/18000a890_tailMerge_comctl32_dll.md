# __tailMerge_comctl32_dll

- ea: `0x18000a890`
- end: `0x18000a909`
- name: `__tailMerge_comctl32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a90f`
- `0x18000a921`

## callees

- `0x180006bb0`
- `0x18000a890`

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
0x18000a890  mov     [rsp+arg_0], rcx
0x18000a895  mov     [rsp+arg_8], rdx
0x18000a89a  mov     [rsp+arg_10], r8
0x18000a89f  mov     [rsp+arg_18], r9
0x18000a8a4  sub     rsp, 68h
0x18000a8a8  movdqa  [rsp+68h+var_48], xmm0
0x18000a8ae  movdqa  [rsp+68h+var_38], xmm1
0x18000a8b4  movdqa  [rsp+68h+var_28], xmm2
0x18000a8ba  movdqa  [rsp+68h+var_18], xmm3
0x18000a8c0  mov     rdx, rax
0x18000a8c3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comctl32_dll
0x18000a8ca  call    __delayLoadHelper2
0x18000a8cf  movdqa  xmm0, [rsp+68h+var_48]
0x18000a8d5  movdqa  xmm1, [rsp+68h+var_38]
0x18000a8db  movdqa  xmm2, [rsp+68h+var_28]
0x18000a8e1  movdqa  xmm3, [rsp+68h+var_18]
0x18000a8e7  mov     rcx, [rsp+68h+arg_0]
0x18000a8ec  mov     rdx, [rsp+68h+arg_8]
0x18000a8f1  mov     r8, [rsp+68h+arg_10]
0x18000a8f9  mov     r9, [rsp+68h+arg_18]
0x18000a901  add     rsp, 68h
0x18000a905  jmp     short $+2
0x18000a907  jmp     rax
```
