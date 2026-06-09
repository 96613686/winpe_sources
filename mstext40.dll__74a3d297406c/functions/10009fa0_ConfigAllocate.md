# ConfigAllocate()

- ea: `0x10009fa0`
- end: `0x10009fb7`
- name: `_ConfigAllocate@0`
- size: `23`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10015240`

## callees

- `0x10009fa0`
- `0x1000b070`

## pseudocode

```c
_DWORD *__stdcall ConfigAllocate()
{
  _DWORD *result; // eax

  result = MemAllocate(8);
  if ( result )
  {
    *result = 0;
    *((_BYTE *)result + 4) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x10009fa0  push    8; Size
0x10009fa2  call    _MemAllocate@4; MemAllocate(x)
0x10009fa7  test    eax, eax
0x10009fa9  jnz     short loc_10009FAC
0x10009fab  retn
0x10009fac  mov     dword ptr [eax], 0
0x10009fb2  mov     byte ptr [eax+4], 1
0x10009fb6  retn
```
