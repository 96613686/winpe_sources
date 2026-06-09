# __GSHandlerCheck

- ea: `0x180002fa8`
- end: `0x180002fc5`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002fcc`

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
0x180002fa8  sub     rsp, 28h
0x180002fac  mov     r8, [r9+38h]
0x180002fb0  mov     rcx, rdx
0x180002fb3  mov     rdx, r9
0x180002fb6  call    __GSHandlerCheckCommon
0x180002fbb  mov     eax, 1
0x180002fc0  add     rsp, 28h
0x180002fc4  retn
```
