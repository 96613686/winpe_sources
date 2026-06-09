# __tailMerge_srvcli_dll

- ea: `0x180002631`
- end: `0x1800026aa`
- name: `__tailMerge_srvcli_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800026b0`

## callees

- `0x180002631`
- `0x180007f20`

## pseudocode

```c
__int64 __fastcall _tailMerge_srvcli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_srvcli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002631  mov     [rsp+arg_0], rcx
0x180002636  mov     [rsp+arg_8], rdx
0x18000263b  mov     [rsp+arg_10], r8
0x180002640  mov     [rsp+arg_18], r9
0x180002645  sub     rsp, 68h
0x180002649  movdqa  [rsp+68h+var_48], xmm0
0x18000264f  movdqa  [rsp+68h+var_38], xmm1
0x180002655  movdqa  [rsp+68h+var_28], xmm2
0x18000265b  movdqa  [rsp+68h+var_18], xmm3
0x180002661  mov     rdx, rax
0x180002664  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_srvcli_dll
0x18000266b  call    __delayLoadHelper2
0x180002670  movdqa  xmm0, [rsp+68h+var_48]
0x180002676  movdqa  xmm1, [rsp+68h+var_38]
0x18000267c  movdqa  xmm2, [rsp+68h+var_28]
0x180002682  movdqa  xmm3, [rsp+68h+var_18]
0x180002688  mov     rcx, [rsp+68h+arg_0]
0x18000268d  mov     rdx, [rsp+68h+arg_8]
0x180002692  mov     r8, [rsp+68h+arg_10]
0x18000269a  mov     r9, [rsp+68h+arg_18]
0x1800026a2  add     rsp, 68h
0x1800026a6  jmp     short $+2
0x1800026a8  jmp     rax
```
