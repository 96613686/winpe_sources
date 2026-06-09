# __GSHandlerCheck

- ea: `0x180003a84`
- end: `0x180003aa1`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003aa8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4);
  return 1;
}

```

## disassembly

```asm
0x180003a84  sub     rsp, 28h
0x180003a88  mov     r8, [r9+38h]
0x180003a8c  mov     rcx, rdx
0x180003a8f  mov     rdx, r9
0x180003a92  call    __GSHandlerCheckCommon
0x180003a97  mov     eax, 1
0x180003a9c  add     rsp, 28h
0x180003aa0  retn
```
