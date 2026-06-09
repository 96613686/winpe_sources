# __tailMerge_shell32_dll

- ea: `0x140010b10`
- end: `0x140010b89`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010b8f`
- `0x140010ba1`

## callees

- `0x1400083b0`
- `0x140010b10`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140010b10  mov     [rsp+arg_0], rcx
0x140010b15  mov     [rsp+arg_8], rdx
0x140010b1a  mov     [rsp+arg_10], r8
0x140010b1f  mov     [rsp+arg_18], r9
0x140010b24  sub     rsp, 68h
0x140010b28  movdqa  [rsp+68h+var_48], xmm0
0x140010b2e  movdqa  [rsp+68h+var_38], xmm1
0x140010b34  movdqa  [rsp+68h+var_28], xmm2
0x140010b3a  movdqa  [rsp+68h+var_18], xmm3
0x140010b40  mov     rdx, rax
0x140010b43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x140010b4a  call    __delayLoadHelper2
0x140010b4f  movdqa  xmm0, [rsp+68h+var_48]
0x140010b55  movdqa  xmm1, [rsp+68h+var_38]
0x140010b5b  movdqa  xmm2, [rsp+68h+var_28]
0x140010b61  movdqa  xmm3, [rsp+68h+var_18]
0x140010b67  mov     rcx, [rsp+68h+arg_0]
0x140010b6c  mov     rdx, [rsp+68h+arg_8]
0x140010b71  mov     r8, [rsp+68h+arg_10]
0x140010b79  mov     r9, [rsp+68h+arg_18]
0x140010b81  add     rsp, 68h
0x140010b85  jmp     short $+2
0x140010b87  jmp     rax
```
