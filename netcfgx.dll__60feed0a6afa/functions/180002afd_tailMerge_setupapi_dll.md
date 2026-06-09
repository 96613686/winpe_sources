# __tailMerge_setupapi_dll

- ea: `0x180002afd`
- end: `0x180002b76`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180002cb6`
- `0x180002cc8`
- `0x180002cda`
- `0x180002cec`
- `0x180002cfe`
- `0x180002d10`
- `0x180002d22`
- `0x180002d34`
- `0x180002d46`
- `0x180002d58`
- `0x180002d6a`
- `0x180002d7c`
- `0x180002d8e`
- `0x180002da0`

## callees

- `0x180002afd`
- `0x180011dd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_setupapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002afd  mov     [rsp+arg_0], rcx
0x180002b02  mov     [rsp+arg_8], rdx
0x180002b07  mov     [rsp+arg_10], r8
0x180002b0c  mov     [rsp+arg_18], r9
0x180002b11  sub     rsp, 68h
0x180002b15  movdqa  [rsp+68h+var_48], xmm0
0x180002b1b  movdqa  [rsp+68h+var_38], xmm1
0x180002b21  movdqa  [rsp+68h+var_28], xmm2
0x180002b27  movdqa  [rsp+68h+var_18], xmm3
0x180002b2d  mov     rdx, rax
0x180002b30  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x180002b37  call    __delayLoadHelper2
0x180002b3c  movdqa  xmm0, [rsp+68h+var_48]
0x180002b42  movdqa  xmm1, [rsp+68h+var_38]
0x180002b48  movdqa  xmm2, [rsp+68h+var_28]
0x180002b4e  movdqa  xmm3, [rsp+68h+var_18]
0x180002b54  mov     rcx, [rsp+68h+arg_0]
0x180002b59  mov     rdx, [rsp+68h+arg_8]
0x180002b5e  mov     r8, [rsp+68h+arg_10]
0x180002b66  mov     r9, [rsp+68h+arg_18]
0x180002b6e  add     rsp, 68h
0x180002b72  jmp     short $+2
0x180002b74  jmp     rax
```
