# output_bits

- ea: `0x18000ea34`
- end: `0x18000eab2`
- name: `output_bits`
- size: `126`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e558`
- `0x18000e684`
- `0x180010130`
- `0x180011068`
- `0x180011134`
- `0x18001748c`

## callees

- `0x18000ea34`

## pseudocode

```c
char __fastcall output_bits(__int64 a1, char a2, int a3)
{
  char v3; // al
  char result; // al
  _BYTE *v6; // rcx
  char v7; // al
  _BYTE *v8; // rcx
  int v9; // eax

  v3 = *(_BYTE *)(a1 + 44);
  *(_DWORD *)(a1 + 40) |= a3 << (v3 - a2);
  for ( result = v3 - a2; ; result = *(_BYTE *)(a1 + 44) + 16 )
  {
    *(_BYTE *)(a1 + 44) = result;
    if ( result > 16 )
      break;
    v6 = *(_BYTE **)(a1 + 2184);
    if ( (unsigned __int64)v6 >= *(_QWORD *)(a1 + 2192) )
    {
      v6 = *(_BYTE **)(a1 + 2176);
      *(_QWORD *)(a1 + 2184) = v6;
      *(_DWORD *)(a1 + 48) = 1;
    }
    *v6 = *(_BYTE *)(a1 + 42);
    v7 = *(_BYTE *)(a1 + 43);
    v8 = (_BYTE *)(*(_QWORD *)(a1 + 2184) + 1LL);
    *(_QWORD *)(a1 + 2184) = v8;
    *v8 = v7;
    v9 = *(_DWORD *)(a1 + 40);
    ++*(_QWORD *)(a1 + 2184);
    *(_DWORD *)(a1 + 40) = v9 << 16;
  }
  return result;
}

```

## disassembly

```asm
0x18000ea34  movsx   eax, byte ptr [rcx+2Ch]
0x18000ea38  mov     r9, rcx
0x18000ea3b  mov     ecx, eax
0x18000ea3d  sub     ecx, edx
0x18000ea3f  shl     r8d, cl
0x18000ea42  or      [r9+28h], r8d
0x18000ea46  sub     al, dl
0x18000ea48  mov     dl, 10h
0x18000ea4a  mov     [r9+2Ch], al
0x18000ea4e  cmp     al, dl
0x18000ea50  jg      short locret_18000EA99
0x18000ea52  mov     rcx, [r9+888h]
0x18000ea59  cmp     rcx, [r9+890h]
0x18000ea60  jnb     short loc_18000EA9A
0x18000ea62  mov     al, [r9+2Ah]
0x18000ea66  mov     [rcx], al
0x18000ea68  mov     rcx, [r9+888h]
0x18000ea6f  mov     al, [r9+2Bh]
0x18000ea73  inc     rcx
0x18000ea76  mov     [r9+888h], rcx
0x18000ea7d  mov     [rcx], al
0x18000ea7f  mov     eax, [r9+28h]
0x18000ea83  inc     qword ptr [r9+888h]
0x18000ea8a  shl     eax, 10h
0x18000ea8d  mov     [r9+28h], eax
0x18000ea91  mov     al, [r9+2Ch]
0x18000ea95  add     al, dl
0x18000ea97  jmp     short loc_18000EA4A
0x18000ea99  retn
0x18000ea9a  mov     rcx, [r9+880h]
0x18000eaa1  mov     [r9+888h], rcx
0x18000eaa8  mov     dword ptr [r9+30h], 1
0x18000eab0  jmp     short loc_18000EA62
```
