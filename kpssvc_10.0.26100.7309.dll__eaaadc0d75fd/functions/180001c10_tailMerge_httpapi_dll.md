# __tailMerge_httpapi_dll

- ea: `0x180001c10`
- end: `0x180001c89`
- name: `__tailMerge_httpapi_dll`
- size: `121`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c8f`
- `0x180001ca1`
- `0x180001cb3`
- `0x180001cc5`
- `0x180001cd7`
- `0x180001ce9`
- `0x180001cfb`
- `0x180001d0d`
- `0x180001d1f`
- `0x180001d31`
- `0x180001d43`
- `0x180001d55`
- `0x180001d67`
- `0x180001d79`
- `0x180001d8b`

## callees

- `0x180001c10`
- `0x180030f20`

## pseudocode

```c
__int64 __fastcall _tailMerge_httpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_httpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001c10  mov     [rsp+arg_0], rcx
0x180001c15  mov     [rsp+arg_8], rdx
0x180001c1a  mov     [rsp+arg_10], r8
0x180001c1f  mov     [rsp+arg_18], r9
0x180001c24  sub     rsp, 68h
0x180001c28  movdqa  [rsp+68h+var_48], xmm0
0x180001c2e  movdqa  [rsp+68h+var_38], xmm1
0x180001c34  movdqa  [rsp+68h+var_28], xmm2
0x180001c3a  movdqa  [rsp+68h+var_18], xmm3
0x180001c40  mov     rdx, rax
0x180001c43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_httpapi_dll
0x180001c4a  call    __delayLoadHelper2
0x180001c4f  movdqa  xmm0, [rsp+68h+var_48]
0x180001c55  movdqa  xmm1, [rsp+68h+var_38]
0x180001c5b  movdqa  xmm2, [rsp+68h+var_28]
0x180001c61  movdqa  xmm3, [rsp+68h+var_18]
0x180001c67  mov     rcx, [rsp+68h+arg_0]
0x180001c6c  mov     rdx, [rsp+68h+arg_8]
0x180001c71  mov     r8, [rsp+68h+arg_10]
0x180001c79  mov     r9, [rsp+68h+arg_18]
0x180001c81  add     rsp, 68h
0x180001c85  jmp     short $+2
0x180001c87  jmp     rax
```
