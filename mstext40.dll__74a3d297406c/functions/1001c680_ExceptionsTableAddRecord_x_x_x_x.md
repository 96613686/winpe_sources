# ExceptionsTableAddRecord(x,x,x,x)

- ea: `0x1001c680`
- end: `0x1001ca14`
- name: `_ExceptionsTableAddRecord@16`
- size: `916`
- prototype: `int __stdcall(JET_SESID *, int, const void *, char)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10015960`
- `0x1001d040`
- `0x10020080`
- `0x10021670`

## callees

- `0x1000a8c0`
- `0x1000ad60`
- `0x1001c530`
- `0x1001c680`
- `0x1001cb30`
- `0x1002b650`
- `0x1002b656`
- `0x1002b65c`
- `0x1002b662`
- `0x1002b668`
- `0x1002b66e`
- `0x1002b81a`

## pseudocode

```c
int __stdcall ExceptionsTableAddRecord(JET_SESID *a1, int a2, const void *a3, char a4)
{
  int v4; // ebp
  JET_TABLEID *v6; // ebx
  wchar_t *v7; // ecx
  int v8; // edx
  int v9; // edi
  wchar_t v10; // ax
  const wchar_t *v11; // eax
  int Table; // eax
  int v13; // ebp
  int v14; // edx
  wchar_t *v15; // ecx
  wchar_t v16; // ax
  const wchar_t *v17; // eax
  int v18; // eax
  _WORD *v19; // ecx
  _WORD *v20; // edi
  JET_SESID v22; // [esp-1Ch] [ebp-1D4h]
  JET_SESID v23; // [esp-18h] [ebp-1D0h]
  int v24; // [esp+10h] [ebp-1A8h] BYREF
  __int128 v25; // [esp+14h] [ebp-1A4h] BYREF
  __int64 v26; // [esp+24h] [ebp-194h]
  wchar_t pszDest[64]; // [esp+2Ch] [ebp-18Ch] BYREF
  __int16 v28; // [esp+ACh] [ebp-10Ch]
  wchar_t psz[66]; // [esp+130h] [ebp-88h] BYREF

  v4 = a2;
  if ( !a1 )
    return 0;
  v6 = a1 + 2;
  if ( !a1[2] )
  {
    GetLocalizedNames(a1);
    v7 = pszDest;
    v8 = 130;
    v9 = (char *)a1 - (char *)pszDest + 28;
    while ( v8 != -2147483516 )
    {
      v10 = *(wchar_t *)((char *)v7 + v9);
      if ( !v10 )
        break;
      *v7++ = v10;
      if ( !--v8 )
      {
        --v7;
        break;
      }
    }
    *v7 = 0;
    StringCchCatW(pszDest, 0x82u, L"_");
    v11 = (const wchar_t *)a1 + 79;
    if ( a1[6] != 1 )
      v11 = (const wchar_t *)(a1 + 72);
    StringCchCatW(pszDest, 0x82u, v11);
    v28 = 0;
    MakeValidJetName(pszDest, psz, 65, 0);
    Table = JetCreateTable(*a1, a1[1], psz, 0, 0, a1 + 2);
    if ( Table && Table != -1303 )
      return -5407;
    v13 = 1;
    if ( Table == -1303 )
    {
      while ( 1 )
      {
        v14 = 130;
        v15 = pszDest;
        while ( v14 != -2147483516 )
        {
          v16 = *(wchar_t *)((char *)v15 + v9);
          if ( !v16 )
            break;
          *v15++ = v16;
          if ( !--v14 )
          {
            --v15;
            break;
          }
        }
        *v15 = 0;
        StringCchCatW(pszDest, 0x82u, L"_");
        v17 = (const wchar_t *)a1 + 79;
        if ( a1[6] != 1 )
          v17 = (const wchar_t *)(a1 + 72);
        StringCchCatW(pszDest, 0x82u, v17);
        v28 = 0;
        MakeValidJetName(pszDest, psz, 65, 0);
        AppendSuffix(psz, v13++, 0x40u);
        v18 = JetCreateTable(*a1, a1[1], psz, 0, 0, a1 + 2);
        if ( !v18 )
          break;
        if ( v18 != -1303 )
          return -5407;
      }
    }
    v23 = a1[1];
    v25 = 0;
    LODWORD(v25) = 24;
    v22 = *a1;
    v26 = 0;
    if ( JetGetDatabaseInfo(v22, v23, &v24, 4, 18) )
      return -5407;
    HIDWORD(v25) = v24;
    DWORD2(v25) = 10;
    LODWORD(v26) = 510;
    if ( JetAddColumn(*a1, *v6, (char *)a1 + 418, &v25, 0, 0, a1 + 3) )
      return -5407;
    if ( JetAddColumn(*a1, *v6, a1 + 137, &v25, 0, 0, a1 + 4) )
      return -5407;
    DWORD2(v25) = 4;
    LODWORD(v26) = 4;
    if ( JetAddColumn(*a1, *v6, (char *)a1 + 678, &v25, 0, 0, a1 + 5) )
      return -5407;
    v4 = a2;
  }
  if ( JetPrepareUpdate(*a1, *v6, 0) )
    return -5408;
  v19 = (_WORD *)a1 + 65 * v4 + 404;
  v20 = v19 + 1;
  while ( *v19++ )
    ;
  if ( JetSetColumn(*a1, *v6, a1[3], (char *)a1 + 130 * v4 + 808, 2 * (v19 - v20), 0, 0)
    || JetSetColumn(*a1, *v6, a1[4], a3, 2 * wcslen((const unsigned __int16 *)a3), 0, 0)
    || JetSetColumn(*a1, *v6, a1[5], &a4, 4u, 0, 0)
    || JetUpdate(*a1, *v6, 0, 0, 0) )
  {
    JetPrepareUpdate(*a1, *v6, 3u);
    return -5408;
  }
  return 0;
}

```

