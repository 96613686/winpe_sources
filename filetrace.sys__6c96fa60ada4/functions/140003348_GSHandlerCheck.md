# __GSHandlerCheck

- ea: `0x140003348`
- end: `0x140003366`
- name: `__GSHandlerCheck`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000336c`

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
0x140003348  sub     rsp, 28h
0x14000334c  mov     r8, [r9+38h]
0x140003350  mov     rcx, rdx
0x140003353  mov     rdx, r9
0x140003356  call    __GSHandlerCheckCommon
0x14000335b  mov     eax, 1
0x140003360  add     rsp, 28h
0x140003364  retn
```
