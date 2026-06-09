# ErrREPDetectMoveCopy(x,x,x,x)

- ea: `0x1011bb70`
- end: `0x1011c0ca`
- name: `_ErrREPDetectMoveCopy@16`
- size: `1370`
- prototype: `int __stdcall(Session *, int, int, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10117340`

## callees

- `0x10012a80`
- `0x10043060`
- `0x100437f0`
- `0x10044240`
- `0x10044a70`
- `0x10044d80`
- `0x10044f80`
- `0x1004d920`
- `0x1004d9c0`
- `0x1004da20`
- `0x1011bae0`
- `0x1011bb70`
- `0x1012081d`
- `0x101214c2`
- `0x10121870`
- `0x1012193b`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1011bfd0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1011bfd0`

## string_xrefs

- `0x1011bced`: `UNCPathname`
- `0x1011be31`: `UNCPathname`
- `0x1011c047`: `UNCPathname`
- `0x1011bc96`: `Pathname`
- `0x1011bec7`: `Pathname`

## pseudocode

```c
int __stdcall ErrREPDetectMoveCopy(Session *a1, int a2, int a3, _DWORD *a4)
{
  int result; // eax
  int DatabaseInfo; // esi
  int v6; // eax
  unsigned int v7; // kr00_4
  WCHAR *v8; // ecx
  __int16 v9; // ax
  WCHAR *p_pszDest; // ecx
  int v12; // eax
  unsigned int i; // ebx
  int v14; // eax
  int v16; // [esp+10h] [ebp-928h] BYREF
  int v17; // [esp+14h] [ebp-924h]
  _DWORD *v18; // [esp+18h] [ebp-920h]
  int v19; // [esp+1Ch] [ebp-91Ch] BYREF
  int v20; // [esp+20h] [ebp-918h] BYREF
  int v21; // [esp+24h] [ebp-914h]
  _BYTE v22[4]; // [esp+28h] [ebp-910h] BYREF
  int v23; // [esp+2Ch] [ebp-90Ch]
  WCHAR v24[52]; // [esp+40h] [ebp-8F8h] BYREF
  WCHAR pszDest; // [esp+A8h] [ebp-890h] BYREF
  __int16 v26; // [esp+AAh] [ebp-88Eh] BYREF
  WCHAR v27; // [esp+2B0h] [ebp-688h] BYREF
  __int16 v28; // [esp+2B2h] [ebp-686h] BYREF
  WCHAR szLongPath[260]; // [esp+4B8h] [ebp-480h] BYREF
  int v30[26]; // [esp+6C0h] [ebp-278h] BYREF
  WCHAR v31[262]; // [esp+728h] [ebp-210h] BYREF

  v18 = a4;
  v21 = 0;
  v19 = 0;
  result = ErrIsamBeginTransaction(a1);
  if ( result >= 0 )
  {
    DatabaseInfo = ErrDispGetDatabaseInfo(a1, a2, &v19, 4, 6);
    if ( DatabaseInfo < 0 )
    {
LABEL_61:
      ErrIsamRollback(a1, 0);
      return DatabaseInfo;
    }
    v17 = v19 & 1;
    *v18 = 0;
    v6 = ErrREPGetFullDbpath((int)a1, a2, (int)v30, 49, (int)v31, 260, &pszDest, 260, (int)&v20);
    DatabaseInfo = v6;
    if ( v6 != -20019 )
    {
      if ( v6 < 0 )
        goto LABEL_61;
      DatabaseInfo = ErrDispGetTableColumnInfo(a1, a3, L"Machinename", v22, 24, 0);
      if ( DatabaseInfo < 0 )
        goto LABEL_61;
      DatabaseInfo = ErrDispRetrieveColumn(a1, a3, v23, v24, 97, &v16, 0, 0);
      if ( DatabaseInfo < 0 )
        goto LABEL_61;
      *(WCHAR *)((char *)v24 + v16) = 0;
      if ( !WCSICMP(v24, v30) )
      {
        DatabaseInfo = ErrDispGetTableColumnInfo(a1, a3, L"Pathname", v22, 24, 0);
        if ( DatabaseInfo < 0 )
          goto LABEL_61;
        DatabaseInfo = ErrDispRetrieveColumn(a1, a3, v23, szLongPath, 519, &v16, 0, 0);
        if ( DatabaseInfo < 0 )
          goto LABEL_61;
        *(WCHAR *)((char *)szLongPath + v16) = 0;
        DatabaseInfo = ErrDispGetTableColumnInfo(a1, a3, L"UNCPathname", v22, 24, 0);
        if ( DatabaseInfo < 0 )
          goto LABEL_61;
        DatabaseInfo = ErrDispRetrieveColumn(a1, a3, v23, &v27, 519, &v16, 0, 0);
        if ( DatabaseInfo < 0 )
          goto LABEL_61;
        *(WCHAR *)((char *)&v27 + v16) = 0;
        if ( szLongPath[0] || v27 )
        {
          if ( v20 )
          {
            if ( szLongPath[0] )
            {
              if ( !ComparePathStrings(szLongPath, v31, 1) )
              {
                if ( !pszDest )
                  goto LABEL_44;
                if ( v27 && (!ComparePathStrings(&pszDest, &v27, 1) || FValidateShareName(&v27)) )
                {
                  v7 = wcslen(&pszDest);
                  v8 = &v27;
                  do
                    v9 = *v8++;
                  while ( v9 != (_WORD)v21 );
                  if ( v7 >= ((char *)v8 - (char *)&v28) >> 1 )
                    goto LABEL_44;
                }
                if ( v17 )
                  goto LABEL_44;
                DatabaseInfo = ErrDispPrepareUpdate2(a1, a3, 2);
                if ( DatabaseInfo < 0 )
                  goto LABEL_61;
                DatabaseInfo = ErrDispGetTableColumnInfo(a1, a3, L"UNCPathname", v22, 24, 0);
                if ( DatabaseInfo < 0 )
                  goto LABEL_61;
                p_pszDest = &pszDest;
                while ( *p_pszDest++ )
                  ;
                goto LABEL_58;
              }
            }
            else if ( ResolveRemotePathToLocalName(&v27, szLongPath, 260) && !ComparePathStrings(v31, szLongPath, 1) )
            {
              if ( v17 )
                goto LABEL_44;
              DatabaseInfo = ErrDispPrepareUpdate2(a1, a3, 2);
              if ( DatabaseInfo < 0 )
                goto LABEL_61;
              DatabaseInfo = ErrDispGetTableColumnInfo(a1, a3, L"Pathname", v22, 24, 0);
              if ( DatabaseInfo < 0 )
                goto LABEL_61;
              v12 = ErrDispSetColumn(a1, a3, v23, szLongPath, 2 * wcslen(szLongPath), 0, 0);
              goto LABEL_59;
            }
          }
          else if ( v27 )
          {
            if ( !ComparePathStrings(&v27, &pszDest, 1) )
              goto LABEL_44;
            if ( !ComparePathFindData(&v27, &pszDest) )
            {
              *v18 = 0;
              goto LABEL_44;
            }
            if ( ResolveRemotePathToLocalName(&v27, szLongPath, 260)
              && ResolveRemotePathToLocalName(&pszDest, v31, 260)
              && !ComparePathStrings(v31, szLongPath, 1) )
            {
              goto LABEL_44;
            }
          }
          else if ( ResolveRemotePathToLocalName(&pszDest, v31, 260) && !ComparePathStrings(v31, szLongPath, 1) )
          {
            if ( v17 )
              goto LABEL_44;
            DatabaseInfo = ErrDispPrepareUpdate2(a1, a3, 2);
            if ( DatabaseInfo < 0 )
              goto LABEL_61;
            DatabaseInfo = ErrDispGetTableColumnInfo(a1, a3, L"UNCPathname", v22, 24, 0);
            if ( DatabaseInfo < 0 )
              goto LABEL_61;
            p_pszDest = &pszDest;
            while ( *p_pszDest++ )
              ;
LABEL_58:
            v12 = ErrDispSetColumn(a1, a3, v23, &pszDest, 2 * (((char *)p_pszDest - (char *)&v26) >> 1), 0, 0);
LABEL_59:
            DatabaseInfo = v12;
            if ( v12 < 0 )
              goto LABEL_61;
            DatabaseInfo = ErrDispUpdate(a1, a3, 0, 0, 0);
            if ( DatabaseInfo < 0 )
              goto LABEL_61;
LABEL_44:
            for ( i = 0; i < 0x78; ++i )
            {
              v14 = ErrIsamCommitTransaction(a1, 1u);
              DatabaseInfo = v14;
              if ( v14 != -1106 && v14 != -1105 && v14 != -1102 )
                break;
              Sleep(0x1F4u);
            }
            if ( DatabaseInfo >= 0 )
              return 0;
            goto LABEL_61;
          }
        }
      }
    }
    *v18 = 1;
    goto LABEL_44;
  }
  return result;
}

