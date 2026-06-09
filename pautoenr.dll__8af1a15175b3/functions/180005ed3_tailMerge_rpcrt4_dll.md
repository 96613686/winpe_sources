# __tailMerge_rpcrt4_dll

- ea: `0x180005ed3`
- end: `0x180005f4c`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005f52`
- `0x180006013`

## callees

- `0x1800046b0`
- `0x180005ed3`

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
0x180005ed3  mov     [rsp+arg_0], rcx
0x180005ed8  mov     [rsp+arg_8], rdx
0x180005edd  mov     [rsp+arg_10], r8
0x180005ee2  mov     [rsp+arg_18], r9
0x180005ee7  sub     rsp, 68h
0x180005eeb  movdqa  [rsp+68h+var_48], xmm0
0x180005ef1  movdqa  [rsp+68h+var_38], xmm1
0x180005ef7  movdqa  [rsp+68h+var_28], xmm2
0x180005efd  movdqa  [rsp+68h+var_18], xmm3
0x180005f03  mov     rdx, rax
0x180005f06  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180005f0d  call    __delayLoadHelper2
0x180005f12  movdqa  xmm0, [rsp+68h+var_48]
0x180005f18  movdqa  xmm1, [rsp+68h+var_38]
0x180005f1e  movdqa  xmm2, [rsp+68h+var_28]
0x180005f24  movdqa  xmm3, [rsp+68h+var_18]
0x180005f2a  mov     rcx, [rsp+68h+arg_0]
0x180005f2f  mov     rdx, [rsp+68h+arg_8]
0x180005f34  mov     r8, [rsp+68h+arg_10]
0x180005f3c  mov     r9, [rsp+68h+arg_18]
0x180005f44  add     rsp, 68h
0x180005f48  jmp     short $+2
0x180005f4a  jmp     rax
```
