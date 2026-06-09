# __tailMerge_ole32_dll

- ea: `0x180001a90`
- end: `0x180001b09`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b0f`

## callees

- `0x180001a90`
- `0x180003010`

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
0x180001a90  mov     [rsp+arg_0], rcx
0x180001a95  mov     [rsp+arg_8], rdx
0x180001a9a  mov     [rsp+arg_10], r8
0x180001a9f  mov     [rsp+arg_18], r9
0x180001aa4  sub     rsp, 68h
0x180001aa8  movdqa  [rsp+68h+var_48], xmm0
0x180001aae  movdqa  [rsp+68h+var_38], xmm1
0x180001ab4  movdqa  [rsp+68h+var_28], xmm2
0x180001aba  movdqa  [rsp+68h+var_18], xmm3
0x180001ac0  mov     rdx, rax
0x180001ac3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180001aca  call    __delayLoadHelper2
0x180001acf  movdqa  xmm0, [rsp+68h+var_48]
0x180001ad5  movdqa  xmm1, [rsp+68h+var_38]
0x180001adb  movdqa  xmm2, [rsp+68h+var_28]
0x180001ae1  movdqa  xmm3, [rsp+68h+var_18]
0x180001ae7  mov     rcx, [rsp+68h+arg_0]
0x180001aec  mov     rdx, [rsp+68h+arg_8]
0x180001af1  mov     r8, [rsp+68h+arg_10]
0x180001af9  mov     r9, [rsp+68h+arg_18]
0x180001b01  add     rsp, 68h
0x180001b05  jmp     short $+2
0x180001b07  jmp     rax
```
