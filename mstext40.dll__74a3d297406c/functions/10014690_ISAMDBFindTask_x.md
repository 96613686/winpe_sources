# ISAMDBFindTask(x)

- ea: `0x10014690`
- end: `0x100146b0`
- name: `_ISAMDBFindTask@4`
- size: `32`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1000f0e0`
- `0x100108e0`
- `0x10011060`
- `0x10011310`
- `0x10011870`
- `0x10011d90`
- `0x10012e70`
- `0x100147d0`
- `0x100148d0`
- `0x10014ea0`
- `0x100170e0`
- `0x100178b0`
- `0x10017ea0`
- `0x10018160`
- `0x10018200`
- `0x1001ca20`
- `0x1001cb00`

## callees

- `0x10014690`

## pseudocode

```c
_DWORD *__stdcall ISAMDBFindTask(int a1)
{
  _DWORD *result; // eax

  result = (_DWORD *)dword_10040FBC;
  if ( !dword_10040FBC )
    return 0;
  while ( result[4] != a1 )
  {
    result = (_DWORD *)*result;
    if ( !result )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10014690  mov     eax, dword_10040FBC
0x10014695  test    eax, eax
0x10014697  jz      short loc_100146AB
0x10014699  mov     ecx, [esp+arg_0]
0x1001469d  lea     ecx, [ecx+0]
0x100146a0  cmp     [eax+10h], ecx
0x100146a3  jz      short locret_100146AD
0x100146a5  mov     eax, [eax]
0x100146a7  test    eax, eax
0x100146a9  jnz     short loc_100146A0
0x100146ab  xor     eax, eax
0x100146ad  retn    4
```
