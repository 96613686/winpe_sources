# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x1800105bb`
- end: `0x180010634`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001063a`

## callees

- `0x18000aac0`
- `0x1800105bb`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800105bb  mov     [rsp+arg_0], rcx
0x1800105c0  mov     [rsp+arg_8], rdx
0x1800105c5  mov     [rsp+arg_10], r8
0x1800105ca  mov     [rsp+arg_18], r9
0x1800105cf  sub     rsp, 68h
0x1800105d3  movdqa  [rsp+68h+var_48], xmm0
0x1800105d9  movdqa  [rsp+68h+var_38], xmm1
0x1800105df  movdqa  [rsp+68h+var_28], xmm2
0x1800105e5  movdqa  [rsp+68h+var_18], xmm3
0x1800105eb  mov     rdx, rax
0x1800105ee  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x1800105f5  call    __delayLoadHelper2
0x1800105fa  movdqa  xmm0, [rsp+68h+var_48]
0x180010600  movdqa  xmm1, [rsp+68h+var_38]
0x180010606  movdqa  xmm2, [rsp+68h+var_28]
0x18001060c  movdqa  xmm3, [rsp+68h+var_18]
0x180010612  mov     rcx, [rsp+68h+arg_0]
0x180010617  mov     rdx, [rsp+68h+arg_8]
0x18001061c  mov     r8, [rsp+68h+arg_10]
0x180010624  mov     r9, [rsp+68h+arg_18]
0x18001062c  add     rsp, 68h
0x180010630  jmp     short $+2
0x180010632  jmp     rax
```
