# ISAMDBDeleteDatabaseUser(x,x)

- ea: `0x1002aa6e`
- end: `0x1002aa9e`
- name: `_ISAMDBDeleteDatabaseUser@8`
- size: `48`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10026c60`
- `0x100279f0`
- `0x1002a907`

## callees

- `0x10025ab7`
- `0x1002aa6e`

## pseudocode

```c
void __fastcall ISAMDBDeleteDatabaseUser(int a1, _DWORD *a2)
{
  _DWORD *v3; // esi
  _DWORD *i; // ecx
  _DWORD *v5; // eax

  v3 = 0;
  for ( i = *(_DWORD **)(a1 + 44); i; i = (_DWORD *)*i )
  {
    v5 = (_DWORD *)*i;
    if ( i == a2 )
    {
      if ( v3 )
        *v3 = v5;
      else
        *(_DWORD *)(a1 + 44) = v5;
      MemFree(i);
      return;
    }
    v3 = i;
  }
}

```

## disassembly

```asm
0x1002aa6e  mov     edi, edi
0x1002aa70  push    esi
0x1002aa71  push    edi
0x1002aa72  mov     edi, ecx
0x1002aa74  xor     esi, esi
0x1002aa76  mov     ecx, [edi+2Ch]
0x1002aa79  jmp     short loc_1002AA85
0x1002aa7b  mov     eax, [ecx]
0x1002aa7d  cmp     ecx, edx
0x1002aa7f  jz      short loc_1002AA8C
0x1002aa81  mov     esi, ecx
0x1002aa83  mov     ecx, eax
0x1002aa85  test    ecx, ecx
0x1002aa87  jnz     short loc_1002AA7B
0x1002aa89  pop     edi
0x1002aa8a  pop     esi
0x1002aa8b  retn
0x1002aa8c  test    esi, esi
0x1002aa8e  jnz     short loc_1002AA95
0x1002aa90  mov     [edi+2Ch], eax
0x1002aa93  jmp     short loc_1002AA97
0x1002aa95  mov     [esi], eax
0x1002aa97  pop     edi
0x1002aa98  pop     esi
0x1002aa99  jmp     _MemFree@4; MemFree(x)
```
