# TXDBOpenTable(x,x,x,x,x)

- ea: `0x10011870`
- end: `0x10011d63`
- name: `_TXDBOpenTable@20`
- size: `1267`
- prototype: `int __stdcall(int, int, int, STRSAFE_LPCWSTR, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x10016d90`
- `0x10016fc0`
- `0x10017670`

## callees

- `0x10009010`
- `0x1000a1f0`
- `0x1000a740`
- `0x1000ad60`
- `0x1000b070`
- `0x1000b200`
- `0x1000bf60`
- `0x1000e350`
- `0x10010f00`
- `0x10011060`
- `0x10011870`
- `0x10013f90`
- `0x10014400`
- `0x100145a0`
- `0x10014690`
- `0x10029870`
- `0x1002a2b0`
- `0x1002b81a`
- `0x1002c490`

## pseudocode

```c
int __stdcall TXDBOpenTable(int a1, int a2, int a3, wchar_t *a4, int a5)
{
  _DWORD *v5; // eax
  _DWORD *v6; // ebp
  bool v8; // zf
  int v9; // eax
  int v10; // ebx
  WCHAR *v11; // ecx
  int v12; // edx
  WCHAR v13; // ax
  int v14; // esi
  wchar_t *v15; // esi
  wchar_t *v16; // ecx
  int v17; // edx
  int ValidTableName; // esi
  int v19; // eax
  wchar_t *v20; // ecx
  int v21; // edx
  wchar_t v22; // ax
  int v23; // edx
  wchar_t v24; // ax
  int v25; // eax
  int v26; // eax
  int v27; // ebx
  char *v28; // ecx
  int v29; // edx
  char *v30; // esi
  __int16 v31; // ax
  char *v32; // esi
  __int16 v33; // ax
  int v34; // ebp
  char *v35; // eax
  char *v36; // edi
  _WORD *v37; // ecx
  int v38; // edx
  _WORD *v39; // esi
  int v40; // eax
  int v41; // eax
  DWORD v42; // eax
  int v43; // eax
  _DWORD *v44; // ecx
  int v45; // [esp+Ch] [ebp-654h] BYREF
  int v46; // [esp+10h] [ebp-650h] BYREF
  int v47; // [esp+14h] [ebp-64Ch]
  _DWORD *v48; // [esp+18h] [ebp-648h]
  unsigned int v49; // [esp+1Ch] [ebp-644h]
  _DWORD *v50; // [esp+20h] [ebp-640h]
  int v51; // [esp+24h] [ebp-63Ch]
  int v52; // [esp+28h] [ebp-638h] BYREF
  int v53; // [esp+2Ch] [ebp-634h]
  int v54; // [esp+30h] [ebp-630h]
  int v55; // [esp+34h] [ebp-62Ch] BYREF
  wchar_t pszDest[262]; // [esp+38h] [ebp-628h] BYREF
  WCHAR WideCharStr[262]; // [esp+244h] [ebp-41Ch] BYREF
  wchar_t pszSrc[262]; // [esp+450h] [ebp-210h] BYREF

  v53 = a1;
  v54 = a3;
  v45 = 0;
  v46 = 0;
  v5 = (_DWORD *)ISAMDBFindDatabaseUser(a1, a2);
  v6 = v5;
  v48 = v5;
  if ( !v5 )
    return -1010;
  v8 = v5[217] == 0;
  v9 = v5[2];
  v47 = v9;
  if ( v8 )
  {
    ValidTableName = OpenTable(v9, (int)v6, a3, a4, a5, 0, 1);
    goto LABEL_82;
  }
  v10 = v6[1];
  if ( !*a4 )
    goto LABEL_44;
  if ( *(_DWORD *)(v10 + 8) )
  {
    v11 = WideCharStr;
    v12 = 261;
    while ( v12 != -2147483385 )
    {
      v13 = *(WCHAR *)((char *)v11 + (char *)a4 - (char *)WideCharStr);
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
  }
  else
  {
    TranslateNames(v6[12], a4, WideCharStr, 261);
  }
  if ( !MakeIntoValidFilename(WideCharStr, (int)pszSrc, 261, 255, 255, 1, 0x4B0u) )
  {
    ErrorSetExtendedInfoSz1(-8198, a4, 1);
    return -1002;
  }
  if ( !*a4 || !ascii_wcsicmp(a4, L"NoName") )
  {
LABEL_44:
    pszDest[0] = 0;
    goto LABEL_45;
  }
  if ( NetProtocolType(v10 + 578) )
  {
    v14 = *(_DWORD *)(v10 + 20);
    if ( !v14 )
    {
      ValidTableName = -1305;
      goto LABEL_82;
    }
    v15 = *(wchar_t **)(v14 + 12);
    v16 = pszDest;
    v17 = 261;
    while ( v17 != -2147483385 && *v15 )
    {
      *v16++ = *v15++;
      if ( !--v17 )
        goto LABEL_39;
    }
    goto LABEL_40;
  }
  v19 = *(_DWORD *)(v10 + 8);
  if ( v19 )
  {
    if ( v19 != 1 )
    {
      ValidTableName = -1001;
      goto LABEL_82;
    }
    v16 = pszDest;
    v23 = 261;
    while ( v23 != -2147483385 )
    {
      v24 = *(wchar_t *)((char *)v16 + v10 + 578 - (_DWORD)pszDest);
      if ( !v24 )
        break;
      *v16++ = v24;
      if ( !--v23 )
      {
LABEL_39:
        --v16;
        break;
      }
    }
LABEL_40:
    *v16 = 0;
    goto LABEL_41;
  }
  v20 = pszDest;
  v21 = 261;
  while ( v21 != -2147483385 )
  {
    v22 = *(wchar_t *)((char *)v20 + v10 + 56 - (_DWORD)pszDest);
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
  StringCchCatW(pszDest, 0x105u, pszSrc);
LABEL_41:
  ValidTableName = MakeValidTableName(v10, pszDest, 0x105u);
  if ( !ValidTableName )
  {
LABEL_45:
    v25 = 0;
    if ( *(_DWORD *)(v10 + 8) == 1 )
      v25 = 3;
    ValidTableName = TextDetectCodePageInfo(
                       pszDest,
                       v6[217],
                       (int)(v6 + 216),
                       v6[219],
                       v6[218],
                       (int)&v45,
                       (int)&v46,
                       (int)&v55,
                       v25);
    if ( !ValidTableName )
    {
      v26 = ISAMDBAddVTDef(v47, 3);
      v27 = v26;
      if ( v26 )
      {
        *(_DWORD *)(v26 + 560) = 0;
        v28 = (char *)(v26 + 38);
        *(_DWORD *)(v26 + 32) = 0;
        v29 = 261;
        if ( *a4 )
        {
          v30 = (char *)((char *)pszSrc - v28);
          while ( v29 != -2147483385 )
          {
            v31 = *(_WORD *)&v30[(_DWORD)v28];
            if ( !v31 )
              break;
            *(_WORD *)v28 = v31;
            v28 += 2;
            if ( !--v29 )
              goto LABEL_62;
          }
        }
        else
        {
          v32 = (char *)((char *)pszDest - v28);
          while ( v29 != -2147483385 )
          {
            v33 = *(_WORD *)&v32[(_DWORD)v28];
            if ( !v33 )
              break;
            *(_WORD *)v28 = v33;
            v28 += 2;
            if ( !--v29 )
            {
LABEL_62:
              v28 -= 2;
              break;
            }
          }
        }
        *(_WORD *)v28 = 0;
        v50 = 0;
        v51 = 0;
        v49 = 0;
        if ( v46 )
        {
          v34 = 0;
          do
          {
            v35 = (char *)MemAllocate(0x20Cu);
            v36 = v35;
            if ( !v35 )
            {
              ISAMDBDeleteVTDef(v47, v27);
              ValidTableName = -1011;
              goto LABEL_82;
            }
            memset(v35, 0, 0x20Cu);
            v37 = v36 + 4;
            v38 = 256;
            v39 = (_WORD *)(v34 + v45);
            while ( v38 != -2147483390 && *v39 )
            {
              *v37++ = *v39++;
              if ( !--v38 )
              {
                --v37;
                break;
              }
            }
            *v37 = 0;
            *((_DWORD *)v36 + 129) = *(_DWORD *)(v45 + v34 + 512);
            *((_DWORD *)v36 + 130) = *(_DWORD *)(v45 + v34 + 516);
            if ( *(_DWORD *)(v27 + 560) )
              *v50 = v36;
            else
              *(_DWORD *)(v27 + 560) = v36;
            v34 += 1032;
            v40 = v51 + 1;
            v50 = v36;
            ++v51;
            ++v49;
          }
          while ( v49 < v46 );
          v6 = v48;
          if ( v40 > 0 )
          {
            *(_DWORD *)(v27 + 32) = v40;
            v41 = *(_DWORD *)(v27 + 560);
            *(_BYTE *)(v27 + 36) = 2;
            *(_DWORD *)(v27 + 564) = v41;
          }
        }
        v42 = CurrentTaskHandle();
        v43 = ISAMDBFindTask(v42);
        ValidTableName = (*(int (__stdcall **)(int, int *, _DWORD, int *))(*(_DWORD *)(v43 + 28) + 36))(
                           v53,
                           &v52,
                           *(_DWORD *)(v27 + 12),
                           &VTEntryPoints);
        if ( ValidTableName )
        {
          ISAMDBDeleteVTDef(v47, v27);
        }
        else
        {
          v44 = (_DWORD *)v54;
          *(_DWORD *)(v27 + 16) = v52;
          *(_DWORD *)(v27 + 20) = v6[221];
          *(_DWORD *)(v27 + 24) = v6[222];
          *v44 = v52;
        }
      }
      else
      {
        ValidTableName = -1011;
      }
    }
  }
LABEL_82:
  if ( v45 )
    MemFree(v45);
  return ValidTableName;
}

```

