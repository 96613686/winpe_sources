# __tailMerge_cryptnet_dll

- ea: `0x180005f70`
- end: `0x180005fe9`
- name: `__tailMerge_cryptnet_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005fef`

## callees

- `0x1800046b0`
- `0x180005f70`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptnet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_cryptnet_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005f70  mov     [rsp+arg_0], rcx
0x180005f75  mov     [rsp+arg_8], rdx
0x180005f7a  mov     [rsp+arg_10], r8
0x180005f7f  mov     [rsp+arg_18], r9
0x180005f84  sub     rsp, 68h
0x180005f88  movdqa  [rsp+68h+var_48], xmm0
0x180005f8e  movdqa  [rsp+68h+var_38], xmm1
0x180005f94  movdqa  [rsp+68h+var_28], xmm2
0x180005f9a  movdqa  [rsp+68h+var_18], xmm3
0x180005fa0  mov     rdx, rax
0x180005fa3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptnet_dll
0x180005faa  call    __delayLoadHelper2
0x180005faf  movdqa  xmm0, [rsp+68h+var_48]
0x180005fb5  movdqa  xmm1, [rsp+68h+var_38]
0x180005fbb  movdqa  xmm2, [rsp+68h+var_28]
0x180005fc1  movdqa  xmm3, [rsp+68h+var_18]
0x180005fc7  mov     rcx, [rsp+68h+arg_0]
0x180005fcc  mov     rdx, [rsp+68h+arg_8]
0x180005fd1  mov     r8, [rsp+68h+arg_10]
0x180005fd9  mov     r9, [rsp+68h+arg_18]
0x180005fe1  add     rsp, 68h
0x180005fe5  jmp     short $+2
0x180005fe7  jmp     rax
```
