# ISAMDBFindTask(x)

- ea: `0x1002a7de`
- end: `0x1002a7f1`
- name: `_ISAMDBFindTask@4`
- size: `19`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10026c60`
- `0x100279f0`
- `0x10029068`
- `0x10029730`
- `0x1002a7f7`
- `0x1002b0c0`
- `0x1002b250`
- `0x1002b580`
- `0x1002ba40`
- `0x1002bff0`
- `0x1002df60`
- `0x10034b1c`
- `0x10034bca`

## callees

- `0x1002a7de`

## pseudocode

```c
_DWORD *__thiscall ISAMDBFindTask(void *this)
{
  _DWORD *result; // eax

  for ( result = (_DWORD *)dword_1003AE68; result && (void *)result[4] != this; result = (_DWORD *)*result )
    ;
  return result;
}

```

## disassembly

```asm
0x1002a7de  mov     eax, dword_1003AE68
0x1002a7e3  jmp     short loc_1002A7EC
0x1002a7e5  cmp     [eax+10h], ecx
0x1002a7e8  jz      short locret_1002A7F0
0x1002a7ea  mov     eax, [eax]
0x1002a7ec  test    eax, eax
0x1002a7ee  jnz     short loc_1002A7E5
0x1002a7f0  retn
```
