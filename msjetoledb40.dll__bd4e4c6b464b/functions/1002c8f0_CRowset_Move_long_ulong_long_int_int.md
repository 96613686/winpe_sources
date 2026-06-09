# CRowset::Move(long,ulong,long &,int,int)

- ea: `0x1002c8f0`
- end: `0x1002ca16`
- name: `?Move@CRowset@@IAGJJKAAJHH@Z`
- size: `294`
- prototype: `int(CRowset *__hidden this, int, unsigned int, int *, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x10028340`
- `0x100304b0`
- `0x10031240`

## callees

- `0x1002c700`
- `0x1002c8f0`

## import_xrefs

- `msjet40!__imp__JetGetBookmark@20` at `0x1002c9d4`
- `msjet40!__imp__JetGetBookmark@20` at `0x1002c9d4`
- `msjet40!__imp__JetMove@16` at `0x1002c910`
- `msjet40!__imp__JetMove@16` at `0x1002c941`
- `msjet40!__imp__JetMove@16` at `0x1002c910`
- `msjet40!__imp__JetMove@16` at `0x1002c941`

## pseudocode

```c
int __userpurge CRowset::Move@<eax>(
        int a1@<edx>,
        _DWORD *a2@<ecx>,
        CRowset *this,
        JET_ERR *a4,
        unsigned int a5,
        int *a6,
        int a7,
        int a8)
{
  JET_SESID v10; // ebx
  JET_ERR v11; // eax
  bool v12; // sf
  _BYTE *v13; // edi
  JET_ERR v14; // eax
  int v16; // edi
  JET_ERR Bookmark; // eax
  unsigned int *v18; // [esp+0h] [ebp-10h]
  unsigned int v19; // [esp+4h] [ebp-Ch]
  unsigned int pcbActual; // [esp+Ch] [ebp-4h] BYREF

  v10 = *(_DWORD *)(a2[14] + 16);
  if ( a2[29] == 4 )
    return 265926;
  v11 = JetMove(v10, a2[27], a1, 0);
  *a4 = v11;
  if ( v11 )
  {
    if ( v11 != -1603 )
      return -2147467259;
    v12 = a1 < 0;
    v13 = a2 + 24;
    if ( !v12 || (*v13 & 4) != 0 )
    {
      if ( a5 == 1 )
      {
        if ( a2[31] != -1 )
          CRowset::GotoBookmark(0xFFFFFFFF, v18, v19);
        return -2147217890;
      }
    }
    else
    {
      v14 = JetMove(v10, a2[27], 0x80000000, 0);
      *a4 = v14;
      if ( v14 < 0 )
        return 265926;
    }
    if ( (*(_DWORD *)v13 & 0x80u) != 0 )
      return 265926;
    *(_DWORD *)v13 |= 4u;
    return 265926;
  }
  else
  {
    if ( a1 > 0 )
      a2[24] &= ~0x200u;
    if ( a2[33] )
    {
      v16 = 0;
      Bookmark = JetGetBookmark(*(_DWORD *)(a2[14] + 16), a2[27], a2 + 31, 4u, &pcbActual);
      if ( Bookmark < 0 )
      {
        if ( Bookmark == -1603 )
        {
          a2[31] = -1;
          return 265926;
        }
        return -2147467259;
      }
      return v16;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1002c8f0  mov     edi, edi
0x1002c8f2  push    ebp
0x1002c8f3  mov     ebp, esp
0x1002c8f5  push    ecx
0x1002c8f6  push    ebx
0x1002c8f7  push    esi; unsigned int
0x1002c8f8  mov     esi, ecx
0x1002c8fa  push    edi; unsigned int *
0x1002c8fb  mov     edi, edx
0x1002c8fd  cmp     dword ptr [esi+74h], 4
0x1002c901  mov     eax, [esi+38h]
0x1002c904  mov     ebx, [eax+10h]
0x1002c907  jz      short loc_1002C950
0x1002c909  push    0; grbit
0x1002c90b  push    edi; cRow
0x1002c90c  push    dword ptr [esi+6Ch]; tableid
0x1002c90f  push    ebx; sesid
0x1002c910  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002c916  mov     ecx, [ebp+arg_4]
0x1002c919  mov     [ecx], eax
0x1002c91b  test    eax, eax
0x1002c91d  jz      loc_1002C9AB
0x1002c923  cmp     eax, 0FFFFF9BDh
0x1002c928  jnz     short loc_1002C99D
0x1002c92a  test    edi, edi
0x1002c92c  lea     edi, [esi+60h]
0x1002c92f  jns     short loc_1002C95E
0x1002c931  test    byte ptr [edi], 4
0x1002c934  jnz     short loc_1002C95E
0x1002c936  push    0; grbit
0x1002c938  push    80000000h; cRow
0x1002c93d  push    dword ptr [esi+6Ch]; tableid
0x1002c940  push    ebx; sesid
0x1002c941  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002c947  mov     ecx, [ebp+arg_4]
0x1002c94a  mov     [ecx], eax
0x1002c94c  test    eax, eax
0x1002c94e  jns     short loc_1002C984
0x1002c950  pop     edi
0x1002c951  pop     esi
0x1002c952  mov     eax, 40EC6h
0x1002c957  pop     ebx
0x1002c958  mov     esp, ebp
0x1002c95a  pop     ebp
0x1002c95b  retn    10h
0x1002c95e  cmp     [ebp+arg_8], 1
0x1002c962  jnz     short loc_1002C984
0x1002c964  cmp     dword ptr [esi+7Ch], 0FFFFFFFFh
0x1002c968  lea     edx, [esi+7Ch]
0x1002c96b  jz      short loc_1002C976
0x1002c96d  push    0FFFFFFFFh; tableid
0x1002c96f  mov     ecx, esi
0x1002c971  call    ?GotoBookmark@CRowset@@IAGJPAKK@Z; CRowset::GotoBookmark(ulong *,ulong)
0x1002c976  pop     edi
0x1002c977  pop     esi
0x1002c978  mov     eax, 80040E1Eh
0x1002c97d  pop     ebx
0x1002c97e  mov     esp, ebp
0x1002c980  pop     ebp
0x1002c981  retn    10h
0x1002c984  mov     eax, [edi]
0x1002c986  test    al, al
0x1002c988  js      short loc_1002C950
0x1002c98a  or      eax, 4
0x1002c98d  mov     [edi], eax
0x1002c98f  mov     eax, 40EC6h
0x1002c994  pop     edi
0x1002c995  pop     esi
0x1002c996  pop     ebx
0x1002c997  mov     esp, ebp
0x1002c999  pop     ebp
0x1002c99a  retn    10h
0x1002c99d  pop     edi
0x1002c99e  pop     esi
0x1002c99f  mov     eax, 80004005h
0x1002c9a4  pop     ebx
0x1002c9a5  mov     esp, ebp
0x1002c9a7  pop     ebp
0x1002c9a8  retn    10h
0x1002c9ab  test    edi, edi
0x1002c9ad  jle     short loc_1002C9B6
0x1002c9af  and     dword ptr [esi+60h], 0FFFFFDFFh
0x1002c9b6  cmp     dword ptr [esi+84h], 0
0x1002c9bd  jz      short loc_1002CA0B
0x1002c9bf  mov     eax, [esi+38h]
0x1002c9c2  lea     ecx, [ebp+pcbActual]
0x1002c9c5  push    ecx; pcbActual
0x1002c9c6  push    4; cbMax
0x1002c9c8  lea     ebx, [esi+7Ch]
0x1002c9cb  xor     edi, edi
0x1002c9cd  push    ebx; pvBookmark
0x1002c9ce  push    dword ptr [esi+6Ch]; tableid
0x1002c9d1  push    dword ptr [eax+10h]; sesid
0x1002c9d4  call    ds:__imp__JetGetBookmark@20; JetGetBookmark(x,x,x,x,x)
0x1002c9da  test    eax, eax
0x1002c9dc  jns     short loc_1002CA00
0x1002c9de  cmp     eax, 0FFFFF9BDh
0x1002c9e3  jnz     short loc_1002C9FB
0x1002c9e5  mov     edi, 40EC6h
0x1002c9ea  mov     dword ptr [ebx], 0FFFFFFFFh
0x1002c9f0  mov     eax, edi
0x1002c9f2  pop     edi
0x1002c9f3  pop     esi
0x1002c9f4  pop     ebx
0x1002c9f5  mov     esp, ebp
0x1002c9f7  pop     ebp
0x1002c9f8  retn    10h
0x1002c9fb  mov     edi, 80004005h
0x1002ca00  mov     eax, edi
0x1002ca02  pop     edi
0x1002ca03  pop     esi
0x1002ca04  pop     ebx
0x1002ca05  mov     esp, ebp
0x1002ca07  pop     ebp
0x1002ca08  retn    10h
0x1002ca0b  xor     eax, eax
0x1002ca0d  pop     edi
0x1002ca0e  pop     esi
0x1002ca0f  pop     ebx
0x1002ca10  mov     esp, ebp
0x1002ca12  pop     ebp
0x1002ca13  retn    10h
```
