# ISAMDBDeleteDatabaseUser(x,x)

- ea: `0x100141b0`
- end: `0x100141f6`
- name: `_ISAMDBDeleteDatabaseUser@8`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x10011310`
- `0x10011d90`

## callees

- `0x1000b200`
- `0x100141b0`
- `0x1001f060`

## pseudocode

```c
void __stdcall ISAMDBDeleteDatabaseUser(int a1, _DWORD *a2)
{
  _DWORD *v2; // ecx
  _DWORD *v3; // esi
  int v4; // eax

  v2 = 0;
  v3 = *(_DWORD **)(a1 + 48);
  if ( v3 )
  {
    while ( v3 != a2 )
    {
      v2 = v3;
      v3 = (_DWORD *)*v3;
      if ( !v3 )
        return;
    }
    v4 = *v3;
    if ( v2 )
      *v2 = v4;
    else
      *(_DWORD *)(a1 + 48) = v4;
    if ( v3[5] )
      TextDestroyFileList(v3[5]);
    MemFree(v3);
  }
}

```

## disassembly

```asm
0x100141b0  mov     edx, [esp+arg_0]
0x100141b4  xor     ecx, ecx
0x100141b6  push    esi
0x100141b7  mov     esi, [edx+30h]
0x100141ba  test    esi, esi
0x100141bc  jz      short loc_100141F2
0x100141be  mov     eax, [esp+4+arg_4]
0x100141c2  cmp     esi, eax
0x100141c4  jz      short loc_100141D2
0x100141c6  mov     ecx, esi
0x100141c8  mov     esi, [esi]
0x100141ca  test    esi, esi
0x100141cc  jnz     short loc_100141C2
0x100141ce  pop     esi
0x100141cf  retn    8
0x100141d2  mov     eax, [esi]
0x100141d4  test    ecx, ecx
0x100141d6  jnz     short loc_100141DD
0x100141d8  mov     [edx+30h], eax
0x100141db  jmp     short loc_100141DF
0x100141dd  mov     [ecx], eax
0x100141df  mov     eax, [esi+14h]
0x100141e2  test    eax, eax
0x100141e4  jz      short loc_100141EC
0x100141e6  push    eax
0x100141e7  call    _TextDestroyFileList@4; TextDestroyFileList(x)
0x100141ec  push    esi
0x100141ed  call    _MemFree@4; MemFree(x)
0x100141f2  pop     esi
0x100141f3  retn    8
```
