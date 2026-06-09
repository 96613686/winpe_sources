# __tailMerge_sspicli_dll

- ea: `0x180008382`
- end: `0x1800083fb`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008401`

## callees

- `0x180008382`
- `0x18001e2e0`

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
0x180008382  mov     [rsp+arg_0], rcx
0x180008387  mov     [rsp+arg_8], rdx
0x18000838c  mov     [rsp+arg_10], r8
0x180008391  mov     [rsp+arg_18], r9
0x180008396  sub     rsp, 68h
0x18000839a  movdqa  [rsp+68h+var_48], xmm0
0x1800083a0  movdqa  [rsp+68h+var_38], xmm1
0x1800083a6  movdqa  [rsp+68h+var_28], xmm2
0x1800083ac  movdqa  [rsp+68h+var_18], xmm3
0x1800083b2  mov     rdx, rax
0x1800083b5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x1800083bc  call    __delayLoadHelper2
0x1800083c1  movdqa  xmm0, [rsp+68h+var_48]
0x1800083c7  movdqa  xmm1, [rsp+68h+var_38]
0x1800083cd  movdqa  xmm2, [rsp+68h+var_28]
0x1800083d3  movdqa  xmm3, [rsp+68h+var_18]
0x1800083d9  mov     rcx, [rsp+68h+arg_0]
0x1800083de  mov     rdx, [rsp+68h+arg_8]
0x1800083e3  mov     r8, [rsp+68h+arg_10]
0x1800083eb  mov     r9, [rsp+68h+arg_18]
0x1800083f3  add     rsp, 68h
0x1800083f7  jmp     short $+2
0x1800083f9  jmp     rax
```
