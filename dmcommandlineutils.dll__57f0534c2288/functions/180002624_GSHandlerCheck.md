# __GSHandlerCheck

- ea: `0x180002624`
- end: `0x180002641`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002648`

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
0x180002624  sub     rsp, 28h
0x180002628  mov     r8, [r9+38h]
0x18000262c  mov     rcx, rdx
0x18000262f  mov     rdx, r9
0x180002632  call    __GSHandlerCheckCommon
0x180002637  mov     eax, 1
0x18000263c  add     rsp, 28h
0x180002640  retn
```
