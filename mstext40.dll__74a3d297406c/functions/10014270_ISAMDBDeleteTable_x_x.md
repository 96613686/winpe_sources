# ISAMDBDeleteTable(x,x)

- ea: `0x10014270`
- end: `0x10014312`
- name: `_ISAMDBDeleteTable@8`
- size: `162`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1000f0e0`
- `0x100108e0`
- `0x10011060`
- `0x100113f0`
- `0x10012e70`
- `0x10014100`
- `0x10016b70`
- `0x10016bf0`

## callees

- `0x1000b200`
- `0x10014070`
- `0x10014270`

## pseudocode

```c
int __stdcall ISAMDBDeleteTable(int a1, _DWORD *a2)
{
  _DWORD *v2; // ebx
  _DWORD *v3; // esi
  _DWORD *v5; // ecx
  _DWORD *v6; // eax
  _DWORD *v7; // edx
  _DWORD *v8; // edi
  int v9; // ecx
  int v10; // eax

  v2 = 0;
  v3 = *(_DWORD **)(a1 + 52);
  if ( !v3 )
    return -1310;
  while ( v3 != a2 )
  {
    v2 = v3;
    v3 = (_DWORD *)*v3;
    if ( !v3 )
      return -1310;
  }
  ISAMDBDeleteColumns(v3);
  v5 = (_DWORD *)v3[217];
  if ( v5 )
  {
    do
    {
      v6 = (_DWORD *)v3[217];
      v7 = 0;
      v8 = (_DWORD *)*v5;
      if ( v6 )
      {
        while ( v6 != v5 )
        {
          v7 = v6;
          v6 = (_DWORD *)*v6;
          if ( !v6 )
            goto LABEL_14;
        }
        v9 = *v6;
        if ( v7 )
          *v7 = v9;
        else
          v3[217] = v9;
        MemFree(v6);
      }
LABEL_14:
      v5 = v8;
    }
    while ( v8 );
  }
  v10 = *v3;
  if ( v2 )
    *v2 = v10;
  else
    *(_DWORD *)(a1 + 52) = v10;
  MemFree(v3);
  return 0;
}

```

## disassembly

```asm
0x10014270  push    ebx
0x10014271  push    ebp
0x10014272  mov     ebp, [esp+8+arg_0]
0x10014276  xor     ebx, ebx
0x10014278  push    esi
0x10014279  mov     esi, [ebp+34h]
0x1001427c  test    esi, esi
0x1001427e  jz      short loc_10014290
0x10014280  mov     eax, [esp+0Ch+arg_4]
0x10014284  cmp     esi, eax
0x10014286  jz      short loc_1001429B
0x10014288  mov     ebx, esi
0x1001428a  mov     esi, [esi]
0x1001428c  test    esi, esi
0x1001428e  jnz     short loc_10014284
0x10014290  pop     esi
0x10014291  pop     ebp
0x10014292  mov     eax, 0FFFFFAE2h
0x10014297  pop     ebx
0x10014298  retn    8
0x1001429b  push    esi
0x1001429c  call    _ISAMDBDeleteColumns@4; ISAMDBDeleteColumns(x)
0x100142a1  mov     ecx, [esi+364h]
0x100142a7  test    ecx, ecx
0x100142a9  jz      short loc_100142EB
0x100142ab  push    edi
0x100142ac  lea     esp, [esp+0]
0x100142b0  mov     eax, [esi+364h]
0x100142b6  xor     edx, edx
0x100142b8  mov     edi, [ecx]
0x100142ba  test    eax, eax
0x100142bc  jz      short loc_100142E4
0x100142be  mov     edi, edi
0x100142c0  cmp     eax, ecx
0x100142c2  jz      short loc_100142CE
0x100142c4  mov     edx, eax
0x100142c6  mov     eax, [eax]
0x100142c8  test    eax, eax
0x100142ca  jnz     short loc_100142C0
0x100142cc  jmp     short loc_100142E4
0x100142ce  mov     ecx, [eax]
0x100142d0  test    edx, edx
0x100142d2  jnz     short loc_100142DC
0x100142d4  mov     [esi+364h], ecx
0x100142da  jmp     short loc_100142DE
0x100142dc  mov     [edx], ecx
0x100142de  push    eax
0x100142df  call    _MemFree@4; MemFree(x)
0x100142e4  mov     ecx, edi
0x100142e6  test    edi, edi
0x100142e8  jnz     short loc_100142B0
0x100142ea  pop     edi
0x100142eb  mov     eax, [esi]
0x100142ed  test    ebx, ebx
0x100142ef  jnz     short loc_10014302
0x100142f1  push    esi
0x100142f2  mov     [ebp+34h], eax
0x100142f5  call    _MemFree@4; MemFree(x)
0x100142fa  pop     esi
0x100142fb  pop     ebp
0x100142fc  xor     eax, eax
0x100142fe  pop     ebx
0x100142ff  retn    8
0x10014302  push    esi
0x10014303  mov     [ebx], eax
0x10014305  call    _MemFree@4; MemFree(x)
0x1001430a  pop     esi
0x1001430b  pop     ebp
0x1001430c  xor     eax, eax
0x1001430e  pop     ebx
0x1001430f  retn    8
```
