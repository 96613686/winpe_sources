# __GSHandlerCheck

- ea: `0x140001f3c`
- end: `0x140001f59`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001f60`

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
0x140001f3c  sub     rsp, 28h
0x140001f40  mov     r8, [r9+38h]
0x140001f44  mov     rcx, rdx
0x140001f47  mov     rdx, r9
0x140001f4a  call    __GSHandlerCheckCommon
0x140001f4f  mov     eax, 1
0x140001f54  add     rsp, 28h
0x140001f58  retn
```
