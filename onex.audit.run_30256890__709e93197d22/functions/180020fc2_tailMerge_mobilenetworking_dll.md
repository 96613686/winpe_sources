# __tailMerge_mobilenetworking_dll

- ea: `0x180020fc2`
- end: `0x18002103b`
- name: `__tailMerge_mobilenetworking_dll`
- size: `121`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021041`
- `0x180021053`
- `0x180021065`
- `0x180021077`
- `0x180021089`
- `0x18002109b`
- `0x1800210ad`
- `0x1800210bf`
- `0x1800210d1`
- `0x1800210e3`
- `0x1800210f5`
- `0x180021107`
- `0x180021119`
- `0x18002112b`
- `0x18002113d`
- `0x18002114f`
- `0x180021161`
- `0x180021173`
- `0x180021185`

## callees

- `0x180018b30`
- `0x180020fc2`

## pseudocode

```c
__int64 __fastcall _tailMerge_mobilenetworking_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mobilenetworking_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180020fc2  mov     [rsp+arg_0], rcx
0x180020fc7  mov     [rsp+arg_8], rdx
0x180020fcc  mov     [rsp+arg_10], r8
0x180020fd1  mov     [rsp+arg_18], r9
0x180020fd6  sub     rsp, 68h
0x180020fda  movdqa  [rsp+68h+var_48], xmm0
0x180020fe0  movdqa  [rsp+68h+var_38], xmm1
0x180020fe6  movdqa  [rsp+68h+var_28], xmm2
0x180020fec  movdqa  [rsp+68h+var_18], xmm3
0x180020ff2  mov     rdx, rax
0x180020ff5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mobilenetworking_dll
0x180020ffc  call    __delayLoadHelper2
0x180021001  movdqa  xmm0, [rsp+68h+var_48]
0x180021007  movdqa  xmm1, [rsp+68h+var_38]
0x18002100d  movdqa  xmm2, [rsp+68h+var_28]
0x180021013  movdqa  xmm3, [rsp+68h+var_18]
0x180021019  mov     rcx, [rsp+68h+arg_0]
0x18002101e  mov     rdx, [rsp+68h+arg_8]
0x180021023  mov     r8, [rsp+68h+arg_10]
0x18002102b  mov     r9, [rsp+68h+arg_18]
0x180021033  add     rsp, 68h
0x180021037  jmp     short $+2
0x180021039  jmp     rax
```