```

## disassembly

```asm
0x1011bb70  mov     edi, edi
0x1011bb72  push    ebp
0x1011bb73  mov     ebp, esp
0x1011bb75  and     esp, 0FFFFFFF8h
0x1011bb78  sub     esp, 92Ch
0x1011bb7e  mov     eax, ___security_cookie
0x1011bb83  xor     eax, esp
0x1011bb85  mov     [esp+92Ch+var_4], eax
0x1011bb8c  mov     eax, [ebp+arg_C]
0x1011bb8f  push    ebx
0x1011bb90  push    esi
0x1011bb91  push    edi
0x1011bb92  mov     edi, [ebp+arg_0]
0x1011bb95  mov     [esp+938h+var_920], eax
0x1011bb99  xor     eax, eax
0x1011bb9b  push    edi
0x1011bb9c  mov     [esp+93Ch+var_914], eax
0x1011bba0  mov     [esp+93Ch+var_91C], eax
0x1011bba4  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x1011bba9  test    eax, eax
0x1011bbab  js      loc_1011C0B3
0x1011bbb1  push    6
0x1011bbb3  push    4
0x1011bbb5  lea     eax, [esp+940h+var_91C]
0x1011bbb9  push    eax
0x1011bbba  push    [ebp+arg_4]
0x1011bbbd  push    edi
0x1011bbbe  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1011bbc3  mov     esi, eax
0x1011bbc5  test    esi, esi
0x1011bbc7  js      loc_1011C0A9
0x1011bbcd  mov     eax, [esp+938h+var_91C]
0x1011bbd1  xor     ebx, ebx
0x1011bbd3  and     eax, 1
0x1011bbd6  mov     ecx, 104h
0x1011bbdb  mov     [esp+938h+var_924], eax
0x1011bbdf  mov     eax, [esp+938h+var_920]
0x1011bbe3  mov     [eax], ebx
0x1011bbe5  lea     eax, [esp+938h+var_918]
0x1011bbe9  push    eax; int
0x1011bbea  push    ecx; int
0x1011bbeb  lea     eax, [esp+940h+pszDest]
0x1011bbf2  push    eax; pszDest
0x1011bbf3  push    ecx; int
0x1011bbf4  lea     eax, [esp+948h+var_210]
0x1011bbfb  push    eax; int
0x1011bbfc  push    31h ; '1'; int
0x1011bbfe  lea     eax, [esp+950h+var_278]
0x1011bc05  push    eax; int
0x1011bc06  push    [ebp+arg_4]; int
0x1011bc09  push    edi; int
0x1011bc0a  call    _ErrREPGetFullDbpath@36; ErrREPGetFullDbpath(x,x,x,x,x,x,x,x,x)
0x1011bc0f  mov     esi, eax
0x1011bc11  cmp     esi, 0FFFFB1CDh
0x1011bc17  jz      loc_1011BF9D
0x1011bc1d  test    esi, esi
0x1011bc1f  js      loc_1011C0A9
0x1011bc25  push    ebx
0x1011bc26  mov     ebx, [ebp+arg_8]
0x1011bc29  lea     eax, [esp+93Ch+var_910]
0x1011bc2d  push    18h
0x1011bc2f  push    eax
0x1011bc30  push    offset _WZMachinename; "Machinename"
0x1011bc35  push    ebx
0x1011bc36  push    edi
0x1011bc37  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bc3c  mov     esi, eax
0x1011bc3e  test    esi, esi
0x1011bc40  js      loc_1011C0A9
0x1011bc46  xor     eax, eax
0x1011bc48  push    eax
0x1011bc49  push    eax
0x1011bc4a  lea     eax, [esp+940h+var_928]
0x1011bc4e  push    eax
0x1011bc4f  push    61h ; 'a'
0x1011bc51  lea     eax, [esp+948h+var_8F8]
0x1011bc55  push    eax
0x1011bc56  push    [esp+94Ch+var_90C]
0x1011bc5a  push    ebx
0x1011bc5b  push    edi
0x1011bc5c  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011bc61  mov     esi, eax
0x1011bc63  test    esi, esi
0x1011bc65  js      loc_1011C0A9
0x1011bc6b  mov     eax, [esp+938h+var_928]
0x1011bc6f  lea     edx, [esp+938h+var_278]
0x1011bc76  xor     ecx, ecx
0x1011bc78  mov     [esp+eax+938h+var_8F8], cx
0x1011bc7d  lea     ecx, [esp+938h+var_8F8]
0x1011bc81  call    _WCSICMP@8; WCSICMP(x,x)
0x1011bc86  test    eax, eax
0x1011bc88  jnz     loc_1011BF9D
0x1011bc8e  push    eax
0x1011bc8f  push    18h
0x1011bc91  lea     eax, [esp+940h+var_910]
0x1011bc95  push    eax
0x1011bc96  push    offset _WZPathname; "Pathname"
0x1011bc9b  push    ebx
0x1011bc9c  push    edi
0x1011bc9d  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bca2  mov     esi, eax
0x1011bca4  test    esi, esi
0x1011bca6  js      loc_1011C0A9
0x1011bcac  xor     eax, eax
0x1011bcae  push    eax
0x1011bcaf  push    eax
0x1011bcb0  lea     eax, [esp+940h+var_928]
0x1011bcb4  push    eax
0x1011bcb5  push    207h
0x1011bcba  lea     eax, [esp+948h+szLongPath]
0x1011bcc1  push    eax
0x1011bcc2  push    [esp+94Ch+var_90C]
0x1011bcc6  push    ebx
0x1011bcc7  push    edi
0x1011bcc8  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011bccd  mov     esi, eax
0x1011bccf  test    esi, esi
0x1011bcd1  js      loc_1011C0A9
0x1011bcd7  mov     eax, [esp+938h+var_928]
0x1011bcdb  xor     ecx, ecx
0x1011bcdd  push    ecx
0x1011bcde  push    18h
0x1011bce0  mov     [esp+eax+940h+szLongPath], cx
0x1011bce8  lea     eax, [esp+940h+var_910]
0x1011bcec  push    eax
0x1011bced  push    offset _WZUNCPathname; "UNCPathname"
0x1011bcf2  push    ebx
0x1011bcf3  push    edi
0x1011bcf4  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bcf9  mov     esi, eax
0x1011bcfb  test    esi, esi
0x1011bcfd  js      loc_1011C0A9
0x1011bd03  xor     eax, eax
0x1011bd05  push    eax
0x1011bd06  push    eax
0x1011bd07  lea     eax, [esp+940h+var_928]
0x1011bd0b  push    eax
0x1011bd0c  push    207h
0x1011bd11  lea     eax, [esp+948h+var_688]
0x1011bd18  push    eax
0x1011bd19  push    [esp+94Ch+var_90C]
0x1011bd1d  push    ebx
0x1011bd1e  push    edi
0x1011bd1f  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011bd24  mov     esi, eax
0x1011bd26  test    esi, esi
0x1011bd28  js      loc_1011C0A9
0x1011bd2e  mov     eax, [esp+938h+var_928]
0x1011bd32  xor     ecx, ecx
0x1011bd34  mov     [esp+eax+938h+var_688], cx
0x1011bd3c  mov     cx, [esp+938h+szLongPath]
0x1011bd44  mov     ax, [esp+938h+var_688]
0x1011bd4c  test    cx, cx
0x1011bd4f  jnz     short loc_1011BD5A
0x1011bd51  test    ax, ax
0x1011bd54  jz      loc_1011BF9D
0x1011bd5a  cmp     [esp+938h+var_918], 0
0x1011bd5f  jz      loc_1011BF0A
0x1011bd65  test    cx, cx
0x1011bd68  jz      loc_1011BE63
0x1011bd6e  push    1; int
0x1011bd70  lea     edx, [esp+93Ch+var_210]; LPCWSTR
0x1011bd77  lea     ecx, [esp+93Ch+szLongPath]; lpszLongPath
0x1011bd7e  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bd83  test    eax, eax
0x1011bd85  jnz     loc_1011BF9D
0x1011bd8b  cmp     [esp+938h+pszDest], ax
0x1011bd93  jz      loc_1011BFA7
0x1011bd99  cmp     [esp+938h+var_688], ax
0x1011bda1  jz      short loc_1011BE0A
0x1011bda3  push    1; int
0x1011bda5  lea     edx, [esp+93Ch+var_688]; LPCWSTR
0x1011bdac  lea     ecx, [esp+93Ch+pszDest]; lpszLongPath
0x1011bdb3  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bdb8  test    eax, eax
0x1011bdba  jz      short loc_1011BDCC
0x1011bdbc  lea     ecx, [esp+938h+var_688]
0x1011bdc3  call    _FValidateShareName@4; FValidateShareName(x)
0x1011bdc8  test    eax, eax
0x1011bdca  jz      short loc_1011BE0A
0x1011bdcc  lea     edx, [esp+938h+pszDest]
0x1011bdd3  xor     esi, esi
0x1011bdd5  lea     ecx, [edx+2]
0x1011bdd8  mov     ax, [edx]
0x1011bddb  add     edx, 2
0x1011bdde  cmp     ax, si
0x1011bde1  jnz     short loc_1011BDD8
0x1011bde3  sub     edx, ecx
0x1011bde5  lea     ecx, [esp+938h+var_688]
0x1011bdec  sar     edx, 1
0x1011bdee  lea     esi, [ecx+2]
0x1011bdf1  mov     ax, [ecx]
0x1011bdf4  add     ecx, 2
0x1011bdf7  cmp     ax, word ptr [esp+938h+var_914]
0x1011bdfc  jnz     short loc_1011BDF1
0x1011bdfe  sub     ecx, esi
0x1011be00  sar     ecx, 1
0x1011be02  cmp     edx, ecx
0x1011be04  jnb     loc_1011BFA7
0x1011be0a  cmp     [esp+938h+var_924], 0
0x1011be0f  jnz     loc_1011BFA7
0x1011be15  push    2
0x1011be17  push    ebx
0x1011be18  push    edi
0x1011be19  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1011be1e  mov     esi, eax
0x1011be20  test    esi, esi
0x1011be22  js      loc_1011C0A9
0x1011be28  push    0
0x1011be2a  push    18h
0x1011be2c  lea     eax, [esp+940h+var_910]
0x1011be30  push    eax
0x1011be31  push    offset _WZUNCPathname; "UNCPathname"
0x1011be36  push    ebx
0x1011be37  push    edi
0x1011be38  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011be3d  mov     esi, eax
0x1011be3f  test    esi, esi
0x1011be41  js      loc_1011C0A9
0x1011be47  lea     ecx, [esp+938h+pszDest]
0x1011be4e  xor     esi, esi
0x1011be50  lea     edx, [ecx+2]
0x1011be53  mov     ax, [ecx]
0x1011be56  add     ecx, 2
0x1011be59  cmp     ax, si
0x1011be5c  jnz     short loc_1011BE53
0x1011be5e  jmp     loc_1011C070
0x1011be63  mov     esi, 104h
0x1011be68  lea     edx, [esp+938h+szLongPath]
0x1011be6f  push    esi
0x1011be70  lea     ecx, [esp+93Ch+var_688]
0x1011be77  call    _ResolveRemotePathToLocalName@12; ResolveRemotePathToLocalName(x,x,x)
0x1011be7c  test    eax, eax
0x1011be7e  jz      loc_1011BF9D
0x1011be84  push    1; int
0x1011be86  lea     edx, [esp+93Ch+szLongPath]; LPCWSTR
0x1011be8d  lea     ecx, [esp+93Ch+var_210]; lpszLongPath
0x1011be94  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011be99  test    eax, eax
0x1011be9b  jnz     loc_1011BF9D
0x1011bea1  cmp     [esp+938h+var_924], eax
0x1011bea5  jnz     loc_1011BFA7
0x1011beab  push    2
0x1011bead  push    ebx
0x1011beae  push    edi
0x1011beaf  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1011beb4  mov     esi, eax
0x1011beb6  test    esi, esi
0x1011beb8  js      loc_1011C0A9
0x1011bebe  push    0
0x1011bec0  push    18h
0x1011bec2  lea     eax, [esp+940h+var_910]
0x1011bec6  push    eax
0x1011bec7  push    offset _WZPathname; "Pathname"
0x1011becc  push    ebx
0x1011becd  push    edi
0x1011bece  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bed3  mov     esi, eax
0x1011bed5  test    esi, esi
0x1011bed7  js      loc_1011C0A9
0x1011bedd  lea     ecx, [esp+938h+szLongPath]
0x1011bee4  xor     esi, esi
0x1011bee6  lea     edx, [ecx+2]
0x1011bee9  mov     ax, [ecx]
0x1011beec  add     ecx, 2
0x1011beef  cmp     ax, si
0x1011bef2  jnz     short loc_1011BEE9
0x1011bef4  sub     ecx, edx
0x1011bef6  sar     ecx, 1
0x1011bef8  push    esi
0x1011bef9  push    esi
0x1011befa  lea     eax, [ecx+ecx]
0x1011befd  push    eax
0x1011befe  lea     eax, [esp+944h+szLongPath]
0x1011bf05  jmp     loc_1011C081
0x1011bf0a  test    ax, ax
0x1011bf0d  jz      loc_1011BFEB
0x1011bf13  push    1; int
0x1011bf15  lea     edx, [esp+93Ch+pszDest]; LPCWSTR
0x1011bf1c  lea     ecx, [esp+93Ch+var_688]; lpszLongPath
0x1011bf23  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bf28  test    eax, eax
0x1011bf2a  jz      short loc_1011BFA7
0x1011bf2c  lea     edx, [esp+938h+pszDest]
0x1011bf33  lea     ecx, [esp+938h+var_688]
0x1011bf3a  call    _ComparePathFindData@8; ComparePathFindData(x,x)
0x1011bf3f  test    eax, eax
0x1011bf41  jnz     short loc_1011BF4F
0x1011bf43  mov     eax, [esp+938h+var_920]
0x1011bf47  mov     dword ptr [eax], 0
0x1011bf4d  jmp     short loc_1011BFA7
0x1011bf4f  mov     esi, 104h
0x1011bf54  lea     edx, [esp+938h+szLongPath]
0x1011bf5b  push    esi
0x1011bf5c  lea     ecx, [esp+93Ch+var_688]
0x1011bf63  call    _ResolveRemotePathToLocalName@12; ResolveRemotePathToLocalName(x,x,x)
0x1011bf68  test    eax, eax
0x1011bf6a  jz      short loc_1011BF9D
0x1011bf6c  push    esi
0x1011bf6d  lea     edx, [esp+93Ch+var_210]
  ... truncated ...
```
