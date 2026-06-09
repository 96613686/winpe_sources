# __tailMerge_dsreg_dll

- ea: `0x180002b20`
- end: `0x180002b99`
- name: `__tailMerge_dsreg_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b9f`
- `0x180002bb1`

## callees

- `0x180002b20`
- `0x18002b720`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsreg_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dsreg_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_0], rcx
0x180002b25  mov     [rsp+arg_8], rdx
0x180002b2a  mov     [rsp+arg_10], r8
0x180002b2f  mov     [rsp+arg_18], r9
0x180002b34  sub     rsp, 68h
0x180002b38  movdqa  [rsp+68h+var_48], xmm0
0x180002b3e  movdqa  [rsp+68h+var_38], xmm1
0x180002b44  movdqa  [rsp+68h+var_28], xmm2
0x180002b4a  movdqa  [rsp+68h+var_18], xmm3
0x180002b50  mov     rdx, rax
0x180002b53  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsreg_dll
0x180002b5a  call    __delayLoadHelper2
0x180002b5f  movdqa  xmm0, [rsp+68h+var_48]
0x180002b65  movdqa  xmm1, [rsp+68h+var_38]
0x180002b6b  movdqa  xmm2, [rsp+68h+var_28]
0x180002b71  movdqa  xmm3, [rsp+68h+var_18]
0x180002b77  mov     rcx, [rsp+68h+arg_0]
0x180002b7c  mov     rdx, [rsp+68h+arg_8]
0x180002b81  mov     r8, [rsp+68h+arg_10]
0x180002b89  mov     r9, [rsp+68h+arg_18]
0x180002b91  add     rsp, 68h
0x180002b95  jmp     short $+2
0x180002b97  jmp     rax
```
