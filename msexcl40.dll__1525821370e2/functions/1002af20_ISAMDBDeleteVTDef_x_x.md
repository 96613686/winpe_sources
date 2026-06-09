# ISAMDBDeleteVTDef(x,x)

- ea: `0x1002af20`
- end: `0x1002af6f`
- name: `_ISAMDBDeleteVTDef@8`
- size: `79`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x10006a60`
- `0x1002b0c0`
- `0x1002b250`
- `0x1002b580`
- `0x1002ba40`
- `0x1002bff0`

## callees

- `0x10025ab7`
- `0x1002af20`

## pseudocode

```c
int __fastcall ISAMDBDeleteVTDef(int a1, _DWORD *a2)
{
  _DWORD *v4; // edx
  _DWORD *i; // eax
  _DWORD *v6; // ecx
  _DWORD *v8; // ecx
  _DWORD *v9; // esi

  v4 = 0;
  for ( i = *(_DWORD **)(a1 + 8); ; i = (_DWORD *)*i )
  {
    if ( !i )
      return -1310;
    v6 = (_DWORD *)*i;
    if ( i == a2 )
      break;
    v4 = i;
  }
  if ( v4 )
    *v4 = v6;
  else
    *(_DWORD *)(a1 + 8) = v6;
  v8 = (_DWORD *)a2[10];
  if ( v8 )
  {
    do
    {
      v9 = (_DWORD *)*v8;
      MemFree(v8);
      v8 = v9;
    }
    while ( v9 );
  }
  MemFree(a2);
  return 0;
}

```

## disassembly

```asm
0x1002af20  mov     edi, edi
0x1002af22  push    esi
0x1002af23  mov     esi, ecx
0x1002af25  push    edi
0x1002af26  mov     edi, edx
0x1002af28  xor     edx, edx
0x1002af2a  mov     eax, [esi+8]
0x1002af2d  jmp     short loc_1002AF39
0x1002af2f  mov     ecx, [eax]
0x1002af31  cmp     eax, edi
0x1002af33  jz      short loc_1002AF45
0x1002af35  mov     edx, eax
0x1002af37  mov     eax, ecx
0x1002af39  test    eax, eax
0x1002af3b  jnz     short loc_1002AF2F
0x1002af3d  mov     eax, 0FFFFFAE2h
0x1002af42  pop     edi
0x1002af43  pop     esi
0x1002af44  retn
0x1002af45  test    edx, edx
0x1002af47  jnz     short loc_1002AF4E
0x1002af49  mov     [esi+8], ecx
0x1002af4c  jmp     short loc_1002AF50
0x1002af4e  mov     [edx], ecx
0x1002af50  mov     ecx, [edi+28h]
0x1002af53  test    ecx, ecx
0x1002af55  jz      short loc_1002AF64
0x1002af57  mov     esi, [ecx]
0x1002af59  call    _MemFree@4; MemFree(x)
0x1002af5e  mov     ecx, esi
0x1002af60  test    esi, esi
0x1002af62  jnz     short loc_1002AF57
0x1002af64  mov     ecx, edi
0x1002af66  call    _MemFree@4; MemFree(x)
0x1002af6b  xor     eax, eax
0x1002af6d  jmp     short loc_1002AF42
```
