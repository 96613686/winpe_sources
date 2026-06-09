# __GSHandlerCheck

- ea: `0x140002798`
- end: `0x1400027b5`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400027bc`

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
0x140002798  sub     rsp, 28h
0x14000279c  mov     r8, [r9+38h]
0x1400027a0  mov     rcx, rdx
0x1400027a3  mov     rdx, r9
0x1400027a6  call    __GSHandlerCheckCommon
0x1400027ab  mov     eax, 1
0x1400027b0  add     rsp, 28h
0x1400027b4  retn
```
