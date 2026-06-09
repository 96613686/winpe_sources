# __tailMerge_api_ms_win_security_base_l1_1_0_dll

- ea: `0x18001586b`
- end: `0x1800158e4`
- name: `__tailMerge_api_ms_win_security_base_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800158ea`
- `0x1800158fc`
- `0x180015920`
- `0x180015c55`
- `0x180015cf2`
- `0x180015d04`

## callees

- `0x180014230`
- `0x18001586b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001586b  mov     [rsp+arg_0], rcx
0x180015870  mov     [rsp+arg_8], rdx
0x180015875  mov     [rsp+arg_10], r8
0x18001587a  mov     [rsp+arg_18], r9
0x18001587f  sub     rsp, 68h
0x180015883  movdqa  [rsp+68h+var_48], xmm0
0x180015889  movdqa  [rsp+68h+var_38], xmm1
0x18001588f  movdqa  [rsp+68h+var_28], xmm2
0x180015895  movdqa  [rsp+68h+var_18], xmm3
0x18001589b  mov     rdx, rax
0x18001589e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll
0x1800158a5  call    __delayLoadHelper2
0x1800158aa  movdqa  xmm0, [rsp+68h+var_48]
0x1800158b0  movdqa  xmm1, [rsp+68h+var_38]
0x1800158b6  movdqa  xmm2, [rsp+68h+var_28]
0x1800158bc  movdqa  xmm3, [rsp+68h+var_18]
0x1800158c2  mov     rcx, [rsp+68h+arg_0]
0x1800158c7  mov     rdx, [rsp+68h+arg_8]
0x1800158cc  mov     r8, [rsp+68h+arg_10]
0x1800158d4  mov     r9, [rsp+68h+arg_18]
0x1800158dc  add     rsp, 68h
0x1800158e0  jmp     short $+2
0x1800158e2  jmp     rax
```
