# __tailMerge_ole32_dll

- ea: `0x180001f90`
- end: `0x180002009`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000200f`
- `0x180002021`
- `0x180002033`
- `0x180002045`
- `0x180002057`
- `0x180002069`
- `0x18000207b`
- `0x18000208d`

## callees

- `0x180001f90`
- `0x18000a390`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f90  mov     [rsp+arg_0], rcx
0x180001f95  mov     [rsp+arg_8], rdx
0x180001f9a  mov     [rsp+arg_10], r8
0x180001f9f  mov     [rsp+arg_18], r9
0x180001fa4  sub     rsp, 68h
0x180001fa8  movdqa  [rsp+68h+var_48], xmm0
0x180001fae  movdqa  [rsp+68h+var_38], xmm1
0x180001fb4  movdqa  [rsp+68h+var_28], xmm2
0x180001fba  movdqa  [rsp+68h+var_18], xmm3
0x180001fc0  mov     rdx, rax
0x180001fc3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180001fca  call    __delayLoadHelper2
0x180001fcf  movdqa  xmm0, [rsp+68h+var_48]
0x180001fd5  movdqa  xmm1, [rsp+68h+var_38]
0x180001fdb  movdqa  xmm2, [rsp+68h+var_28]
0x180001fe1  movdqa  xmm3, [rsp+68h+var_18]
0x180001fe7  mov     rcx, [rsp+68h+arg_0]
0x180001fec  mov     rdx, [rsp+68h+arg_8]
0x180001ff1  mov     r8, [rsp+68h+arg_10]
0x180001ff9  mov     r9, [rsp+68h+arg_18]
0x180002001  add     rsp, 68h
0x180002005  jmp     short $+2
0x180002007  jmp     rax
```
