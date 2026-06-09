# __tailMerge_oleaut32_dll

- ea: `0x1400021c2`
- end: `0x14000223b`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002241`

## callees

- `0x1400021c2`
- `0x140008ee0`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400021c2  mov     [rsp+arg_0], rcx
0x1400021c7  mov     [rsp+arg_8], rdx
0x1400021cc  mov     [rsp+arg_10], r8
0x1400021d1  mov     [rsp+arg_18], r9
0x1400021d6  sub     rsp, 68h
0x1400021da  movdqa  [rsp+68h+var_48], xmm0
0x1400021e0  movdqa  [rsp+68h+var_38], xmm1
0x1400021e6  movdqa  [rsp+68h+var_28], xmm2
0x1400021ec  movdqa  [rsp+68h+var_18], xmm3
0x1400021f2  mov     rdx, rax
0x1400021f5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x1400021fc  call    __delayLoadHelper2
0x140002201  movdqa  xmm0, [rsp+68h+var_48]
0x140002207  movdqa  xmm1, [rsp+68h+var_38]
0x14000220d  movdqa  xmm2, [rsp+68h+var_28]
0x140002213  movdqa  xmm3, [rsp+68h+var_18]
0x140002219  mov     rcx, [rsp+68h+arg_0]
0x14000221e  mov     rdx, [rsp+68h+arg_8]
0x140002223  mov     r8, [rsp+68h+arg_10]
0x14000222b  mov     r9, [rsp+68h+arg_18]
0x140002233  add     rsp, 68h
0x140002237  jmp     short $+2
0x140002239  jmp     rax
```
