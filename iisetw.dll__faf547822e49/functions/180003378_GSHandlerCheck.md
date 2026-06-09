# __GSHandlerCheck

- ea: `0x180003378`
- end: `0x180003395`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000339c`

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
0x180003378  sub     rsp, 28h
0x18000337c  mov     r8, [r9+38h]
0x180003380  mov     rcx, rdx
0x180003383  mov     rdx, r9
0x180003386  call    __GSHandlerCheckCommon
0x18000338b  mov     eax, 1
0x180003390  add     rsp, 28h
0x180003394  retn
```
