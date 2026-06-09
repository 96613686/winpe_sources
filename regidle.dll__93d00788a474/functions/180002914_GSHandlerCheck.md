# __GSHandlerCheck

- ea: `0x180002914`
- end: `0x180002931`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002938`

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
0x180002914  sub     rsp, 28h
0x180002918  mov     r8, [r9+38h]
0x18000291c  mov     rcx, rdx
0x18000291f  mov     rdx, r9
0x180002922  call    __GSHandlerCheckCommon
0x180002927  mov     eax, 1
0x18000292c  add     rsp, 28h
0x180002930  retn
```
