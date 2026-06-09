# __tailMerge_oleaut32_dll

- ea: `0x180003f54`
- end: `0x180003fcd`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003fd3`
- `0x180003fe5`
- `0x180003ff7`
- `0x180004143`
- `0x18000426b`
- `0x18000427d`
- `0x18000428f`
- `0x1800042a1`
- `0x1800042b3`
- `0x1800042c5`
- `0x1800042d7`
- `0x1800042e9`
- `0x180004398`

## callees

- `0x180003f54`
- `0x1800223d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003f54  mov     [rsp+arg_0], rcx
0x180003f59  mov     [rsp+arg_8], rdx
0x180003f5e  mov     [rsp+arg_10], r8
0x180003f63  mov     [rsp+arg_18], r9
0x180003f68  sub     rsp, 68h
0x180003f6c  movdqa  [rsp+68h+var_48], xmm0
0x180003f72  movdqa  [rsp+68h+var_38], xmm1
0x180003f78  movdqa  [rsp+68h+var_28], xmm2
0x180003f7e  movdqa  [rsp+68h+var_18], xmm3
0x180003f84  mov     rdx, rax
0x180003f87  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180003f8e  call    __delayLoadHelper2
0x180003f93  movdqa  xmm0, [rsp+68h+var_48]
0x180003f99  movdqa  xmm1, [rsp+68h+var_38]
0x180003f9f  movdqa  xmm2, [rsp+68h+var_28]
0x180003fa5  movdqa  xmm3, [rsp+68h+var_18]
0x180003fab  mov     rcx, [rsp+68h+arg_0]
0x180003fb0  mov     rdx, [rsp+68h+arg_8]
0x180003fb5  mov     r8, [rsp+68h+arg_10]
0x180003fbd  mov     r9, [rsp+68h+arg_18]
0x180003fc5  add     rsp, 68h
0x180003fc9  jmp     short $+2
0x180003fcb  jmp     rax
```