## disassembly

```asm
0x1001c680  sub     esp, 1B0h
0x1001c686  mov     eax, ___security_cookie
0x1001c68b  xor     eax, esp
0x1001c68d  mov     [esp+1B0h+var_4], eax
0x1001c694  mov     eax, [esp+1B0h+arg_8]
0x1001c69b  push    ebp
0x1001c69c  mov     ebp, [esp+1B4h+arg_4]
0x1001c6a3  push    esi
0x1001c6a4  mov     esi, [esp+1B8h+arg_0]
0x1001c6ab  mov     [esp+1B8h+var_1AC], ebp
0x1001c6af  mov     [esp+1B8h+pvData], eax
0x1001c6b3  test    esi, esi
0x1001c6b5  jnz     short loc_1001C6BE
0x1001c6b7  xor     eax, eax
0x1001c6b9  jmp     loc_1001C9FB
0x1001c6be  cmp     dword ptr [esi+8], 0
0x1001c6c2  push    ebx
0x1001c6c3  lea     ebx, [esi+8]
0x1001c6c6  push    edi
0x1001c6c7  jnz     loc_1001C935
0x1001c6cd  push    esi
0x1001c6ce  call    GetLocalizedNames
0x1001c6d3  lea     ecx, [esp+1C0h+pszDest]
0x1001c6d7  mov     eax, esi
0x1001c6d9  mov     edi, ecx
0x1001c6db  mov     edx, 82h
0x1001c6e0  sub     eax, edi
0x1001c6e2  lea     edi, [eax+1Ch]
0x1001c6e5  lea     eax, [edx+7FFFFF7Ch]
0x1001c6eb  test    eax, eax
0x1001c6ed  jz      short loc_1001C703
0x1001c6ef  movzx   eax, word ptr [edi+ecx]
0x1001c6f3  test    ax, ax
0x1001c6f6  jz      short loc_1001C703
0x1001c6f8  mov     [ecx], ax
0x1001c6fb  add     ecx, 2
0x1001c6fe  dec     edx
0x1001c6ff  jnz     short loc_1001C6E5
0x1001c701  jmp     short loc_1001C707
0x1001c703  test    edx, edx
0x1001c705  jnz     short loc_1001C70A
0x1001c707  sub     ecx, 2
0x1001c70a  xor     eax, eax
0x1001c70c  push    offset asc_10002460; "_"
0x1001c711  mov     [ecx], ax
0x1001c714  lea     eax, [esp+1C4h+pszDest]
0x1001c718  push    82h; cchDest
0x1001c71d  push    eax; pszDest
0x1001c71e  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001c723  cmp     dword ptr [esi+18h], 1
0x1001c727  lea     eax, [esi+9Eh]
0x1001c72d  jz      short loc_1001C735
0x1001c72f  lea     eax, [esi+120h]
0x1001c735  push    eax; pszSrc
0x1001c736  push    82h; cchDest
0x1001c73b  lea     eax, [esp+1C8h+pszDest]
0x1001c73f  push    eax; pszDest
0x1001c740  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001c745  xor     eax, eax
0x1001c747  push    eax; CodePage
0x1001c748  mov     [esp+1C4h+var_10C], ax
0x1001c750  lea     eax, [esp+1C4h+psz]
0x1001c757  push    41h ; 'A'; cchWideChar
0x1001c759  push    eax; pszDest
0x1001c75a  lea     eax, [esp+1CCh+pszDest]
0x1001c75e  push    eax; lpWideCharStr
0x1001c75f  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1001c764  push    ebx
0x1001c765  push    0
0x1001c767  push    0
0x1001c769  lea     eax, [esp+1CCh+psz]
0x1001c770  push    eax
0x1001c771  push    dword ptr [esi+4]
0x1001c774  push    dword ptr [esi]
0x1001c776  call    _JetCreateTable@24; JetCreateTable(x,x,x,x,x,x)
0x1001c77b  test    eax, eax
0x1001c77d  jz      short loc_1001C78A
0x1001c77f  cmp     eax, 0FFFFFAE9h
0x1001c784  jnz     loc_1001C866
0x1001c78a  mov     ebp, 1
0x1001c78f  cmp     eax, 0FFFFFAE9h
0x1001c794  jnz     loc_1001C870
0x1001c79a  lea     ebx, [ebx+0]
0x1001c7a0  mov     edx, 82h
0x1001c7a5  lea     ecx, [esp+1C0h+pszDest]
0x1001c7a9  lea     esp, [esp+0]
0x1001c7b0  lea     eax, [edx+7FFFFF7Ch]
0x1001c7b6  test    eax, eax
0x1001c7b8  jz      short loc_1001C7CE
0x1001c7ba  movzx   eax, word ptr [edi+ecx]
0x1001c7be  test    ax, ax
0x1001c7c1  jz      short loc_1001C7CE
0x1001c7c3  mov     [ecx], ax
0x1001c7c6  add     ecx, 2
0x1001c7c9  dec     edx
0x1001c7ca  jnz     short loc_1001C7B0
0x1001c7cc  jmp     short loc_1001C7D2
0x1001c7ce  test    edx, edx
0x1001c7d0  jnz     short loc_1001C7D5
0x1001c7d2  sub     ecx, 2
0x1001c7d5  xor     eax, eax
0x1001c7d7  push    offset asc_10002460; "_"
0x1001c7dc  mov     [ecx], ax
0x1001c7df  lea     eax, [esp+1C4h+pszDest]
0x1001c7e3  push    82h; cchDest
0x1001c7e8  push    eax; pszDest
0x1001c7e9  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001c7ee  cmp     dword ptr [esi+18h], 1
0x1001c7f2  lea     eax, [esi+9Eh]
0x1001c7f8  jz      short loc_1001C800
0x1001c7fa  lea     eax, [esi+120h]
0x1001c800  push    eax; pszSrc
0x1001c801  push    82h; cchDest
0x1001c806  lea     eax, [esp+1C8h+pszDest]
0x1001c80a  push    eax; pszDest
0x1001c80b  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001c810  xor     eax, eax
0x1001c812  push    eax; CodePage
0x1001c813  mov     [esp+1C4h+var_10C], ax
0x1001c81b  lea     eax, [esp+1C4h+psz]
0x1001c822  push    41h ; 'A'; cchWideChar
0x1001c824  push    eax; pszDest
0x1001c825  lea     eax, [esp+1CCh+pszDest]
0x1001c829  push    eax; lpWideCharStr
0x1001c82a  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1001c82f  push    40h ; '@'; cchMax
0x1001c831  push    ebp; int
0x1001c832  lea     eax, [esp+1C8h+psz]
0x1001c839  push    eax; psz
0x1001c83a  call    AppendSuffix
0x1001c83f  push    ebx
0x1001c840  push    0
0x1001c842  push    0
0x1001c844  lea     eax, [esp+1CCh+psz]
0x1001c84b  inc     ebp
0x1001c84c  push    eax
0x1001c84d  push    dword ptr [esi+4]
0x1001c850  push    dword ptr [esi]
0x1001c852  call    _JetCreateTable@24; JetCreateTable(x,x,x,x,x,x)
0x1001c857  test    eax, eax
0x1001c859  jz      short loc_1001C870
0x1001c85b  cmp     eax, 0FFFFFAE9h
0x1001c860  jz      loc_1001C7A0
0x1001c866  mov     eax, 0FFFFEAE1h
0x1001c86b  jmp     loc_1001C9F9
0x1001c870  push    12h
0x1001c872  push    4
0x1001c874  lea     eax, [esp+1C8h+var_1A8]
0x1001c878  xorps   xmm0, xmm0
0x1001c87b  push    eax
0x1001c87c  push    dword ptr [esi+4]
0x1001c87f  movdqu  [esp+1D0h+var_1A4], xmm0
0x1001c885  mov     dword ptr [esp+1D0h+var_1A4], 18h
0x1001c88d  push    dword ptr [esi]
0x1001c88f  movq    [esp+1D4h+var_194], xmm0
0x1001c895  call    _JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001c89a  test    eax, eax
0x1001c89c  jnz     short loc_1001C866
0x1001c89e  mov     eax, [esp+1C0h+var_1A8]
0x1001c8a2  mov     dword ptr [esp+1C0h+var_1A4+0Ch], eax
0x1001c8a6  lea     eax, [esi+0Ch]
0x1001c8a9  push    eax
0x1001c8aa  push    0
0x1001c8ac  push    0
0x1001c8ae  lea     eax, [esp+1CCh+var_1A4]
0x1001c8b2  mov     dword ptr [esp+1CCh+var_1A4+8], 0Ah
0x1001c8ba  push    eax
0x1001c8bb  lea     eax, [esi+1A2h]
0x1001c8c1  mov     dword ptr [esp+1D0h+var_194], 1FEh
0x1001c8c9  push    eax
0x1001c8ca  push    dword ptr [ebx]
0x1001c8cc  push    dword ptr [esi]
0x1001c8ce  call    _JetAddColumn@28; JetAddColumn(x,x,x,x,x,x,x)
0x1001c8d3  test    eax, eax
0x1001c8d5  jnz     short loc_1001C866
0x1001c8d7  lea     eax, [esi+10h]
0x1001c8da  push    eax
0x1001c8db  push    0
0x1001c8dd  push    0
0x1001c8df  lea     eax, [esp+1CCh+var_1A4]
0x1001c8e3  push    eax
0x1001c8e4  lea     eax, [esi+224h]
0x1001c8ea  push    eax
0x1001c8eb  push    dword ptr [ebx]
0x1001c8ed  push    dword ptr [esi]
0x1001c8ef  call    _JetAddColumn@28; JetAddColumn(x,x,x,x,x,x,x)
0x1001c8f4  test    eax, eax
0x1001c8f6  jnz     loc_1001C866
0x1001c8fc  lea     eax, [esi+14h]
0x1001c8ff  mov     dword ptr [esp+1C0h+var_1A4+8], 4
0x1001c907  push    eax
0x1001c908  push    0
0x1001c90a  push    0
0x1001c90c  lea     eax, [esp+1CCh+var_1A4]
0x1001c910  mov     dword ptr [esp+1CCh+var_194], 4
0x1001c918  push    eax
0x1001c919  lea     eax, [esi+2A6h]
0x1001c91f  push    eax
0x1001c920  push    dword ptr [ebx]
0x1001c922  push    dword ptr [esi]
0x1001c924  call    _JetAddColumn@28; JetAddColumn(x,x,x,x,x,x,x)
0x1001c929  test    eax, eax
0x1001c92b  jnz     loc_1001C866
0x1001c931  mov     ebp, [esp+1C0h+var_1AC]
0x1001c935  push    0; prep
0x1001c937  push    dword ptr [ebx]; tableid
0x1001c939  push    dword ptr [esi]; sesid
0x1001c93b  call    _JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1001c940  test    eax, eax
0x1001c942  jnz     loc_1001C9F0
0x1001c948  imul    eax, ebp, 82h
0x1001c94e  lea     edx, [esi+328h]
0x1001c954  add     edx, eax
0x1001c956  mov     ecx, edx
0x1001c958  lea     edi, [ecx+2]
0x1001c95b  jmp     short loc_1001C960
0x1001c960  mov     ax, [ecx]
0x1001c963  add     ecx, 2
0x1001c966  test    ax, ax
0x1001c969  jnz     short loc_1001C960
0x1001c96b  sub     ecx, edi
0x1001c96d  push    0; psetinfo
0x1001c96f  sar     ecx, 1
0x1001c971  push    0; grbit
0x1001c973  lea     eax, [ecx+ecx]
0x1001c976  push    eax; cbData
0x1001c977  push    edx; pvData
0x1001c978  push    dword ptr [esi+0Ch]; columnid
0x1001c97b  push    dword ptr [ebx]; tableid
0x1001c97d  push    dword ptr [esi]; sesid
0x1001c97f  call    _JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1001c984  test    eax, eax
0x1001c986  jnz     short loc_1001C9E5
0x1001c988  mov     edi, [esp+1C0h+pvData]
0x1001c98c  mov     ecx, edi
0x1001c98e  lea     edx, [ecx+2]
0x1001c991  mov     ax, [ecx]
0x1001c994  add     ecx, 2
0x1001c997  test    ax, ax
0x1001c99a  jnz     short loc_1001C991
0x1001c99c  sub     ecx, edx
0x1001c99e  push    0; psetinfo
0x1001c9a0  sar     ecx, 1
0x1001c9a2  push    0; grbit
0x1001c9a4  lea     eax, [ecx+ecx]
0x1001c9a7  push    eax; cbData
0x1001c9a8  push    edi; pvData
0x1001c9a9  push    dword ptr [esi+10h]; columnid
0x1001c9ac  push    dword ptr [ebx]; tableid
0x1001c9ae  push    dword ptr [esi]; sesid
0x1001c9b0  call    _JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1001c9b5  test    eax, eax
0x1001c9b7  jnz     short loc_1001C9E5
0x1001c9b9  push    eax; psetinfo
0x1001c9ba  push    eax; grbit
0x1001c9bb  push    4; cbData
0x1001c9bd  lea     eax, [esp+1CCh+arg_C]
0x1001c9c4  push    eax; pvData
0x1001c9c5  push    dword ptr [esi+14h]; columnid
0x1001c9c8  push    dword ptr [ebx]; tableid
0x1001c9ca  push    dword ptr [esi]; sesid
0x1001c9cc  call    _JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1001c9d1  test    eax, eax
0x1001c9d3  jnz     short loc_1001C9E5
0x1001c9d5  push    eax; pcbActual
0x1001c9d6  push    eax; cbBookmark
0x1001c9d7  push    eax; pvBookmark
0x1001c9d8  push    dword ptr [ebx]; tableid
0x1001c9da  push    dword ptr [esi]; sesid
0x1001c9dc  call    _JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1001c9e1  test    eax, eax
0x1001c9e3  jz      short loc_1001C9F7
0x1001c9e5  push    3; prep
0x1001c9e7  push    dword ptr [ebx]; tableid
0x1001c9e9  push    dword ptr [esi]; sesid
0x1001c9eb  call    _JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1001c9f0  mov     eax, 0FFFFEAE0h
0x1001c9f5  jmp     short loc_1001C9F9
0x1001c9f7  xor     eax, eax
0x1001c9f9  pop     edi
0x1001c9fa  pop     ebx
0x1001c9fb  mov     ecx, [esp+1B8h+var_4]
0x1001ca02  pop     esi
0x1001ca03  pop     ebp
0x1001ca04  xor     ecx, esp; StackCookie
0x1001ca06  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ca0b  add     esp, 1B0h
0x1001ca11  retn    10h
```
