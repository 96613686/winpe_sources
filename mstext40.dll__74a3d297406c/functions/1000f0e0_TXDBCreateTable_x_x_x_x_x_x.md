# TXDBCreateTable(x,x,x,x,x,x)

- ea: `0x1000f0e0`
- end: `0x1000f528`
- name: `_TXDBCreateTable@24`
- size: `1096`
- prototype: `int __stdcall(int, int, STRSAFE_LPCWSTR pszSrc, int, int, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x1000a1f0`
- `0x1000a470`
- `0x1000a740`
- `0x1000ad60`
- `0x1000bf60`
- `0x1000e350`
- `0x1000f0e0`
- `0x1000fc70`
- `0x100108e0`
- `0x10013c80`
- `0x10013ee0`
- `0x10014270`
- `0x100145a0`
- `0x10014690`
- `0x10014740`
- `0x10019c30`
- `0x1001bff0`
- `0x1001c060`
- `0x1001c250`
- `0x1002a2b0`
- `0x1002b81a`
- `0x1002c253`

## pseudocode

```c
int __stdcall TXDBCreateTable(int a1, int a2, char *pszSrc, int a4, int a5, int a6)
{
  int v6; // eax
  int *v7; // ebx
  int result; // eax
  int v9; // edi
  int v10; // eax
  wchar_t *v11; // ecx
  int v12; // edx
  wchar_t v13; // ax
  unsigned int v14; // kr00_4
  unsigned int v15; // eax
  WCHAR *v16; // ecx
  int v17; // edx
  WCHAR v18; // ax
  int v19; // ecx
  wchar_t *v20; // ecx
  int v21; // edx
  wchar_t v22; // ax
  int v23; // esi
  __int16 v24; // si
  __int16 v25; // cx
  __int16 v26; // bp
  __int16 v27; // dx
  int v28; // eax
  int v29; // esi
  DWORD v30; // eax
  int v31; // eax
  _DWORD *v32; // ebp
  int v33; // ebx
  int v34; // [esp+10h] [ebp-620h] BYREF
  int IntoValidFilename; // [esp+14h] [ebp-61Ch]
  int v36; // [esp+18h] [ebp-618h]
  int v37; // [esp+1Ch] [ebp-614h]
  wchar_t pszDest[262]; // [esp+20h] [ebp-610h] BYREF
  WCHAR WideCharStr[256]; // [esp+22Ch] [ebp-404h] BYREF
  wchar_t v40[256]; // [esp+42Ch] [ebp-204h] BYREF

  v37 = a1;
  v36 = a6;
  v6 = ISAMDBFindDatabaseUser(a1, a2);
  v7 = (int *)v6;
  if ( !v6 )
    return -1010;
  if ( (*(_BYTE *)(v6 + 892) & 1) != 0 )
    return -1809;
  v9 = *(_DWORD *)(v6 + 4);
  v10 = NetProtocolType(v9 + 578);
  if ( *(_DWORD *)(v9 + 8) || v10 != 1 )
  {
    if ( v10 )
    {
      result = TestFTPWrite(v9);
      if ( result )
        return result;
    }
    if ( *(_DWORD *)(v9 + 8) )
    {
      v16 = WideCharStr;
      v17 = 256;
      while ( v17 != -2147483390 )
      {
        v18 = *(WCHAR *)((char *)v16 + pszSrc - (char *)WideCharStr);
        if ( !v18 )
          break;
        *v16++ = v18;
        if ( !--v17 )
        {
          --v16;
          break;
        }
      }
      *v16 = 0;
    }
    else
    {
      TranslateNames(v7[12], pszSrc, WideCharStr, 256);
    }
    IntoValidFilename = MakeIntoValidFilename(WideCharStr, (int)v40, 256, 255, 255, 1, 0x4B0u);
    v34 = ISAMDBLocateTable(v9, v40);
    if ( !v34 )
    {
      result = LocateTableInDatabase((int)v7, (STRSAFE_LPCWSTR)pszSrc, (int)&v34, 0);
      if ( result )
      {
        if ( result != -1305 )
          return result;
        if ( !IsAcceptableFileName(v40) )
          return -1809;
        v19 = ISAMDBAddTable(v9, v40);
        v34 = v19;
        if ( v19 )
        {
          if ( *(_DWORD *)(v9 + 8) != 1 )
          {
            GetFixedFormat(v7, 1);
            v19 = v34;
          }
          if ( *(_WORD *)(v9 + 36) )
          {
            TextCopySpecInfo(v19 + 12, v7 + 3);
            *(_DWORD *)(v34 + 48) = v7[216];
            *(_DWORD *)(v34 + 52) = v7[218];
            *(_DWORD *)(v34 + 56) = v7[217];
          }
          else
          {
            v20 = pszDest;
            v21 = 261;
            while ( v21 != -2147483385 )
            {
              v22 = *(wchar_t *)((char *)v20 + v9 + 56 - (_DWORD)pszDest);
              if ( !v22 )
                break;
              *v20++ = v22;
              if ( !--v21 )
              {
                --v20;
                break;
              }
            }
            *v20 = 0;
            StringCchCatW(pszDest, 0x105u, L"schema.ini");
            if ( TextSpecAvailable((int)v7, (JET_TABLEID)pszDest, (void *)(v34 + 920), 0) )
            {
              v23 = TextSpecRead((int)v7, (JET_TABLEID)pszDest, v34 + 920, v34 + 12, 0);
              if ( v23 )
              {
                ISAMDBDeleteTable(v9, v34);
                return v23;
              }
              *(_DWORD *)(v34 + 12) = 2;
            }
            else
            {
              TextCopySpecInfo(v34 + 12, v7 + 3);
            }
          }
          if ( !*(_DWORD *)(v34 + 64) )
          {
            v24 = *(_WORD *)(v34 + 742);
            v25 = *(_WORD *)(v34 + 68);
            if ( v24 == v25 )
              return -5406;
            v26 = *(_WORD *)(v34 + 736);
            if ( v26 == v25 )
              return -5406;
            v27 = *(_WORD *)(v34 + 84);
            if ( v27 == v24 || v27 == v26 || v27 == v25 )
              return -5406;
          }
          v28 = ISAMDBAddCursor(v7, v34);
          v29 = v28;
          if ( v28 )
          {
            *(_DWORD *)(v28 + 20) = 3;
            *(_WORD *)(v28 + 28) = 0;
            *(_DWORD *)(v34 + 880) = 1;
            *(_DWORD *)(v34 + 912) = 0;
            v30 = CurrentTaskHandle();
            v31 = ISAMDBFindTask(v30);
            v32 = (_DWORD *)v36;
            v33 = (*(int (__stdcall **)(int, int, _DWORD, int *))(*(_DWORD *)(v31 + 28) + 36))(
                    v37,
                    v36,
                    *(_DWORD *)(v29 + 12),
                    &TableEntryPoints);
            if ( v33 )
            {
              ISAMDBDeleteTable(v9, v34);
              return v33;
            }
            else
            {
              *(_DWORD *)(v29 + 16) = *v32;
              result = 0;
              if ( IntoValidFilename == 2 )
                return 5011;
            }
            return result;
          }
          ISAMDBDeleteTable(v9, v34);
        }
        return -1011;
      }
      ISAMDBDeleteTable(v9, v34);
    }
    ErrorSetExtendedInfoSz1(-8162, (STRSAFE_LPCWSTR)pszSrc, 1);
    return -1303;
  }
  v11 = pszDest;
  v12 = 261;
  while ( v12 != -2147483385 )
  {
    v13 = *(wchar_t *)((char *)v11 + v9 + 578 - (_DWORD)pszDest);
    if ( !v13 )
      break;
    *v11++ = v13;
    if ( !--v12 )
    {
      --v11;
      break;
    }
  }
  *v11 = 0;
  v14 = wcslen(pszDest);
  if ( pszDest[v14 - 1] == 92 )
  {
    v15 = 2 * v14 - 2;
    if ( v15 >= 0x20A )
      __report_rangecheckfailure();
    *(wchar_t *)((char *)pszDest + v15) = 0;
  }
  ErrorSetExtendedInfoSz1(-8161, pszDest, 0);
  return -1023;
}

```