## disassembly

```asm
0x10011870  sub     esp, 654h
0x10011876  mov     eax, ___security_cookie
0x1001187b  xor     eax, esp
0x1001187d  mov     [esp+654h+var_4], eax
0x10011884  mov     eax, [esp+654h+arg_4]
0x1001188b  mov     ecx, [esp+654h+arg_0]
0x10011892  push    ebx
0x10011893  mov     ebx, [esp+658h+arg_8]
0x1001189a  push    ebp
0x1001189b  push    edi
0x1001189c  mov     edi, [esp+660h+arg_C]
0x100118a3  push    eax
0x100118a4  push    ecx
0x100118a5  mov     [esp+668h+var_634], ecx
0x100118a9  mov     [esp+668h+var_630], ebx
0x100118ad  mov     [esp+668h+var_654], 0
0x100118b5  mov     [esp+668h+var_650], 0
0x100118bd  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x100118c2  mov     ebp, eax
0x100118c4  mov     [esp+660h+var_648], ebp
0x100118c8  test    ebp, ebp
0x100118ca  jnz     short loc_100118D6
0x100118cc  mov     eax, 0FFFFFC0Eh
0x100118d1  jmp     loc_10011D49
0x100118d6  cmp     dword ptr [ebp+364h], 0
0x100118dd  mov     eax, [ebp+8]
0x100118e0  push    esi
0x100118e1  mov     [esp+664h+var_64C], eax
0x100118e5  jz      loc_10011D22
0x100118eb  cmp     word ptr [edi], 0
0x100118ef  mov     ebx, [ebp+4]
0x100118f2  jz      loc_10011AD5
0x100118f8  cmp     dword ptr [ebx+8], 0
0x100118fc  lea     eax, [esp+664h+WideCharStr]
0x10011903  jnz     short loc_10011916
0x10011905  push    105h; int
0x1001190a  push    eax; lpWideCharStr
0x1001190b  push    edi; Src
0x1001190c  push    dword ptr [ebp+30h]; int
0x1001190f  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x10011914  jmp     short loc_10011950
0x10011916  mov     esi, edi
0x10011918  lea     ecx, [esp+664h+WideCharStr]
0x1001191f  mov     edx, 105h
0x10011924  sub     esi, eax
0x10011926  lea     eax, [edx+7FFFFEF9h]
0x1001192c  test    eax, eax
0x1001192e  jz      short loc_10011944
0x10011930  movzx   eax, word ptr [esi+ecx]
0x10011934  test    ax, ax
0x10011937  jz      short loc_10011944
0x10011939  mov     [ecx], ax
0x1001193c  add     ecx, 2
0x1001193f  dec     edx
0x10011940  jnz     short loc_10011926
0x10011942  jmp     short loc_10011948
0x10011944  test    edx, edx
0x10011946  jnz     short loc_1001194B
0x10011948  sub     ecx, 2
0x1001194b  xor     eax, eax
0x1001194d  mov     [ecx], ax
0x10011950  push    4B0h; CodePage
0x10011955  push    1; int
0x10011957  push    0FFh; int
0x1001195c  push    0FFh; int
0x10011961  push    105h; int
0x10011966  lea     eax, [esp+678h+pszSrc]
0x1001196d  push    eax; int
0x1001196e  lea     eax, [esp+67Ch+WideCharStr]
0x10011975  push    eax; lpWideCharStr
0x10011976  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x1001197b  test    eax, eax
0x1001197d  jnz     short loc_10011996
0x1001197f  push    1; int
0x10011981  push    edi; pszSrc
0x10011982  push    0FFFFDFFAh; int
0x10011987  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1001198c  mov     eax, 0FFFFFC16h
0x10011991  jmp     loc_10011D48
0x10011996  cmp     word ptr [edi], 0
0x1001199a  jz      loc_10011AD5
0x100119a0  push    offset aNoname; "NoName"
0x100119a5  push    edi
0x100119a6  call    _ascii_wcsicmp
0x100119ab  add     esp, 8
0x100119ae  test    eax, eax
0x100119b0  jz      loc_10011AD5
0x100119b6  lea     esi, [ebx+242h]
0x100119bc  push    esi
0x100119bd  call    _NetProtocolType@4; NetProtocolType(x)
0x100119c2  test    eax, eax
0x100119c4  jz      short loc_10011A15
0x100119c6  mov     esi, [ebx+14h]
0x100119c9  test    esi, esi
0x100119cb  jz      short loc_10011A0B
0x100119cd  mov     esi, [esi+0Ch]
0x100119d0  lea     ecx, [esp+664h+pszDest]
0x100119d4  mov     edx, 105h
0x100119d9  lea     esp, [esp+0]
0x100119e0  lea     eax, [edx+7FFFFEF9h]
0x100119e6  test    eax, eax
0x100119e8  jz      loc_10011AA3
0x100119ee  movzx   eax, word ptr [esi]
0x100119f1  test    ax, ax
0x100119f4  jz      loc_10011AA3
0x100119fa  mov     [ecx], ax
0x100119fd  add     esi, 2
0x10011a00  add     ecx, 2
0x10011a03  dec     edx
0x10011a04  jnz     short loc_100119E0
0x10011a06  jmp     loc_10011AA7
0x10011a0b  mov     esi, 0FFFFFAE7h
0x10011a10  jmp     loc_10011D38
0x10011a15  mov     eax, [ebx+8]
0x10011a18  test    eax, eax
0x10011a1a  jnz     short loc_10011A73
0x10011a1c  lea     ecx, [esp+664h+pszDest]
0x10011a20  mov     edx, 105h
0x10011a25  lea     esi, [ebx+38h]
0x10011a28  mov     eax, ecx
0x10011a2a  sub     esi, eax
0x10011a2c  lea     esp, [esp+0]
0x10011a30  lea     eax, [edx+7FFFFEF9h]
0x10011a36  test    eax, eax
0x10011a38  jz      short loc_10011A4E
0x10011a3a  movzx   eax, word ptr [esi+ecx]
0x10011a3e  test    ax, ax
0x10011a41  jz      short loc_10011A4E
0x10011a43  mov     [ecx], ax
0x10011a46  add     ecx, 2
0x10011a49  dec     edx
0x10011a4a  jnz     short loc_10011A30
0x10011a4c  jmp     short loc_10011A52
0x10011a4e  test    edx, edx
0x10011a50  jnz     short loc_10011A55
0x10011a52  sub     ecx, 2
0x10011a55  xor     eax, eax
0x10011a57  mov     [ecx], ax
0x10011a5a  lea     eax, [esp+664h+pszSrc]
0x10011a61  push    eax; pszSrc
0x10011a62  push    105h; cchDest
0x10011a67  lea     eax, [esp+66Ch+pszDest]
0x10011a6b  push    eax; pszDest
0x10011a6c  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10011a71  jmp     short loc_10011AAF
0x10011a73  cmp     eax, 1
0x10011a76  jnz     short loc_10011ACB
0x10011a78  lea     ecx, [esp+664h+pszDest]
0x10011a7c  mov     edx, 105h
0x10011a81  mov     eax, ecx
0x10011a83  sub     esi, eax
0x10011a85  lea     eax, [edx+7FFFFEF9h]
0x10011a8b  test    eax, eax
0x10011a8d  jz      short loc_10011AA3
0x10011a8f  movzx   eax, word ptr [esi+ecx]
0x10011a93  test    ax, ax
0x10011a96  jz      short loc_10011AA3
0x10011a98  mov     [ecx], ax
0x10011a9b  add     ecx, 2
0x10011a9e  dec     edx
0x10011a9f  jnz     short loc_10011A85
0x10011aa1  jmp     short loc_10011AA7
0x10011aa3  test    edx, edx
0x10011aa5  jnz     short loc_10011AAA
0x10011aa7  sub     ecx, 2
0x10011aaa  xor     eax, eax
0x10011aac  mov     [ecx], ax
0x10011aaf  push    105h; cchDest
0x10011ab4  lea     eax, [esp+668h+pszDest]
0x10011ab8  push    eax; pszDest
0x10011ab9  push    ebx; int
0x10011aba  call    MakeValidTableName
0x10011abf  mov     esi, eax
0x10011ac1  test    esi, esi
0x10011ac3  jnz     loc_10011D38
0x10011ac9  jmp     short loc_10011ADC
0x10011acb  mov     esi, 0FFFFFC17h
0x10011ad0  jmp     loc_10011D38
0x10011ad5  xor     eax, eax
0x10011ad7  mov     [esp+664h+pszDest], ax
0x10011adc  xor     eax, eax
0x10011ade  mov     ecx, 3
0x10011ae3  cmp     dword ptr [ebx+8], 1
0x10011ae7  cmovz   eax, ecx
0x10011aea  push    eax; int
0x10011aeb  lea     eax, [esp+668h+var_62C]
0x10011aef  push    eax; int
0x10011af0  lea     eax, [esp+66Ch+var_650]
0x10011af4  push    eax; int
0x10011af5  lea     eax, [esp+670h+var_654]
0x10011af9  push    eax; int
0x10011afa  push    dword ptr [ebp+368h]; Locale
0x10011b00  lea     eax, [ebp+360h]
0x10011b06  push    dword ptr [ebp+36Ch]; int
0x10011b0c  push    eax; int
0x10011b0d  push    dword ptr [ebp+364h]; int
0x10011b13  lea     eax, [esp+684h+pszDest]
0x10011b17  push    eax; lpFileName
0x10011b18  call    _TextDetectCodePageInfo@36; TextDetectCodePageInfo(x,x,x,x,x,x,x,x,x)
0x10011b1d  mov     esi, eax
0x10011b1f  test    esi, esi
0x10011b21  jnz     loc_10011D38
0x10011b27  push    3
0x10011b29  push    [esp+668h+var_64C]
0x10011b2d  call    _ISAMDBAddVTDef@8; ISAMDBAddVTDef(x,x)
0x10011b32  mov     ebx, eax
0x10011b34  test    ebx, ebx
0x10011b36  jnz     short loc_10011B42
0x10011b38  mov     esi, 0FFFFFC0Dh
0x10011b3d  jmp     loc_10011D38
0x10011b42  mov     dword ptr [ebx+230h], 0
0x10011b4c  lea     ecx, [ebx+26h]
0x10011b4f  mov     dword ptr [ebx+20h], 0
0x10011b56  mov     edx, 105h
0x10011b5b  cmp     word ptr [edi], 0
0x10011b5f  jz      short loc_10011B8E
0x10011b61  lea     esi, [esp+664h+pszSrc]
0x10011b68  sub     esi, ecx
0x10011b6a  lea     ebx, [ebx+0]
0x10011b70  lea     eax, [edx+7FFFFEF9h]
0x10011b76  test    eax, eax
0x10011b78  jz      short loc_10011BB2
0x10011b7a  movzx   eax, word ptr [ecx+esi]
0x10011b7e  test    ax, ax
0x10011b81  jz      short loc_10011BB2
0x10011b83  mov     [ecx], ax
0x10011b86  add     ecx, 2
0x10011b89  dec     edx
0x10011b8a  jnz     short loc_10011B70
0x10011b8c  jmp     short loc_10011BB6
0x10011b8e  lea     esi, [esp+664h+pszDest]
0x10011b92  sub     esi, ecx
0x10011b94  lea     eax, [edx+7FFFFEF9h]
0x10011b9a  test    eax, eax
0x10011b9c  jz      short loc_10011BB2
0x10011b9e  movzx   eax, word ptr [ecx+esi]
0x10011ba2  test    ax, ax
0x10011ba5  jz      short loc_10011BB2
0x10011ba7  mov     [ecx], ax
0x10011baa  add     ecx, 2
0x10011bad  dec     edx
0x10011bae  jnz     short loc_10011B94
0x10011bb0  jmp     short loc_10011BB6
0x10011bb2  test    edx, edx
0x10011bb4  jnz     short loc_10011BB9
0x10011bb6  sub     ecx, 2
0x10011bb9  xor     eax, eax
0x10011bbb  mov     [ecx], ax
0x10011bbe  mov     [esp+664h+var_640], eax
0x10011bc2  mov     [esp+664h+var_63C], eax
0x10011bc6  mov     [esp+664h+var_644], eax
0x10011bca  cmp     [esp+664h+var_650], eax
0x10011bce  jbe     loc_10011CB6
0x10011bd4  xor     ebp, ebp
0x10011bd6  push    20Ch; Size
0x10011bdb  call    _MemAllocate@4; MemAllocate(x)
0x10011be0  mov     edi, eax
0x10011be2  test    edi, edi
0x10011be4  jz      loc_10011CEC
0x10011bea  push    20Ch; Size
0x10011bef  push    0; Val
0x10011bf1  push    edi; void *
0x10011bf2  call    _memset
0x10011bf7  mov     esi, [esp+670h+var_654]
0x10011bfb  lea     ecx, [edi+4]
0x10011bfe  add     esp, 0Ch
0x10011c01  mov     edx, 100h
0x10011c06  add     esi, ebp
0x10011c08  jmp     short loc_10011C10
0x10011c10  lea     eax, [edx+7FFFFEFEh]
0x10011c16  test    eax, eax
0x10011c18  jz      short loc_10011C30
0x10011c1a  movzx   eax, word ptr [esi]
0x10011c1d  test    ax, ax
0x10011c20  jz      short loc_10011C30
0x10011c22  mov     [ecx], ax
0x10011c25  add     esi, 2
0x10011c28  add     ecx, 2
0x10011c2b  dec     edx
0x10011c2c  jnz     short loc_10011C10
0x10011c2e  jmp     short loc_10011C34
0x10011c30  test    edx, edx
0x10011c32  jnz     short loc_10011C37
0x10011c34  sub     ecx, 2
0x10011c37  xor     eax, eax
0x10011c39  mov     [ecx], ax
0x10011c3c  mov     eax, [esp+664h+var_654]
0x10011c40  mov     eax, [eax+ebp+200h]
0x10011c47  mov     [edi+204h], eax
0x10011c4d  mov     eax, [esp+664h+var_654]
0x10011c51  mov     eax, [eax+ebp+204h]
0x10011c58  mov     [edi+208h], eax
0x10011c5e  cmp     dword ptr [ebx+230h], 0
0x10011c65  jnz     short loc_10011C6F
0x10011c67  mov     [ebx+230h], edi
0x10011c6d  jmp     short loc_10011C75
0x10011c6f  mov     eax, [esp+664h+var_640]
0x10011c73  mov     [eax], edi
0x10011c75  mov     esi, [esp+664h+var_644]
0x10011c79  add     ebp, 408h
  ... truncated ...
```
