# __tailMerge_cryptsp_dll

- ea: `0x180001ea5`
- end: `0x180001f1e`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f24`
- `0x180001f36`
- `0x180001f48`
- `0x180001f5a`
- `0x180001f6c`
- `0x180001f7e`
- `0x180001f90`
- `0x180001fa2`

## callees

- `0x180001ea5`
- `0x18000d7b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001ea5  mov     [rsp+arg_0], rcx
0x180001eaa  mov     [rsp+arg_8], rdx
0x180001eaf  mov     [rsp+arg_10], r8
0x180001eb4  mov     [rsp+arg_18], r9
0x180001eb9  sub     rsp, 68h
0x180001ebd  movdqa  [rsp+68h+var_48], xmm0
0x180001ec3  movdqa  [rsp+68h+var_38], xmm1
0x180001ec9  movdqa  [rsp+68h+var_28], xmm2
0x180001ecf  movdqa  [rsp+68h+var_18], xmm3
0x180001ed5  mov     rdx, rax
0x180001ed8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x180001edf  call    __delayLoadHelper2
0x180001ee4  movdqa  xmm0, [rsp+68h+var_48]
0x180001eea  movdqa  xmm1, [rsp+68h+var_38]
0x180001ef0  movdqa  xmm2, [rsp+68h+var_28]
0x180001ef6  movdqa  xmm3, [rsp+68h+var_18]
0x180001efc  mov     rcx, [rsp+68h+arg_0]
0x180001f01  mov     rdx, [rsp+68h+arg_8]
0x180001f06  mov     r8, [rsp+68h+arg_10]
0x180001f0e  mov     r9, [rsp+68h+arg_18]
0x180001f16  add     rsp, 68h
0x180001f1a  jmp     short $+2
0x180001f1c  jmp     rax
```
