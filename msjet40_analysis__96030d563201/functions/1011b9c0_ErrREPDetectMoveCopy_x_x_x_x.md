# ErrREPDetectMoveCopy(x,x,x,x)

- ea: `0x1011b9c0`
- end: `0x1011bf1a`
- name: `_ErrREPDetectMoveCopy@16`
- size: `1370`
- prototype: `int __stdcall(Session *, int, int, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10117190`

## callees

- `0x10012940`
- `0x10042ed0`
- `0x10043660`
- `0x100440c0`
- `0x100448f0`
- `0x10044c00`
- `0x10044e00`
- `0x1004d790`
- `0x1004d830`
- `0x1004d890`
- `0x1011b930`
- `0x1011b9c0`
- `0x1012066d`
- `0x10121312`
- `0x101216c0`
- `0x1012178b`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1011be20`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1011be20`

## string_xrefs

- `0x1011bb3d`: `UNCPathname`
- `0x1011bc81`: `UNCPathname`
- `0x1011be97`: `UNCPathname`
- `0x1011bae6`: `Pathname`
- `0x1011bd17`: `Pathname`

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
0x1011b9c0  mov     edi, edi
0x1011b9c2  push    ebp
0x1011b9c3  mov     ebp, esp
0x1011b9c5  and     esp, 0FFFFFFF8h
0x1011b9c8  sub     esp, 92Ch
0x1011b9ce  mov     eax, ___security_cookie
0x1011b9d3  xor     eax, esp
0x1011b9d5  mov     [esp+92Ch+var_4], eax
0x1011b9dc  mov     eax, [ebp+arg_C]
0x1011b9df  push    ebx
0x1011b9e0  push    esi
0x1011b9e1  push    edi
0x1011b9e2  mov     edi, [ebp+arg_0]
0x1011b9e5  mov     [esp+938h+var_920], eax
0x1011b9e9  xor     eax, eax
0x1011b9eb  push    edi
0x1011b9ec  mov     [esp+93Ch+var_914], eax
0x1011b9f0  mov     [esp+93Ch+var_91C], eax
0x1011b9f4  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x1011b9f9  test    eax, eax
0x1011b9fb  js      loc_1011BF03
0x1011ba01  push    6
0x1011ba03  push    4
0x1011ba05  lea     eax, [esp+940h+var_91C]
0x1011ba09  push    eax
0x1011ba0a  push    [ebp+arg_4]
0x1011ba0d  push    edi
0x1011ba0e  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1011ba13  mov     esi, eax
0x1011ba15  test    esi, esi
0x1011ba17  js      loc_1011BEF9
0x1011ba1d  mov     eax, [esp+938h+var_91C]
0x1011ba21  xor     ebx, ebx
0x1011ba23  and     eax, 1
0x1011ba26  mov     ecx, 104h
0x1011ba2b  mov     [esp+938h+var_924], eax
0x1011ba2f  mov     eax, [esp+938h+var_920]
0x1011ba33  mov     [eax], ebx
0x1011ba35  lea     eax, [esp+938h+var_918]
0x1011ba39  push    eax; int
0x1011ba3a  push    ecx; int
0x1011ba3b  lea     eax, [esp+940h+pszDest]
0x1011ba42  push    eax; pszDest
0x1011ba43  push    ecx; int
0x1011ba44  lea     eax, [esp+948h+var_210]
0x1011ba4b  push    eax; int
0x1011ba4c  push    31h ; '1'; int
0x1011ba4e  lea     eax, [esp+950h+var_278]
0x1011ba55  push    eax; int
0x1011ba56  push    [ebp+arg_4]; int
0x1011ba59  push    edi; int
0x1011ba5a  call    _ErrREPGetFullDbpath@36; ErrREPGetFullDbpath(x,x,x,x,x,x,x,x,x)
0x1011ba5f  mov     esi, eax
0x1011ba61  cmp     esi, 0FFFFB1CDh
0x1011ba67  jz      loc_1011BDED
0x1011ba6d  test    esi, esi
0x1011ba6f  js      loc_1011BEF9
0x1011ba75  push    ebx
0x1011ba76  mov     ebx, [ebp+arg_8]
0x1011ba79  lea     eax, [esp+93Ch+var_910]
0x1011ba7d  push    18h
0x1011ba7f  push    eax
0x1011ba80  push    offset _WZMachinename; "Machinename"
0x1011ba85  push    ebx
0x1011ba86  push    edi
0x1011ba87  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011ba8c  mov     esi, eax
0x1011ba8e  test    esi, esi
0x1011ba90  js      loc_1011BEF9
0x1011ba96  xor     eax, eax
0x1011ba98  push    eax
0x1011ba99  push    eax
0x1011ba9a  lea     eax, [esp+940h+var_928]
0x1011ba9e  push    eax
0x1011ba9f  push    61h ; 'a'
0x1011baa1  lea     eax, [esp+948h+var_8F8]
0x1011baa5  push    eax
0x1011baa6  push    [esp+94Ch+var_90C]
0x1011baaa  push    ebx
0x1011baab  push    edi
0x1011baac  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011bab1  mov     esi, eax
0x1011bab3  test    esi, esi
0x1011bab5  js      loc_1011BEF9
0x1011babb  mov     eax, [esp+938h+var_928]
0x1011babf  lea     edx, [esp+938h+var_278]
0x1011bac6  xor     ecx, ecx
0x1011bac8  mov     [esp+eax+938h+var_8F8], cx
0x1011bacd  lea     ecx, [esp+938h+var_8F8]
0x1011bad1  call    _WCSICMP@8; WCSICMP(x,x)
0x1011bad6  test    eax, eax
0x1011bad8  jnz     loc_1011BDED
0x1011bade  push    eax
0x1011badf  push    18h
0x1011bae1  lea     eax, [esp+940h+var_910]
0x1011bae5  push    eax
0x1011bae6  push    offset _WZPathname; "Pathname"
0x1011baeb  push    ebx
0x1011baec  push    edi
0x1011baed  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011baf2  mov     esi, eax
0x1011baf4  test    esi, esi
0x1011baf6  js      loc_1011BEF9
0x1011bafc  xor     eax, eax
0x1011bafe  push    eax
0x1011baff  push    eax
0x1011bb00  lea     eax, [esp+940h+var_928]
0x1011bb04  push    eax
0x1011bb05  push    207h
0x1011bb0a  lea     eax, [esp+948h+szLongPath]
0x1011bb11  push    eax
0x1011bb12  push    [esp+94Ch+var_90C]
0x1011bb16  push    ebx
0x1011bb17  push    edi
0x1011bb18  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011bb1d  mov     esi, eax
0x1011bb1f  test    esi, esi
0x1011bb21  js      loc_1011BEF9
0x1011bb27  mov     eax, [esp+938h+var_928]
0x1011bb2b  xor     ecx, ecx
0x1011bb2d  push    ecx
0x1011bb2e  push    18h
0x1011bb30  mov     [esp+eax+940h+szLongPath], cx
0x1011bb38  lea     eax, [esp+940h+var_910]
0x1011bb3c  push    eax
0x1011bb3d  push    offset _WZUNCPathname; "UNCPathname"
0x1011bb42  push    ebx
0x1011bb43  push    edi
0x1011bb44  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bb49  mov     esi, eax
0x1011bb4b  test    esi, esi
0x1011bb4d  js      loc_1011BEF9
0x1011bb53  xor     eax, eax
0x1011bb55  push    eax
0x1011bb56  push    eax
0x1011bb57  lea     eax, [esp+940h+var_928]
0x1011bb5b  push    eax
0x1011bb5c  push    207h
0x1011bb61  lea     eax, [esp+948h+var_688]
0x1011bb68  push    eax
0x1011bb69  push    [esp+94Ch+var_90C]
0x1011bb6d  push    ebx
0x1011bb6e  push    edi
0x1011bb6f  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011bb74  mov     esi, eax
0x1011bb76  test    esi, esi
0x1011bb78  js      loc_1011BEF9
0x1011bb7e  mov     eax, [esp+938h+var_928]
0x1011bb82  xor     ecx, ecx
0x1011bb84  mov     [esp+eax+938h+var_688], cx
0x1011bb8c  mov     cx, [esp+938h+szLongPath]
0x1011bb94  mov     ax, [esp+938h+var_688]
0x1011bb9c  test    cx, cx
0x1011bb9f  jnz     short loc_1011BBAA
0x1011bba1  test    ax, ax
0x1011bba4  jz      loc_1011BDED
0x1011bbaa  cmp     [esp+938h+var_918], 0
0x1011bbaf  jz      loc_1011BD5A
0x1011bbb5  test    cx, cx
0x1011bbb8  jz      loc_1011BCB3
0x1011bbbe  push    1; int
0x1011bbc0  lea     edx, [esp+93Ch+var_210]; LPCWSTR
0x1011bbc7  lea     ecx, [esp+93Ch+szLongPath]; lpszLongPath
0x1011bbce  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bbd3  test    eax, eax
0x1011bbd5  jnz     loc_1011BDED
0x1011bbdb  cmp     [esp+938h+pszDest], ax
0x1011bbe3  jz      loc_1011BDF7
0x1011bbe9  cmp     [esp+938h+var_688], ax
0x1011bbf1  jz      short loc_1011BC5A
0x1011bbf3  push    1; int
0x1011bbf5  lea     edx, [esp+93Ch+var_688]; LPCWSTR
0x1011bbfc  lea     ecx, [esp+93Ch+pszDest]; lpszLongPath
0x1011bc03  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bc08  test    eax, eax
0x1011bc0a  jz      short loc_1011BC1C
0x1011bc0c  lea     ecx, [esp+938h+var_688]
0x1011bc13  call    _FValidateShareName@4; FValidateShareName(x)
0x1011bc18  test    eax, eax
0x1011bc1a  jz      short loc_1011BC5A
0x1011bc1c  lea     edx, [esp+938h+pszDest]
0x1011bc23  xor     esi, esi
0x1011bc25  lea     ecx, [edx+2]
0x1011bc28  mov     ax, [edx]
0x1011bc2b  add     edx, 2
0x1011bc2e  cmp     ax, si
0x1011bc31  jnz     short loc_1011BC28
0x1011bc33  sub     edx, ecx
0x1011bc35  lea     ecx, [esp+938h+var_688]
0x1011bc3c  sar     edx, 1
0x1011bc3e  lea     esi, [ecx+2]
0x1011bc41  mov     ax, [ecx]
0x1011bc44  add     ecx, 2
0x1011bc47  cmp     ax, word ptr [esp+938h+var_914]
0x1011bc4c  jnz     short loc_1011BC41
0x1011bc4e  sub     ecx, esi
0x1011bc50  sar     ecx, 1
0x1011bc52  cmp     edx, ecx
0x1011bc54  jnb     loc_1011BDF7
0x1011bc5a  cmp     [esp+938h+var_924], 0
0x1011bc5f  jnz     loc_1011BDF7
0x1011bc65  push    2
0x1011bc67  push    ebx
0x1011bc68  push    edi
0x1011bc69  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1011bc6e  mov     esi, eax
0x1011bc70  test    esi, esi
0x1011bc72  js      loc_1011BEF9
0x1011bc78  push    0
0x1011bc7a  push    18h
0x1011bc7c  lea     eax, [esp+940h+var_910]
0x1011bc80  push    eax
0x1011bc81  push    offset _WZUNCPathname; "UNCPathname"
0x1011bc86  push    ebx
0x1011bc87  push    edi
0x1011bc88  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bc8d  mov     esi, eax
0x1011bc8f  test    esi, esi
0x1011bc91  js      loc_1011BEF9
0x1011bc97  lea     ecx, [esp+938h+pszDest]
0x1011bc9e  xor     esi, esi
0x1011bca0  lea     edx, [ecx+2]
0x1011bca3  mov     ax, [ecx]
0x1011bca6  add     ecx, 2
0x1011bca9  cmp     ax, si
0x1011bcac  jnz     short loc_1011BCA3
0x1011bcae  jmp     loc_1011BEC0
0x1011bcb3  mov     esi, 104h
0x1011bcb8  lea     edx, [esp+938h+szLongPath]
0x1011bcbf  push    esi
0x1011bcc0  lea     ecx, [esp+93Ch+var_688]
0x1011bcc7  call    _ResolveRemotePathToLocalName@12; ResolveRemotePathToLocalName(x,x,x)
0x1011bccc  test    eax, eax
0x1011bcce  jz      loc_1011BDED
0x1011bcd4  push    1; int
0x1011bcd6  lea     edx, [esp+93Ch+szLongPath]; LPCWSTR
0x1011bcdd  lea     ecx, [esp+93Ch+var_210]; lpszLongPath
0x1011bce4  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bce9  test    eax, eax
0x1011bceb  jnz     loc_1011BDED
0x1011bcf1  cmp     [esp+938h+var_924], eax
0x1011bcf5  jnz     loc_1011BDF7
0x1011bcfb  push    2
0x1011bcfd  push    ebx
0x1011bcfe  push    edi
0x1011bcff  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1011bd04  mov     esi, eax
0x1011bd06  test    esi, esi
0x1011bd08  js      loc_1011BEF9
0x1011bd0e  push    0
0x1011bd10  push    18h
0x1011bd12  lea     eax, [esp+940h+var_910]
0x1011bd16  push    eax
0x1011bd17  push    offset _WZPathname; "Pathname"
0x1011bd1c  push    ebx
0x1011bd1d  push    edi
0x1011bd1e  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011bd23  mov     esi, eax
0x1011bd25  test    esi, esi
0x1011bd27  js      loc_1011BEF9
0x1011bd2d  lea     ecx, [esp+938h+szLongPath]
0x1011bd34  xor     esi, esi
0x1011bd36  lea     edx, [ecx+2]
0x1011bd39  mov     ax, [ecx]
0x1011bd3c  add     ecx, 2
0x1011bd3f  cmp     ax, si
0x1011bd42  jnz     short loc_1011BD39
0x1011bd44  sub     ecx, edx
0x1011bd46  sar     ecx, 1
0x1011bd48  push    esi
0x1011bd49  push    esi
0x1011bd4a  lea     eax, [ecx+ecx]
0x1011bd4d  push    eax
0x1011bd4e  lea     eax, [esp+944h+szLongPath]
0x1011bd55  jmp     loc_1011BED1
0x1011bd5a  test    ax, ax
0x1011bd5d  jz      loc_1011BE3B
0x1011bd63  push    1; int
0x1011bd65  lea     edx, [esp+93Ch+pszDest]; LPCWSTR
0x1011bd6c  lea     ecx, [esp+93Ch+var_688]; lpszLongPath
0x1011bd73  call    _ComparePathStrings@12; ComparePathStrings(x,x,x)
0x1011bd78  test    eax, eax
0x1011bd7a  jz      short loc_1011BDF7
0x1011bd7c  lea     edx, [esp+938h+pszDest]
0x1011bd83  lea     ecx, [esp+938h+var_688]
0x1011bd8a  call    _ComparePathFindData@8; ComparePathFindData(x,x)
0x1011bd8f  test    eax, eax
0x1011bd91  jnz     short loc_1011BD9F
0x1011bd93  mov     eax, [esp+938h+var_920]
0x1011bd97  mov     dword ptr [eax], 0
0x1011bd9d  jmp     short loc_1011BDF7
0x1011bd9f  mov     esi, 104h
0x1011bda4  lea     edx, [esp+938h+szLongPath]
0x1011bdab  push    esi
0x1011bdac  lea     ecx, [esp+93Ch+var_688]
0x1011bdb3  call    _ResolveRemotePathToLocalName@12; ResolveRemotePathToLocalName(x,x,x)
0x1011bdb8  test    eax, eax
0x1011bdba  jz      short loc_1011BDED
0x1011bdbc  push    esi
0x1011bdbd  lea     edx, [esp+93Ch+var_210]
  ... truncated ...
```
