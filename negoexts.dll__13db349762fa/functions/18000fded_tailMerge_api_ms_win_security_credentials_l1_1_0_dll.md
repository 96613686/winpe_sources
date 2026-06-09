# __tailMerge_api_ms_win_security_credentials_l1_1_0_dll

- ea: `0x18000fded`
- end: `0x18000fe66`
- name: `__tailMerge_api_ms_win_security_credentials_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe6c`
- `0x18000fe7e`
- `0x18000fe90`
- `0x18000fea2`
- `0x18000feb4`

## callees

- `0x18000d050`
- `0x18000fded`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_credentials_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_credentials_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000fded  mov     [rsp+arg_0], rcx
0x18000fdf2  mov     [rsp+arg_8], rdx
0x18000fdf7  mov     [rsp+arg_10], r8
0x18000fdfc  mov     [rsp+arg_18], r9
0x18000fe01  sub     rsp, 68h
0x18000fe05  movdqa  [rsp+68h+var_48], xmm0
0x18000fe0b  movdqa  [rsp+68h+var_38], xmm1
0x18000fe11  movdqa  [rsp+68h+var_28], xmm2
0x18000fe17  movdqa  [rsp+68h+var_18], xmm3
0x18000fe1d  mov     rdx, rax
0x18000fe20  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_credentials_l1_1_0_dll
0x18000fe27  call    __delayLoadHelper2
0x18000fe2c  movdqa  xmm0, [rsp+68h+var_48]
0x18000fe32  movdqa  xmm1, [rsp+68h+var_38]
0x18000fe38  movdqa  xmm2, [rsp+68h+var_28]
0x18000fe3e  movdqa  xmm3, [rsp+68h+var_18]
0x18000fe44  mov     rcx, [rsp+68h+arg_0]
0x18000fe49  mov     rdx, [rsp+68h+arg_8]
0x18000fe4e  mov     r8, [rsp+68h+arg_10]
0x18000fe56  mov     r9, [rsp+68h+arg_18]
0x18000fe5e  add     rsp, 68h
0x18000fe62  jmp     short $+2
0x18000fe64  jmp     rax
```
