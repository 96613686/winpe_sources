# __tailMerge_rpcrt4_dll

- ea: `0x180010530`
- end: `0x1800105a9`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800105af`

## callees

- `0x18000aac0`
- `0x180010530`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010530  mov     [rsp+arg_0], rcx
0x180010535  mov     [rsp+arg_8], rdx
0x18001053a  mov     [rsp+arg_10], r8
0x18001053f  mov     [rsp+arg_18], r9
0x180010544  sub     rsp, 68h
0x180010548  movdqa  [rsp+68h+var_48], xmm0
0x18001054e  movdqa  [rsp+68h+var_38], xmm1
0x180010554  movdqa  [rsp+68h+var_28], xmm2
0x18001055a  movdqa  [rsp+68h+var_18], xmm3
0x180010560  mov     rdx, rax
0x180010563  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18001056a  call    __delayLoadHelper2
0x18001056f  movdqa  xmm0, [rsp+68h+var_48]
0x180010575  movdqa  xmm1, [rsp+68h+var_38]
0x18001057b  movdqa  xmm2, [rsp+68h+var_28]
0x180010581  movdqa  xmm3, [rsp+68h+var_18]
0x180010587  mov     rcx, [rsp+68h+arg_0]
0x18001058c  mov     rdx, [rsp+68h+arg_8]
0x180010591  mov     r8, [rsp+68h+arg_10]
0x180010599  mov     r9, [rsp+68h+arg_18]
0x1800105a1  add     rsp, 68h
0x1800105a5  jmp     short $+2
0x1800105a7  jmp     rax
```
