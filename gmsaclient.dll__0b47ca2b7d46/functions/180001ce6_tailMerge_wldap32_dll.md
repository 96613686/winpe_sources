# __tailMerge_wldap32_dll

- ea: `0x180001ce6`
- end: `0x180001d5f`
- name: `__tailMerge_wldap32_dll`
- size: `121`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d65`
- `0x180001e02`
- `0x180001fd9`
- `0x180001feb`
- `0x180001ffd`
- `0x18000200f`
- `0x180002033`
- `0x180002045`
- `0x180002057`
- `0x180002069`
- `0x18000207b`
- `0x18000208d`
- `0x18000209f`
- `0x1800020b1`
- `0x1800020c3`
- `0x1800020d5`
- `0x1800020e7`

## callees

- `0x180001ce6`
- `0x180007a80`

## pseudocode

```c
__int64 __fastcall _tailMerge_wldap32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wldap32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001ce6  mov     [rsp+arg_0], rcx
0x180001ceb  mov     [rsp+arg_8], rdx
0x180001cf0  mov     [rsp+arg_10], r8
0x180001cf5  mov     [rsp+arg_18], r9
0x180001cfa  sub     rsp, 68h
0x180001cfe  movdqa  [rsp+68h+var_48], xmm0
0x180001d04  movdqa  [rsp+68h+var_38], xmm1
0x180001d0a  movdqa  [rsp+68h+var_28], xmm2
0x180001d10  movdqa  [rsp+68h+var_18], xmm3
0x180001d16  mov     rdx, rax
0x180001d19  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wldap32_dll
0x180001d20  call    __delayLoadHelper2
0x180001d25  movdqa  xmm0, [rsp+68h+var_48]
0x180001d2b  movdqa  xmm1, [rsp+68h+var_38]
0x180001d31  movdqa  xmm2, [rsp+68h+var_28]
0x180001d37  movdqa  xmm3, [rsp+68h+var_18]
0x180001d3d  mov     rcx, [rsp+68h+arg_0]
0x180001d42  mov     rdx, [rsp+68h+arg_8]
0x180001d47  mov     r8, [rsp+68h+arg_10]
0x180001d4f  mov     r9, [rsp+68h+arg_18]
0x180001d57  add     rsp, 68h
0x180001d5b  jmp     short $+2
0x180001d5d  jmp     rax
```
