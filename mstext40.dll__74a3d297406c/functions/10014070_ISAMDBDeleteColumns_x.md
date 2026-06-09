# ISAMDBDeleteColumns(x)

- ea: `0x10014070`
- end: `0x100140a7`
- name: `_ISAMDBDeleteColumns@4`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10010020`
- `0x10014270`

## callees

- `0x1000b200`
- `0x10014070`

## pseudocode

```c
_DWORD *__stdcall ISAMDBDeleteColumns(int a1)
{
  _DWORD *result; // eax
  _DWORD *v2; // esi

  result = *(_DWORD **)(a1 + 916);
  if ( result )
  {
    do
    {
      v2 = (_DWORD *)*result;
      MemFree(result);
      result = v2;
    }
    while ( v2 );
  }
  *(_DWORD *)(a1 + 912) = 0;
  *(_DWORD *)(a1 + 916) = 0;
  return result;
}

```

## disassembly

```asm
0x10014070  push    edi
0x10014071  mov     edi, [esp+4+arg_0]
0x10014075  mov     eax, [edi+394h]
0x1001407b  test    eax, eax
0x1001407d  jz      short loc_1001408F
0x1001407f  push    esi
0x10014080  mov     esi, [eax]
0x10014082  push    eax
0x10014083  call    _MemFree@4; MemFree(x)
0x10014088  mov     eax, esi
0x1001408a  test    esi, esi
0x1001408c  jnz     short loc_10014080
0x1001408e  pop     esi
0x1001408f  mov     dword ptr [edi+390h], 0
0x10014099  mov     dword ptr [edi+394h], 0
0x100140a3  pop     edi
0x100140a4  retn    4
```
