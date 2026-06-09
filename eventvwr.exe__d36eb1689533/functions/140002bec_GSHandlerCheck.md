# __GSHandlerCheck

- ea: `0x140002bec`
- end: `0x140002c09`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002c10`

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
0x140002bec  sub     rsp, 28h
0x140002bf0  mov     r8, [r9+38h]
0x140002bf4  mov     rcx, rdx
0x140002bf7  mov     rdx, r9
0x140002bfa  call    __GSHandlerCheckCommon
0x140002bff  mov     eax, 1
0x140002c04  add     rsp, 28h
0x140002c08  retn
```
