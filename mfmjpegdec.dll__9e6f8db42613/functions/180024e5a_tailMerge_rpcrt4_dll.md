# __tailMerge_rpcrt4_dll

- ea: `0x180024e5a`
- end: `0x180024ed3`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024ed9`
- `0x180024eeb`
- `0x180024efd`
- `0x180024f0f`
- `0x180024f21`

## callees

- `0x180024e5a`
- `0x18006eee0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180024e5a  mov     [rsp+arg_0], rcx
0x180024e5f  mov     [rsp+arg_8], rdx
0x180024e64  mov     [rsp+arg_10], r8
0x180024e69  mov     [rsp+arg_18], r9
0x180024e6e  sub     rsp, 68h
0x180024e72  movdqa  [rsp+68h+var_48], xmm0
0x180024e78  movdqa  [rsp+68h+var_38], xmm1
0x180024e7e  movdqa  [rsp+68h+var_28], xmm2
0x180024e84  movdqa  [rsp+68h+var_18], xmm3
0x180024e8a  mov     rdx, rax
0x180024e8d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180024e94  call    __delayLoadHelper2
0x180024e99  movdqa  xmm0, [rsp+68h+var_48]
0x180024e9f  movdqa  xmm1, [rsp+68h+var_38]
0x180024ea5  movdqa  xmm2, [rsp+68h+var_28]
0x180024eab  movdqa  xmm3, [rsp+68h+var_18]
0x180024eb1  mov     rcx, [rsp+68h+arg_0]
0x180024eb6  mov     rdx, [rsp+68h+arg_8]
0x180024ebb  mov     r8, [rsp+68h+arg_10]
0x180024ec3  mov     r9, [rsp+68h+arg_18]
0x180024ecb  add     rsp, 68h
0x180024ecf  jmp     short $+2
0x180024ed1  jmp     rax
```
