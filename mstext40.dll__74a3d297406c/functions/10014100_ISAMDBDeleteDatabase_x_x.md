# ISAMDBDeleteDatabase(x,x)

- ea: `0x10014100`
- end: `0x100141b0`
- name: `_ISAMDBDeleteDatabase@8`
- size: `176`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x10011310`
- `0x10011d90`
- `0x10014320`

## callees

- `0x1000b200`
- `0x10014100`
- `0x10014270`
- `0x1001f060`

## pseudocode

```c
void __stdcall ISAMDBDeleteDatabase(int a1, _DWORD *a2)
{
  int v2; // ebx
  _DWORD *v3; // ebp
  _DWORD *v4; // edi
  _DWORD *v5; // eax
  _DWORD *v6; // esi
  _DWORD *v7; // eax
  _DWORD *v8; // esi
  _DWORD *v9; // ecx
  _DWORD *v10; // ebx
  int v11; // eax
  int v12; // eax

  v2 = a1;
  v3 = 0;
  v4 = *(_DWORD **)(a1 + 8);
  if ( v4 )
  {
    while ( v4 != a2 )
    {
      v3 = v4;
      v4 = (_DWORD *)*v4;
      if ( !v4 )
        return;
    }
    v5 = (_DWORD *)v4[13];
    if ( v5 )
    {
      do
      {
        v6 = (_DWORD *)*v5;
        ISAMDBDeleteTable((int)v4, v5);
        v5 = v6;
      }
      while ( v6 );
    }
    v7 = (_DWORD *)v4[12];
    if ( v7 )
    {
      do
      {
        v8 = (_DWORD *)v4[12];
        v9 = 0;
        v10 = (_DWORD *)*v7;
        if ( v8 )
        {
          while ( v8 != v7 )
          {
            v9 = v8;
            v8 = (_DWORD *)*v8;
            if ( !v8 )
              goto LABEL_18;
          }
          v11 = *v8;
          if ( v9 )
            *v9 = v11;
          else
            v4[12] = v11;
          if ( v8[5] )
            TextDestroyFileList(v8[5]);
          MemFree(v8);
        }
LABEL_18:
        v7 = v10;
      }
      while ( v10 );
      v2 = a1;
    }
    v12 = *v4;
    if ( v3 )
      *v3 = v12;
    else
      *(_DWORD *)(v2 + 8) = v12;
    MemFree(v4);
  }
}

```

## disassembly

```asm
0x10014100  push    ebx
0x10014101  mov     ebx, [esp+4+arg_0]
0x10014105  push    ebp
0x10014106  push    edi
0x10014107  xor     ebp, ebp
0x10014109  mov     edi, [ebx+8]
0x1001410c  test    edi, edi
0x1001410e  jz      loc_100141AA
0x10014114  mov     eax, [esp+0Ch+arg_4]
0x10014118  cmp     edi, eax
0x1001411a  jz      short loc_1001412A
0x1001411c  mov     ebp, edi
0x1001411e  mov     edi, [edi]
0x10014120  test    edi, edi
0x10014122  jnz     short loc_10014118
0x10014124  pop     edi
0x10014125  pop     ebp
0x10014126  pop     ebx
0x10014127  retn    8
0x1001412a  mov     eax, [edi+34h]
0x1001412d  push    esi
0x1001412e  test    eax, eax
0x10014130  jz      short loc_10014141
0x10014132  mov     esi, [eax]
0x10014134  push    eax
0x10014135  push    edi
0x10014136  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x1001413b  mov     eax, esi
0x1001413d  test    esi, esi
0x1001413f  jnz     short loc_10014132
0x10014141  mov     eax, [edi+30h]
0x10014144  test    eax, eax
0x10014146  jz      short loc_1001418B
0x10014148  mov     esi, [edi+30h]
0x1001414b  xor     ecx, ecx
0x1001414d  mov     ebx, [eax]
0x1001414f  test    esi, esi
0x10014151  jz      short loc_10014181
0x10014153  cmp     esi, eax
0x10014155  jz      short loc_10014161
0x10014157  mov     ecx, esi
0x10014159  mov     esi, [esi]
0x1001415b  test    esi, esi
0x1001415d  jnz     short loc_10014153
0x1001415f  jmp     short loc_10014181
0x10014161  mov     eax, [esi]
0x10014163  test    ecx, ecx
0x10014165  jnz     short loc_1001416C
0x10014167  mov     [edi+30h], eax
0x1001416a  jmp     short loc_1001416E
0x1001416c  mov     [ecx], eax
0x1001416e  mov     eax, [esi+14h]
0x10014171  test    eax, eax
0x10014173  jz      short loc_1001417B
0x10014175  push    eax
0x10014176  call    _TextDestroyFileList@4; TextDestroyFileList(x)
0x1001417b  push    esi
0x1001417c  call    _MemFree@4; MemFree(x)
0x10014181  mov     eax, ebx
0x10014183  test    ebx, ebx
0x10014185  jnz     short loc_10014148
0x10014187  mov     ebx, [esp+10h+arg_0]
0x1001418b  mov     eax, [edi]
0x1001418d  pop     esi
0x1001418e  test    ebp, ebp
0x10014190  jnz     short loc_100141A1
0x10014192  push    edi
0x10014193  mov     [ebx+8], eax
0x10014196  call    _MemFree@4; MemFree(x)
0x1001419b  pop     edi
0x1001419c  pop     ebp
0x1001419d  pop     ebx
0x1001419e  retn    8
0x100141a1  push    edi
0x100141a2  mov     [ebp+0], eax
0x100141a5  call    _MemFree@4; MemFree(x)
0x100141aa  pop     edi
0x100141ab  pop     ebp
0x100141ac  pop     ebx
0x100141ad  retn    8
```
