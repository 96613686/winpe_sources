# __tailMerge_sspicli_dll

- ea: `0x18000fbe0`
- end: `0x18000fc59`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fc5f`
- `0x18000fc71`
- `0x18000fc83`
- `0x18000fd44`

## callees

- `0x18000d050`
- `0x18000fbe0`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000fbe0  mov     [rsp+arg_0], rcx
0x18000fbe5  mov     [rsp+arg_8], rdx
0x18000fbea  mov     [rsp+arg_10], r8
0x18000fbef  mov     [rsp+arg_18], r9
0x18000fbf4  sub     rsp, 68h
0x18000fbf8  movdqa  [rsp+68h+var_48], xmm0
0x18000fbfe  movdqa  [rsp+68h+var_38], xmm1
0x18000fc04  movdqa  [rsp+68h+var_28], xmm2
0x18000fc0a  movdqa  [rsp+68h+var_18], xmm3
0x18000fc10  mov     rdx, rax
0x18000fc13  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x18000fc1a  call    __delayLoadHelper2
0x18000fc1f  movdqa  xmm0, [rsp+68h+var_48]
0x18000fc25  movdqa  xmm1, [rsp+68h+var_38]
0x18000fc2b  movdqa  xmm2, [rsp+68h+var_28]
0x18000fc31  movdqa  xmm3, [rsp+68h+var_18]
0x18000fc37  mov     rcx, [rsp+68h+arg_0]
0x18000fc3c  mov     rdx, [rsp+68h+arg_8]
0x18000fc41  mov     r8, [rsp+68h+arg_10]
0x18000fc49  mov     r9, [rsp+68h+arg_18]
0x18000fc51  add     rsp, 68h
0x18000fc55  jmp     short $+2
0x18000fc57  jmp     rax
```
