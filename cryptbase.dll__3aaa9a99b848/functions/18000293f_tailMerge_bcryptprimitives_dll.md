# __tailMerge_bcryptprimitives_dll

- ea: `0x18000293f`
- end: `0x1800029b8`
- name: `__tailMerge_bcryptprimitives_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800029be`

## callees

- `0x1800017d0`
- `0x18000293f`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcryptprimitives_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcryptprimitives_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000293f  mov     [rsp+arg_0], rcx
0x180002944  mov     [rsp+arg_8], rdx
0x180002949  mov     [rsp+arg_10], r8
0x18000294e  mov     [rsp+arg_18], r9
0x180002953  sub     rsp, 68h
0x180002957  movdqa  [rsp+68h+var_48], xmm0
0x18000295d  movdqa  [rsp+68h+var_38], xmm1
0x180002963  movdqa  [rsp+68h+var_28], xmm2
0x180002969  movdqa  [rsp+68h+var_18], xmm3
0x18000296f  mov     rdx, rax
0x180002972  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcryptprimitives_dll
0x180002979  call    __delayLoadHelper2
0x18000297e  movdqa  xmm0, [rsp+68h+var_48]
0x180002984  movdqa  xmm1, [rsp+68h+var_38]
0x18000298a  movdqa  xmm2, [rsp+68h+var_28]
0x180002990  movdqa  xmm3, [rsp+68h+var_18]
0x180002996  mov     rcx, [rsp+68h+arg_0]
0x18000299b  mov     rdx, [rsp+68h+arg_8]
0x1800029a0  mov     r8, [rsp+68h+arg_10]
0x1800029a8  mov     r9, [rsp+68h+arg_18]
0x1800029b0  add     rsp, 68h
0x1800029b4  jmp     short $+2
0x1800029b6  jmp     rax
```
