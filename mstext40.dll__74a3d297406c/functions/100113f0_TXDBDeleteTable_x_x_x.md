# TXDBDeleteTable(x,x,x)

- ea: `0x100113f0`
- end: `0x10011650`
- name: `_TXDBDeleteTable@12`
- size: `608`
- prototype: `int __stdcall(int, int, STRSAFE_LPCWSTR)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x1000a1f0`
- `0x1000a350`
- `0x1000a470`
- `0x1000ad60`
- `0x1000b3f0`
- `0x1000b5f0`
- `0x1000b9b0`
- `0x100108e0`
- `0x100113f0`
- `0x10014270`
- `0x100145a0`
- `0x1001c140`
- `0x1001ca20`
- `0x1001efc0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TXDBDeleteTable(int a1, int a2, STRSAFE_LPCWSTR a3)
{
  int v3; // eax
  int v4; // esi
  int result; // eax
  int v6; // edi
  int v7; // ebx
  wchar_t *v8; // ecx
  int v9; // edx
  int v10; // ebp
  wchar_t v11; // ax
  int v12; // edx
  wchar_t *v13; // ecx
  wchar_t v14; // ax
  const wchar_t *v15; // esi
  int v16; // esi
  HANDLE hObject; // [esp+Ch] [ebp-218h] BYREF
  int v18; // [esp+10h] [ebp-214h] BYREF
  wchar_t pszDest[262]; // [esp+14h] [ebp-210h] BYREF

  v3 = ISAMDBFindDatabaseUser(a1, a2);
  v4 = v3;
  if ( !v3 )
    return -1010;
  if ( (*(_BYTE *)(v3 + 892) & 1) != 0 )
    return -1809;
  v6 = *(_DWORD *)(v3 + 4);
  if ( *(_DWORD *)(v6 + 8) == 1 )
    return -1809;
  result = LocateTableInDatabase(v3, a3, (int)&v18, 1);
  if ( !result )
  {
    v7 = v18;
    if ( *(_DWORD *)(v18 + 8) || *(_DWORD *)(v18 + 880) == 1 )
    {
      ErrorSetExtendedInfoSz2(-8154, a3, 1);
      return -1304;
    }
    v8 = pszDest;
    v9 = 261;
    v10 = v6 - (_DWORD)pszDest + 56;
    while ( v9 != -2147483385 )
    {
      v11 = *(wchar_t *)((char *)v8 + v10);
      if ( !v11 )
        break;
      *v8++ = v11;
      if ( !--v9 )
      {
        --v8;
        break;
      }
    }
    *v8 = 0;
    StringCchCatW(pszDest, 0x105u, (STRSAFE_LPCWSTR)(v7 + 920));
    if ( DOSOpenFile(pszDest, 2, (int)&hObject) )
    {
      ISAMDBDeleteTable(v6, v7);
      ErrorSetExtendedInfoSz1(-8160, a3, 1);
      return -1032;
    }
    DOSCloseFile(hObject);
    if ( !IsAcceptableFileName(pszDest) )
      return -1809;
    if ( *(_DWORD *)(v4 + 12) != 1 || !*(_DWORD *)(v4 + 20) )
    {
      v12 = 261;
      v13 = pszDest;
      while ( v12 != -2147483385 )
      {
        v14 = *(wchar_t *)((char *)v13 + v10);
        if ( !v14 )
          break;
        *v13++ = v14;
        if ( !--v12 )
        {
          --v13;
          break;
        }
      }
      *v13 = 0;
      if ( *(_DWORD *)(v4 + 12) == 1 )
      {
        if ( *(_DWORD *)(v4 + 20) )
        {
LABEL_36:
          StringCchCatW(pszDest, 0x105u, L"schema.ini");
          v15 = (const wchar_t *)(v7 + 920);
          TextSpecDelete(pszDest, (LPCWCH)(v7 + 920), v7, 0);
          goto LABEL_33;
        }
      }
      else if ( *(_WORD *)(v6 + 36) != 1 && *(_DWORD *)(v6 + 32) != 1 )
      {
        goto LABEL_36;
      }
      StringCchCatW(pszDest, 0x105u, L"export.ini");
      DOSFileDelete(pszDest);
    }
    v15 = (const wchar_t *)(v7 + 920);
LABEL_33:
    v16 = TextDeleteFile(*(_DWORD *)(v6 + 28), v15);
    if ( *(_DWORD *)(v7 + 900) <= 1u )
      ExceptionsTableClose(*(_DWORD *)(v7 + 908));
    ISAMDBDeleteTable(v6, v7);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x100113f0  sub     esp, 21Ch
0x100113f6  mov     eax, ___security_cookie
0x100113fb  xor     eax, esp
0x100113fd  mov     [esp+21Ch+var_4], eax
0x10011404  mov     eax, [esp+21Ch+arg_4]
0x1001140b  mov     ecx, [esp+21Ch+arg_0]
0x10011412  push    ebp
0x10011413  mov     ebp, [esp+220h+arg_8]
0x1001141a  push    esi
0x1001141b  push    eax
0x1001141c  push    ecx
0x1001141d  mov     [esp+22Ch+pszSrc], ebp
0x10011421  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x10011426  mov     esi, eax
0x10011428  test    esi, esi
0x1001142a  jnz     short loc_10011436
0x1001142c  mov     eax, 0FFFFFC0Eh
0x10011431  jmp     loc_10011637
0x10011436  test    byte ptr [esi+37Ch], 1
0x1001143d  jz      short loc_10011449
0x1001143f  mov     eax, 0FFFFF8EFh
0x10011444  jmp     loc_10011637
0x10011449  push    edi
0x1001144a  mov     edi, [esi+4]
0x1001144d  cmp     dword ptr [edi+8], 1
0x10011451  jnz     short loc_1001145D
0x10011453  mov     eax, 0FFFFF8EFh
0x10011458  jmp     loc_10011636
0x1001145d  push    1; int
0x1001145f  lea     eax, [esp+22Ch+var_214]
0x10011463  push    eax; int
0x10011464  push    ebp; STRSAFE_LPCWSTR
0x10011465  push    esi; int
0x10011466  call    _LocateTableInDatabase@16; LocateTableInDatabase(x,x,x,x)
0x1001146b  test    eax, eax
0x1001146d  jnz     loc_10011636
0x10011473  push    ebx
0x10011474  mov     ebx, [esp+22Ch+var_214]
0x10011478  cmp     [ebx+8], eax
0x1001147b  jnz     loc_10011623
0x10011481  cmp     dword ptr [ebx+370h], 1
0x10011488  jz      loc_10011623
0x1001148e  lea     ecx, [esp+22Ch+pszDest]
0x10011492  mov     eax, edi
0x10011494  mov     ebp, ecx
0x10011496  mov     edx, 105h
0x1001149b  sub     eax, ebp
0x1001149d  lea     ebp, [eax+38h]
0x100114a0  lea     eax, [edx+7FFFFEF9h]
0x100114a6  test    eax, eax
0x100114a8  jz      short loc_100114BE
0x100114aa  movzx   eax, word ptr [ecx+ebp]
0x100114ae  test    ax, ax
0x100114b1  jz      short loc_100114BE
0x100114b3  mov     [ecx], ax
0x100114b6  add     ecx, 2
0x100114b9  dec     edx
0x100114ba  jnz     short loc_100114A0
0x100114bc  jmp     short loc_100114C2
0x100114be  test    edx, edx
0x100114c0  jnz     short loc_100114C5
0x100114c2  sub     ecx, 2
0x100114c5  xor     eax, eax
0x100114c7  mov     [ecx], ax
0x100114ca  lea     eax, [ebx+398h]
0x100114d0  push    eax; pszSrc
0x100114d1  push    105h; cchDest
0x100114d6  lea     eax, [esp+234h+pszDest]
0x100114da  push    eax; pszDest
0x100114db  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x100114e0  lea     eax, [esp+22Ch+hObject]
0x100114e4  push    eax; int
0x100114e5  push    2; int
0x100114e7  lea     eax, [esp+234h+pszDest]
0x100114eb  push    eax; lpFileName
0x100114ec  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x100114f1  test    eax, eax
0x100114f3  jz      short loc_10011516
0x100114f5  push    ebx
0x100114f6  push    edi
0x100114f7  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x100114fc  push    1; int
0x100114fe  push    [esp+230h+pszSrc]; pszSrc
0x10011502  push    0FFFFE020h; int
0x10011507  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1001150c  mov     eax, 0FFFFFBF8h
0x10011511  jmp     loc_10011635
0x10011516  push    [esp+22Ch+hObject]; hObject
0x1001151a  call    _DOSCloseFile@4; DOSCloseFile(x)
0x1001151f  lea     eax, [esp+22Ch+pszDest]
0x10011523  push    eax; pszSrc
0x10011524  call    _IsAcceptableFileName@4; IsAcceptableFileName(x)
0x10011529  test    eax, eax
0x1001152b  jnz     short loc_10011537
0x1001152d  mov     eax, 0FFFFF8EFh
0x10011532  jmp     loc_10011635
0x10011537  cmp     dword ptr [esi+0Ch], 1
0x1001153b  jnz     short loc_10011547
0x1001153d  cmp     dword ptr [esi+14h], 0
0x10011541  jnz     loc_100115C3
0x10011547  mov     edx, 105h
0x1001154c  lea     ecx, [esp+22Ch+pszDest]
0x10011550  lea     eax, [edx+7FFFFEF9h]
0x10011556  test    eax, eax
0x10011558  jz      short loc_1001156E
0x1001155a  movzx   eax, word ptr [ecx+ebp]
0x1001155e  test    ax, ax
0x10011561  jz      short loc_1001156E
0x10011563  mov     [ecx], ax
0x10011566  add     ecx, 2
0x10011569  dec     edx
0x1001156a  jnz     short loc_10011550
0x1001156c  jmp     short loc_10011572
0x1001156e  test    edx, edx
0x10011570  jnz     short loc_10011575
0x10011572  sub     ecx, 2
0x10011575  xor     eax, eax
0x10011577  mov     [ecx], ax
0x1001157a  mov     eax, [esi+0Ch]
0x1001157d  cmp     eax, 1
0x10011580  jnz     short loc_1001158C
0x10011582  cmp     dword ptr [esi+14h], 0
0x10011586  jz      short loc_100115A5
0x10011588  cmp     eax, eax
0x1001158a  jz      short loc_100115F9
0x1001158c  cmp     word ptr [edi+24h], 1
0x10011591  jz      short loc_100115A5
0x10011593  cmp     eax, 1
0x10011596  jz      short loc_100115F9
0x10011598  cmp     word ptr [edi+24h], 1
0x1001159d  jz      short loc_100115F9
0x1001159f  cmp     dword ptr [edi+20h], 1
0x100115a3  jnz     short loc_100115F9
0x100115a5  push    offset aExportIni; "export.ini"
0x100115aa  push    105h; cchDest
0x100115af  lea     eax, [esp+234h+pszDest]
0x100115b3  push    eax; pszDest
0x100115b4  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x100115b9  lea     eax, [esp+22Ch+pszDest]
0x100115bd  push    eax
0x100115be  call    _DOSFileDelete@4; DOSFileDelete(x)
0x100115c3  lea     esi, [ebx+398h]
0x100115c9  push    esi; pszSrc
0x100115ca  push    dword ptr [edi+1Ch]; int
0x100115cd  call    _TextDeleteFile@8; TextDeleteFile(x,x)
0x100115d2  mov     ecx, [ebx+384h]
0x100115d8  mov     esi, eax
0x100115da  test    ecx, ecx
0x100115dc  jz      short loc_100115E3
0x100115de  cmp     ecx, 1
0x100115e1  jnz     short loc_100115EE
0x100115e3  push    dword ptr [ebx+38Ch]
0x100115e9  call    _ExceptionsTableClose@4; ExceptionsTableClose(x)
0x100115ee  push    ebx
0x100115ef  push    edi
0x100115f0  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x100115f5  mov     eax, esi
0x100115f7  jmp     short loc_10011635
0x100115f9  push    offset aSchemaIni_0; "schema.ini"
0x100115fe  push    105h; cchDest
0x10011603  lea     eax, [esp+234h+pszDest]
0x10011607  push    eax; pszDest
0x10011608  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001160d  push    0; int
0x1001160f  push    ebx; int
0x10011610  lea     esi, [ebx+398h]
0x10011616  push    esi; lpWideCharStr
0x10011617  lea     eax, [esp+238h+pszDest]
0x1001161b  push    eax; lpFileName
0x1001161c  call    _TextSpecDelete@16; TextSpecDelete(x,x,x,x)
0x10011621  jmp     short loc_100115C9
0x10011623  push    1; int
0x10011625  push    ebp; pszSrc
0x10011626  push    0FFFFE026h; int
0x1001162b  call    _ErrorSetExtendedInfoSz2@12; ErrorSetExtendedInfoSz2(x,x,x)
0x10011630  mov     eax, 0FFFFFAE8h
0x10011635  pop     ebx
0x10011636  pop     edi
0x10011637  mov     ecx, [esp+224h+var_4]
0x1001163e  pop     esi
0x1001163f  pop     ebp
0x10011640  xor     ecx, esp; StackCookie
0x10011642  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10011647  add     esp, 21Ch
0x1001164d  retn    0Ch
```