## disassembly

```asm
0x1000f0e0  sub     esp, 620h
0x1000f0e6  mov     eax, ___security_cookie
0x1000f0eb  xor     eax, esp
0x1000f0ed  mov     [esp+620h+var_4], eax
0x1000f0f4  mov     eax, [esp+620h+arg_4]
0x1000f0fb  mov     ecx, [esp+620h+arg_0]
0x1000f102  mov     edx, [esp+620h+arg_14]
0x1000f109  push    ebx
0x1000f10a  push    ebp
0x1000f10b  mov     ebp, [esp+628h+pszSrc]
0x1000f112  push    eax
0x1000f113  push    ecx
0x1000f114  mov     [esp+630h+var_614], ecx
0x1000f118  mov     [esp+630h+var_618], edx
0x1000f11c  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x1000f121  mov     ebx, eax
0x1000f123  test    ebx, ebx
0x1000f125  jnz     short loc_1000F131
0x1000f127  mov     eax, 0FFFFFC0Eh
0x1000f12c  jmp     loc_1000F50A
0x1000f131  test    byte ptr [ebx+37Ch], 1
0x1000f138  jz      short loc_1000F144
0x1000f13a  mov     eax, 0FFFFF8EFh
0x1000f13f  jmp     loc_1000F50A
0x1000f144  push    esi
0x1000f145  push    edi
0x1000f146  mov     edi, [ebx+4]
0x1000f149  lea     esi, [edi+242h]
0x1000f14f  push    esi
0x1000f150  call    _NetProtocolType@4; NetProtocolType(x)
0x1000f155  cmp     dword ptr [edi+8], 0
0x1000f159  jnz     loc_1000F1F1
0x1000f15f  cmp     eax, 1
0x1000f162  jnz     loc_1000F1F1
0x1000f168  lea     ecx, [esp+630h+pszDest]
0x1000f16c  mov     edx, 105h
0x1000f171  mov     eax, ecx
0x1000f173  sub     esi, eax
0x1000f175  lea     eax, [edx+7FFFFEF9h]
0x1000f17b  test    eax, eax
0x1000f17d  jz      short loc_1000F193
0x1000f17f  movzx   eax, word ptr [esi+ecx]
0x1000f183  test    ax, ax
0x1000f186  jz      short loc_1000F193
0x1000f188  mov     [ecx], ax
0x1000f18b  add     ecx, 2
0x1000f18e  dec     edx
0x1000f18f  jnz     short loc_1000F175
0x1000f191  jmp     short loc_1000F197
0x1000f193  test    edx, edx
0x1000f195  jnz     short loc_1000F19A
0x1000f197  sub     ecx, 2
0x1000f19a  xor     eax, eax
0x1000f19c  mov     [ecx], ax
0x1000f19f  lea     ecx, [esp+630h+pszDest]
0x1000f1a3  lea     edx, [ecx+2]
0x1000f1a6  mov     ax, [ecx]
0x1000f1a9  add     ecx, 2
0x1000f1ac  test    ax, ax
0x1000f1af  jnz     short loc_1000F1A6
0x1000f1b1  sub     ecx, edx
0x1000f1b3  sar     ecx, 1
0x1000f1b5  cmp     word ptr [esp+ecx*2+630h+var_614+2], 5Ch ; '\'
0x1000f1bb  jnz     short loc_1000F1D6
0x1000f1bd  lea     eax, ds:0FFFFFFFEh[ecx*2]
0x1000f1c4  cmp     eax, 20Ah
0x1000f1c9  jnb     loc_1000F523
0x1000f1cf  xor     ecx, ecx
0x1000f1d1  mov     [esp+eax+630h+pszDest], cx
0x1000f1d6  push    0; int
0x1000f1d8  lea     eax, [esp+634h+pszDest]
0x1000f1dc  push    eax; pszSrc
0x1000f1dd  push    0FFFFE01Fh; int
0x1000f1e2  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1000f1e7  mov     eax, 0FFFFFC01h
0x1000f1ec  jmp     loc_1000F508
0x1000f1f1  test    eax, eax
0x1000f1f3  jz      short loc_1000F203
0x1000f1f5  push    edi
0x1000f1f6  call    TestFTPWrite
0x1000f1fb  test    eax, eax
0x1000f1fd  jnz     loc_1000F508
0x1000f203  cmp     dword ptr [edi+8], 0
0x1000f207  lea     eax, [esp+630h+WideCharStr]
0x1000f20e  jnz     short loc_1000F221
0x1000f210  push    100h; int
0x1000f215  push    eax; lpWideCharStr
0x1000f216  push    ebp; Src
0x1000f217  push    dword ptr [ebx+30h]; int
0x1000f21a  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x1000f21f  jmp     short loc_1000F25B
0x1000f221  mov     esi, ebp
0x1000f223  lea     ecx, [esp+630h+WideCharStr]
0x1000f22a  mov     edx, 100h
0x1000f22f  sub     esi, eax
0x1000f231  lea     eax, [edx+7FFFFEFEh]
0x1000f237  test    eax, eax
0x1000f239  jz      short loc_1000F24F
0x1000f23b  movzx   eax, word ptr [esi+ecx]
0x1000f23f  test    ax, ax
0x1000f242  jz      short loc_1000F24F
0x1000f244  mov     [ecx], ax
0x1000f247  add     ecx, 2
0x1000f24a  dec     edx
0x1000f24b  jnz     short loc_1000F231
0x1000f24d  jmp     short loc_1000F253
0x1000f24f  test    edx, edx
0x1000f251  jnz     short loc_1000F256
0x1000f253  sub     ecx, 2
0x1000f256  xor     eax, eax
0x1000f258  mov     [ecx], ax
0x1000f25b  push    4B0h; CodePage
0x1000f260  push    1; int
0x1000f262  push    0FFh; int
0x1000f267  push    0FFh; int
0x1000f26c  push    100h; int
0x1000f271  lea     eax, [esp+644h+var_204]
0x1000f278  push    eax; int
0x1000f279  lea     eax, [esp+648h+WideCharStr]
0x1000f280  push    eax; lpWideCharStr
0x1000f281  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x1000f286  mov     [esp+630h+var_61C], eax
0x1000f28a  lea     eax, [esp+630h+var_204]
0x1000f291  push    eax
0x1000f292  push    edi
0x1000f293  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x1000f298  mov     [esp+630h+var_620], eax
0x1000f29c  test    eax, eax
0x1000f29e  jnz     loc_1000F4F6
0x1000f2a4  push    eax; int
0x1000f2a5  lea     eax, [esp+634h+var_620]
0x1000f2a9  push    eax; int
0x1000f2aa  push    ebp; STRSAFE_LPCWSTR
0x1000f2ab  push    ebx; int
0x1000f2ac  call    _LocateTableInDatabase@16; LocateTableInDatabase(x,x,x,x)
0x1000f2b1  test    eax, eax
0x1000f2b3  jz      loc_1000F4EC
0x1000f2b9  cmp     eax, 0FFFFFAE7h
0x1000f2be  jnz     loc_1000F508
0x1000f2c4  lea     eax, [esp+630h+var_204]
0x1000f2cb  push    eax; pszSrc
0x1000f2cc  call    _IsAcceptableFileName@4; IsAcceptableFileName(x)
0x1000f2d1  test    eax, eax
0x1000f2d3  jnz     short loc_1000F2DF
0x1000f2d5  mov     eax, 0FFFFF8EFh
0x1000f2da  jmp     loc_1000F508
0x1000f2df  lea     eax, [esp+630h+var_204]
0x1000f2e6  push    eax
0x1000f2e7  push    edi
0x1000f2e8  call    _ISAMDBAddTable@8; ISAMDBAddTable(x,x)
0x1000f2ed  mov     ecx, eax
0x1000f2ef  mov     [esp+630h+var_620], ecx
0x1000f2f3  test    ecx, ecx
0x1000f2f5  jz      loc_1000F46A
0x1000f2fb  cmp     dword ptr [edi+8], 1
0x1000f2ff  jz      short loc_1000F30D
0x1000f301  push    1
0x1000f303  push    ebx
0x1000f304  call    _GetFixedFormat@8; GetFixedFormat(x,x)
0x1000f309  mov     ecx, [esp+630h+var_620]
0x1000f30d  cmp     word ptr [edi+24h], 0
0x1000f312  jnz     loc_1000F3DC
0x1000f318  lea     ecx, [esp+630h+pszDest]
0x1000f31c  mov     edx, 105h
0x1000f321  lea     esi, [edi+38h]
0x1000f324  mov     eax, ecx
0x1000f326  sub     esi, eax
0x1000f328  jmp     short loc_1000F330
0x1000f330  lea     eax, [edx+7FFFFEF9h]
0x1000f336  test    eax, eax
0x1000f338  jz      short loc_1000F34E
0x1000f33a  movzx   eax, word ptr [esi+ecx]
0x1000f33e  test    ax, ax
0x1000f341  jz      short loc_1000F34E
0x1000f343  mov     [ecx], ax
0x1000f346  add     ecx, 2
0x1000f349  dec     edx
0x1000f34a  jnz     short loc_1000F330
0x1000f34c  jmp     short loc_1000F352
0x1000f34e  test    edx, edx
0x1000f350  jnz     short loc_1000F355
0x1000f352  sub     ecx, 2
0x1000f355  xor     eax, eax
0x1000f357  push    offset aSchemaIni_0; "schema.ini"
0x1000f35c  mov     [ecx], ax
0x1000f35f  lea     eax, [esp+634h+pszDest]
0x1000f363  push    105h; cchDest
0x1000f368  push    eax; pszDest
0x1000f369  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000f36e  mov     eax, [esp+630h+var_620]
0x1000f372  push    0; tableid
0x1000f374  add     eax, 398h
0x1000f379  push    eax; pvData
0x1000f37a  lea     eax, [esp+638h+pszDest]
0x1000f37e  push    eax; JET_TABLEID
0x1000f37f  push    ebx; int
0x1000f380  call    _TextSpecAvailable@16; TextSpecAvailable(x,x,x,x)
0x1000f385  test    eax, eax
0x1000f387  jz      short loc_1000F3C9
0x1000f389  mov     ecx, [esp+630h+var_620]
0x1000f38d  push    0; JET_TABLEID
0x1000f38f  lea     eax, [ecx+0Ch]
0x1000f392  push    eax; int
0x1000f393  lea     eax, [ecx+398h]
0x1000f399  push    eax; int
0x1000f39a  lea     eax, [esp+63Ch+pszDest]
0x1000f39e  push    eax; tableid
0x1000f39f  push    ebx; int
0x1000f3a0  call    _TextSpecRead@20; TextSpecRead(x,x,x,x,x)
0x1000f3a5  mov     esi, eax
0x1000f3a7  test    esi, esi
0x1000f3a9  jz      short loc_1000F3BC
0x1000f3ab  push    [esp+630h+var_620]
0x1000f3af  push    edi
0x1000f3b0  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x1000f3b5  mov     eax, esi
0x1000f3b7  jmp     loc_1000F508
0x1000f3bc  mov     eax, [esp+630h+var_620]
0x1000f3c0  mov     dword ptr [eax+0Ch], 2
0x1000f3c7  jmp     short loc_1000F410
0x1000f3c9  lea     eax, [ebx+0Ch]
0x1000f3cc  push    eax
0x1000f3cd  mov     eax, [esp+634h+var_620]
0x1000f3d1  add     eax, 0Ch
0x1000f3d4  push    eax
0x1000f3d5  call    _TextCopySpecInfo@8; TextCopySpecInfo(x,x)
0x1000f3da  jmp     short loc_1000F410
0x1000f3dc  lea     eax, [ebx+0Ch]
0x1000f3df  push    eax
0x1000f3e0  lea     eax, [ecx+0Ch]
0x1000f3e3  push    eax
0x1000f3e4  call    _TextCopySpecInfo@8; TextCopySpecInfo(x,x)
0x1000f3e9  mov     eax, [esp+630h+var_620]
0x1000f3ed  mov     ecx, [ebx+360h]
0x1000f3f3  mov     [eax+30h], ecx
0x1000f3f6  mov     eax, [esp+630h+var_620]
0x1000f3fa  mov     ecx, [ebx+368h]
0x1000f400  mov     [eax+34h], ecx
0x1000f403  mov     eax, [esp+630h+var_620]
0x1000f407  mov     ecx, [ebx+364h]
0x1000f40d  mov     [eax+38h], ecx
0x1000f410  mov     eax, [esp+630h+var_620]
0x1000f414  cmp     dword ptr [eax+40h], 0
0x1000f418  jnz     short loc_1000F453
0x1000f41a  movzx   esi, word ptr [eax+2E6h]
0x1000f421  movzx   ecx, word ptr [eax+44h]
0x1000f425  cmp     si, cx
0x1000f428  jz      short loc_1000F449
0x1000f42a  movzx   ebp, word ptr [eax+2E0h]
0x1000f431  cmp     bp, cx
0x1000f434  jz      short loc_1000F449
0x1000f436  movzx   edx, word ptr [eax+54h]
0x1000f43a  cmp     dx, si
0x1000f43d  jz      short loc_1000F449
0x1000f43f  cmp     dx, bp
0x1000f442  jz      short loc_1000F449
0x1000f444  cmp     dx, cx
0x1000f447  jnz     short loc_1000F453
0x1000f449  mov     eax, 0FFFFEAE2h
0x1000f44e  jmp     loc_1000F508
0x1000f453  push    eax
0x1000f454  push    ebx
0x1000f455  call    _ISAMDBAddCursor@8; ISAMDBAddCursor(x,x)
0x1000f45a  mov     esi, eax
0x1000f45c  test    esi, esi
0x1000f45e  jnz     short loc_1000F474
0x1000f460  push    [esp+630h+var_620]
0x1000f464  push    edi
0x1000f465  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x1000f46a  mov     eax, 0FFFFFC0Dh
0x1000f46f  jmp     loc_1000F508
0x1000f474  mov     dword ptr [esi+14h], 3
0x1000f47b  mov     word ptr [esi+1Ch], 0
0x1000f481  mov     eax, [esp+630h+var_620]
0x1000f485  mov     dword ptr [eax+370h], 1
0x1000f48f  mov     eax, [esp+630h+var_620]
0x1000f493  mov     dword ptr [eax+390h], 0
0x1000f49d  call    _CurrentTaskHandle@0; CurrentTaskHandle()
0x1000f4a2  push    eax
0x1000f4a3  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1000f4a8  mov     ebp, [esp+630h+var_618]
0x1000f4ac  push    offset _TableEntryPoints
0x1000f4b1  push    dword ptr [esi+0Ch]
0x1000f4b4  mov     eax, [eax+1Ch]
0x1000f4b7  push    ebp
0x1000f4b8  push    [esp+63Ch+var_614]
0x1000f4bc  mov     eax, [eax+24h]
0x1000f4bf  call    eax
0x1000f4c1  mov     ebx, eax
0x1000f4c3  test    ebx, ebx
0x1000f4c5  jz      short loc_1000F4D5
0x1000f4c7  push    [esp+630h+var_620]
0x1000f4cb  push    edi
0x1000f4cc  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x1000f4d1  mov     eax, ebx
0x1000f4d3  jmp     short loc_1000F508
0x1000f4d5  mov     eax, [ebp+0]
0x1000f4d8  mov     ecx, 1393h
0x1000f4dd  mov     [esi+10h], eax
0x1000f4e0  xor     eax, eax
  ... truncated ...
```
