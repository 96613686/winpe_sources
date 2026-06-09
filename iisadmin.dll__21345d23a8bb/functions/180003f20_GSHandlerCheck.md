# __GSHandlerCheck

- ea: `0x180003f20`
- end: `0x180003f3d`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003f44`

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
0x180003f20  sub     rsp, 28h
0x180003f24  mov     r8, [r9+38h]
0x180003f28  mov     rcx, rdx
0x180003f2b  mov     rdx, r9
0x180003f2e  call    __GSHandlerCheckCommon
0x180003f33  mov     eax, 1
0x180003f38  add     rsp, 28h
0x180003f3c  retn
```
