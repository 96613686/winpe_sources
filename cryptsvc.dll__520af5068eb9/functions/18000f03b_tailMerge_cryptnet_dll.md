# __tailMerge_cryptnet_dll

- ea: `0x18000f03b`
- end: `0x18000f0b4`
- name: `__tailMerge_cryptnet_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f0ba`
- `0x18000f0cc`
- `0x18000f0de`

## callees

- `0x18000bd20`
- `0x18000f03b`

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
0x18000f03b  mov     [rsp+arg_0], rcx
0x18000f040  mov     [rsp+arg_8], rdx
0x18000f045  mov     [rsp+arg_10], r8
0x18000f04a  mov     [rsp+arg_18], r9
0x18000f04f  sub     rsp, 68h
0x18000f053  movdqa  [rsp+68h+var_48], xmm0
0x18000f059  movdqa  [rsp+68h+var_38], xmm1
0x18000f05f  movdqa  [rsp+68h+var_28], xmm2
0x18000f065  movdqa  [rsp+68h+var_18], xmm3
0x18000f06b  mov     rdx, rax
0x18000f06e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptnet_dll
0x18000f075  call    __delayLoadHelper2
0x18000f07a  movdqa  xmm0, [rsp+68h+var_48]
0x18000f080  movdqa  xmm1, [rsp+68h+var_38]
0x18000f086  movdqa  xmm2, [rsp+68h+var_28]
0x18000f08c  movdqa  xmm3, [rsp+68h+var_18]
0x18000f092  mov     rcx, [rsp+68h+arg_0]
0x18000f097  mov     rdx, [rsp+68h+arg_8]
0x18000f09c  mov     r8, [rsp+68h+arg_10]
0x18000f0a4  mov     r9, [rsp+68h+arg_18]
0x18000f0ac  add     rsp, 68h
0x18000f0b0  jmp     short $+2
0x18000f0b2  jmp     rax
```
