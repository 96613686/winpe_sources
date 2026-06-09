# ISAMDBDeleteCursor(x,x)

- ea: `0x100140b0`
- end: `0x10014100`
- name: `_ISAMDBDeleteCursor@8`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10011060`
- `0x10012e70`

## callees

- `0x1000b200`
- `0x100140b0`

## pseudocode

```c
int __stdcall ISAMDBDeleteCursor(int a1, _DWORD *a2)
{
  _DWORD *v2; // edx
  _DWORD *v3; // ecx
  int v5; // eax

  v2 = 0;
  v3 = *(_DWORD **)(a1 + 868);
  if ( !v3 )
    return -1310;
  while ( v3 != a2 )
  {
    v2 = v3;
    v3 = (_DWORD *)*v3;
    if ( !v3 )
      return -1310;
  }
  v5 = *v3;
  if ( v2 )
    *v2 = v5;
  else
    *(_DWORD *)(a1 + 868) = v5;
  MemFree(v3);
  return 0;
}

```

## disassembly

```asm
0x100140b0  push    esi
0x100140b1  mov     esi, [esp+4+arg_0]
0x100140b5  xor     edx, edx
0x100140b7  mov     ecx, [esi+364h]
0x100140bd  test    ecx, ecx
0x100140bf  jz      short loc_100140D1
0x100140c1  mov     eax, [esp+4+arg_4]
0x100140c5  cmp     ecx, eax
0x100140c7  jz      short loc_100140DA
0x100140c9  mov     edx, ecx
0x100140cb  mov     ecx, [ecx]
0x100140cd  test    ecx, ecx
0x100140cf  jnz     short loc_100140C5
0x100140d1  mov     eax, 0FFFFFAE2h
0x100140d6  pop     esi
0x100140d7  retn    8
0x100140da  mov     eax, [ecx]
0x100140dc  test    edx, edx
0x100140de  jnz     short loc_100140F2
0x100140e0  push    ecx
0x100140e1  mov     [esi+364h], eax
0x100140e7  call    _MemFree@4; MemFree(x)
0x100140ec  xor     eax, eax
0x100140ee  pop     esi
0x100140ef  retn    8
0x100140f2  push    ecx
0x100140f3  mov     [edx], eax
0x100140f5  call    _MemFree@4; MemFree(x)
0x100140fa  xor     eax, eax
0x100140fc  pop     esi
0x100140fd  retn    8
```
