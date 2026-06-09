# __tailMerge_samlib_dll

- ea: `0x1800037bc`
- end: `0x180003835`
- name: `__tailMerge_samlib_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000383b`
- `0x18000384d`
- `0x18000385f`
- `0x180003871`
- `0x180003883`
- `0x180003895`
- `0x1800038a7`

## callees

- `0x1800037bc`
- `0x18002de50`

## pseudocode

```c
__int64 __fastcall _tailMerge_samlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_samlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800037bc  mov     [rsp+arg_0], rcx
0x1800037c1  mov     [rsp+arg_8], rdx
0x1800037c6  mov     [rsp+arg_10], r8
0x1800037cb  mov     [rsp+arg_18], r9
0x1800037d0  sub     rsp, 68h
0x1800037d4  movdqa  [rsp+68h+var_48], xmm0
0x1800037da  movdqa  [rsp+68h+var_38], xmm1
0x1800037e0  movdqa  [rsp+68h+var_28], xmm2
0x1800037e6  movdqa  [rsp+68h+var_18], xmm3
0x1800037ec  mov     rdx, rax
0x1800037ef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samlib_dll
0x1800037f6  call    __delayLoadHelper2
0x1800037fb  movdqa  xmm0, [rsp+68h+var_48]
0x180003801  movdqa  xmm1, [rsp+68h+var_38]
0x180003807  movdqa  xmm2, [rsp+68h+var_28]
0x18000380d  movdqa  xmm3, [rsp+68h+var_18]
0x180003813  mov     rcx, [rsp+68h+arg_0]
0x180003818  mov     rdx, [rsp+68h+arg_8]
0x18000381d  mov     r8, [rsp+68h+arg_10]
0x180003825  mov     r9, [rsp+68h+arg_18]
0x18000382d  add     rsp, 68h
0x180003831  jmp     short $+2
0x180003833  jmp     rax
```
