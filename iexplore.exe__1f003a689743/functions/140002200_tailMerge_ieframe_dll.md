# __tailMerge_ieframe_dll

- ea: `0x140002200`
- end: `0x140002279`
- name: `__tailMerge_ieframe_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000227f`
- `0x140002291`
- `0x1400022a3`
- `0x1400022b5`

## callees

- `0x140002200`
- `0x1400058b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ieframe_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ieframe_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002200  mov     [rsp+arg_0], rcx
0x140002205  mov     [rsp+arg_8], rdx
0x14000220a  mov     [rsp+arg_10], r8
0x14000220f  mov     [rsp+arg_18], r9
0x140002214  sub     rsp, 68h
0x140002218  movdqa  [rsp+68h+var_48], xmm0
0x14000221e  movdqa  [rsp+68h+var_38], xmm1
0x140002224  movdqa  [rsp+68h+var_28], xmm2
0x14000222a  movdqa  [rsp+68h+var_18], xmm3
0x140002230  mov     rdx, rax
0x140002233  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ieframe_dll
0x14000223a  call    __delayLoadHelper2
0x14000223f  movdqa  xmm0, [rsp+68h+var_48]
0x140002245  movdqa  xmm1, [rsp+68h+var_38]
0x14000224b  movdqa  xmm2, [rsp+68h+var_28]
0x140002251  movdqa  xmm3, [rsp+68h+var_18]
0x140002257  mov     rcx, [rsp+68h+arg_0]
0x14000225c  mov     rdx, [rsp+68h+arg_8]
0x140002261  mov     r8, [rsp+68h+arg_10]
0x140002269  mov     r9, [rsp+68h+arg_18]
0x140002271  add     rsp, 68h
0x140002275  jmp     short $+2
0x140002277  jmp     rax
```
