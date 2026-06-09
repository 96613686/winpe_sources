# __GSHandlerCheck

- ea: `0x180002b28`
- end: `0x180002b45`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002b4c`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4, *(_QWORD *)(a4 + 56));
  return 1;
}

```

## disassembly

```asm
0x180002b28  sub     rsp, 28h
0x180002b2c  mov     r8, [r9+38h]
0x180002b30  mov     rcx, rdx
0x180002b33  mov     rdx, r9
0x180002b36  call    __GSHandlerCheckCommon
0x180002b3b  mov     eax, 1
0x180002b40  add     rsp, 28h
0x180002b44  retn
```
