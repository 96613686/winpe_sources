# __tailMerge_credui_dll

- ea: `0x140010d35`
- end: `0x140010dae`
- name: `__tailMerge_credui_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010db4`
- `0x140010dc6`

## callees

- `0x1400083b0`
- `0x140010d35`

## pseudocode

```c
__int64 __fastcall _tailMerge_credui_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_credui_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140010d35  mov     [rsp+arg_0], rcx
0x140010d3a  mov     [rsp+arg_8], rdx
0x140010d3f  mov     [rsp+arg_10], r8
0x140010d44  mov     [rsp+arg_18], r9
0x140010d49  sub     rsp, 68h
0x140010d4d  movdqa  [rsp+68h+var_48], xmm0
0x140010d53  movdqa  [rsp+68h+var_38], xmm1
0x140010d59  movdqa  [rsp+68h+var_28], xmm2
0x140010d5f  movdqa  [rsp+68h+var_18], xmm3
0x140010d65  mov     rdx, rax
0x140010d68  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_credui_dll
0x140010d6f  call    __delayLoadHelper2
0x140010d74  movdqa  xmm0, [rsp+68h+var_48]
0x140010d7a  movdqa  xmm1, [rsp+68h+var_38]
0x140010d80  movdqa  xmm2, [rsp+68h+var_28]
0x140010d86  movdqa  xmm3, [rsp+68h+var_18]
0x140010d8c  mov     rcx, [rsp+68h+arg_0]
0x140010d91  mov     rdx, [rsp+68h+arg_8]
0x140010d96  mov     r8, [rsp+68h+arg_10]
0x140010d9e  mov     r9, [rsp+68h+arg_18]
0x140010da6  add     rsp, 68h
0x140010daa  jmp     short $+2
0x140010dac  jmp     rax
```
