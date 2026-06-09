# __GSHandlerCheck

- ea: `0x140001048`
- end: `0x140001066`
- name: `__GSHandlerCheck`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000106c`

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
0x140001048  sub     rsp, 28h
0x14000104c  mov     r8, [r9+38h]
0x140001050  mov     rcx, rdx
0x140001053  mov     rdx, r9
0x140001056  call    __GSHandlerCheckCommon
0x14000105b  mov     eax, 1
0x140001060  add     rsp, 28h
0x140001064  retn
```
