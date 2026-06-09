# __tailMerge_devobj_dll

- ea: `0x180001eb0`
- end: `0x180001f29`
- name: `__tailMerge_devobj_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f2f`
- `0x180001f41`
- `0x180001f53`
- `0x180001f65`
- `0x180001f77`

## callees

- `0x180001eb0`
- `0x180008330`

## pseudocode

```c
__int64 __fastcall _tailMerge_devobj_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_devobj_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp+arg_0], rcx
0x180001eb5  mov     [rsp+arg_8], rdx
0x180001eba  mov     [rsp+arg_10], r8
0x180001ebf  mov     [rsp+arg_18], r9
0x180001ec4  sub     rsp, 68h
0x180001ec8  movdqa  [rsp+68h+var_48], xmm0
0x180001ece  movdqa  [rsp+68h+var_38], xmm1
0x180001ed4  movdqa  [rsp+68h+var_28], xmm2
0x180001eda  movdqa  [rsp+68h+var_18], xmm3
0x180001ee0  mov     rdx, rax
0x180001ee3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_devobj_dll
0x180001eea  call    __delayLoadHelper2
0x180001eef  movdqa  xmm0, [rsp+68h+var_48]
0x180001ef5  movdqa  xmm1, [rsp+68h+var_38]
0x180001efb  movdqa  xmm2, [rsp+68h+var_28]
0x180001f01  movdqa  xmm3, [rsp+68h+var_18]
0x180001f07  mov     rcx, [rsp+68h+arg_0]
0x180001f0c  mov     rdx, [rsp+68h+arg_8]
0x180001f11  mov     r8, [rsp+68h+arg_10]
0x180001f19  mov     r9, [rsp+68h+arg_18]
0x180001f21  add     rsp, 68h
0x180001f25  jmp     short $+2
0x180001f27  jmp     rax
```
