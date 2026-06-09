# __tailMerge_userenv_dll

- ea: `0x180001e9e`
- end: `0x180001f17`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f1d`
- `0x180001f53`

## callees

- `0x180001e9e`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e9e  mov     [rsp+arg_0], rcx
0x180001ea3  mov     [rsp+arg_8], rdx
0x180001ea8  mov     [rsp+arg_10], r8
0x180001ead  mov     [rsp+arg_18], r9
0x180001eb2  sub     rsp, 68h
0x180001eb6  movdqa  [rsp+68h+var_48], xmm0
0x180001ebc  movdqa  [rsp+68h+var_38], xmm1
0x180001ec2  movdqa  [rsp+68h+var_28], xmm2
0x180001ec8  movdqa  [rsp+68h+var_18], xmm3
0x180001ece  mov     rdx, rax
0x180001ed1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180001ed8  call    __delayLoadHelper2
0x180001edd  movdqa  xmm0, [rsp+68h+var_48]
0x180001ee3  movdqa  xmm1, [rsp+68h+var_38]
0x180001ee9  movdqa  xmm2, [rsp+68h+var_28]
0x180001eef  movdqa  xmm3, [rsp+68h+var_18]
0x180001ef5  mov     rcx, [rsp+68h+arg_0]
0x180001efa  mov     rdx, [rsp+68h+arg_8]
0x180001eff  mov     r8, [rsp+68h+arg_10]
0x180001f07  mov     r9, [rsp+68h+arg_18]
0x180001f0f  add     rsp, 68h
0x180001f13  jmp     short $+2
0x180001f15  jmp     rax
```
