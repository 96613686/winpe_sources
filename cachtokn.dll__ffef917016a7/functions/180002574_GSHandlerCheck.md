# __GSHandlerCheck

- ea: `0x180002574`
- end: `0x180002591`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002598`

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
0x180002574  sub     rsp, 28h
0x180002578  mov     r8, [r9+38h]
0x18000257c  mov     rcx, rdx
0x18000257f  mov     rdx, r9
0x180002582  call    __GSHandlerCheckCommon
0x180002587  mov     eax, 1
0x18000258c  add     rsp, 28h
0x180002590  retn
```
