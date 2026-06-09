# __tailMerge_ws2_32_dll

- ea: `0x18000a950`
- end: `0x18000a9c9`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a9cf`
- `0x18000aa6c`
- `0x18000aa7e`
- `0x18000aa90`
- `0x18000aaa2`
- `0x18000aab4`

## callees

- `0x180009170`
- `0x18000a950`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a950  mov     [rsp+arg_0], rcx
0x18000a955  mov     [rsp+arg_8], rdx
0x18000a95a  mov     [rsp+arg_10], r8
0x18000a95f  mov     [rsp+arg_18], r9
0x18000a964  sub     rsp, 68h
0x18000a968  movdqa  [rsp+68h+var_48], xmm0
0x18000a96e  movdqa  [rsp+68h+var_38], xmm1
0x18000a974  movdqa  [rsp+68h+var_28], xmm2
0x18000a97a  movdqa  [rsp+68h+var_18], xmm3
0x18000a980  mov     rdx, rax
0x18000a983  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18000a98a  call    __delayLoadHelper2
0x18000a98f  movdqa  xmm0, [rsp+68h+var_48]
0x18000a995  movdqa  xmm1, [rsp+68h+var_38]
0x18000a99b  movdqa  xmm2, [rsp+68h+var_28]
0x18000a9a1  movdqa  xmm3, [rsp+68h+var_18]
0x18000a9a7  mov     rcx, [rsp+68h+arg_0]
0x18000a9ac  mov     rdx, [rsp+68h+arg_8]
0x18000a9b1  mov     r8, [rsp+68h+arg_10]
0x18000a9b9  mov     r9, [rsp+68h+arg_18]
0x18000a9c1  add     rsp, 68h
0x18000a9c5  jmp     short $+2
0x18000a9c7  jmp     rax
```
