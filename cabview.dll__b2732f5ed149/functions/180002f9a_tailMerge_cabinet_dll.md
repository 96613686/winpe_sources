# __tailMerge_cabinet_dll

- ea: `0x180002f9a`
- end: `0x180003013`
- name: `__tailMerge_cabinet_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003019`
- `0x18000302b`
- `0x18000303d`

## callees

- `0x180002f9a`
- `0x180012940`

## pseudocode

```c
__int64 __fastcall _tailMerge_cabinet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cabinet_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002f9a  mov     [rsp+arg_0], rcx
0x180002f9f  mov     [rsp+arg_8], rdx
0x180002fa4  mov     [rsp+arg_10], r8
0x180002fa9  mov     [rsp+arg_18], r9
0x180002fae  sub     rsp, 68h
0x180002fb2  movdqa  [rsp+68h+var_48], xmm0
0x180002fb8  movdqa  [rsp+68h+var_38], xmm1
0x180002fbe  movdqa  [rsp+68h+var_28], xmm2
0x180002fc4  movdqa  [rsp+68h+var_18], xmm3
0x180002fca  mov     rdx, rax
0x180002fcd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cabinet_dll
0x180002fd4  call    __delayLoadHelper2
0x180002fd9  movdqa  xmm0, [rsp+68h+var_48]
0x180002fdf  movdqa  xmm1, [rsp+68h+var_38]
0x180002fe5  movdqa  xmm2, [rsp+68h+var_28]
0x180002feb  movdqa  xmm3, [rsp+68h+var_18]
0x180002ff1  mov     rcx, [rsp+68h+arg_0]
0x180002ff6  mov     rdx, [rsp+68h+arg_8]
0x180002ffb  mov     r8, [rsp+68h+arg_10]
0x180003003  mov     r9, [rsp+68h+arg_18]
0x18000300b  add     rsp, 68h
0x18000300f  jmp     short $+2
0x180003011  jmp     rax
```
