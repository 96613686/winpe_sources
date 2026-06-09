# __GSHandlerCheck

- ea: `0x140001a84`
- end: `0x140001aa1`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001aa8`

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
0x140001a84  sub     rsp, 28h
0x140001a88  mov     r8, [r9+38h]
0x140001a8c  mov     rcx, rdx
0x140001a8f  mov     rdx, r9
0x140001a92  call    __GSHandlerCheckCommon
0x140001a97  mov     eax, 1
0x140001a9c  add     rsp, 28h
0x140001aa0  retn
```
