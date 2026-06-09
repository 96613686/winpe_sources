# LocateTableInDatabase(x,x,x,x)

- ea: `0x100108e0`
- end: `0x10010ee8`
- name: `_LocateTableInDatabase@16`
- size: `1544`
- prototype: `int __stdcall(int, STRSAFE_LPCWSTR, int, int)`
- caller_count: `8`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1000f0e0`
- `0x10011060`
- `0x100113f0`
- `0x10016b70`
- `0x10016bf0`
- `0x10016d90`
- `0x10016fc0`
- `0x100170e0`

## callees

- `0x1000a1f0`
- `0x1000a470`
- `0x1000a590`
- `0x1000a740`
- `0x1000ad60`
- `0x1000b600`
- `0x1000b640`
- `0x1000bf60`
- `0x1000bf80`
- `0x1000c2f0`
- `0x1000e350`
- `0x1000ff30`
- `0x10010870`
- `0x100108e0`
- `0x10013ee0`
- `0x10014270`
- `0x10014690`
- `0x10014740`
- `0x1001ca70`
- `0x1002a2b0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall LocateTableInDatabase(_DWORD *a1, unsigned __int16 *a2, _DWORD *a3, int a4)
{
  char *v4; // ebp
  int result; // eax
  int v6; // eax
  wchar_t *v7; // ecx
  int v8; // edx
  wchar_t v9; // ax
  int v10; // eax
  _DWORD *v11; // esi
  WCHAR *v12; // ecx
  int v13; // edx
  WCHAR v14; // ax
  int v15; // eax
  int v16; // edx
  wchar_t *v17; // ecx
  int v18; // esi
  wchar_t v19; // ax
  int v20; // edx
  wchar_t *v21; // ecx
  wchar_t v22; // ax
  wchar_t *v23; // ecx
  wchar_t v24; // ax
  int v25; // eax
  wchar_t *v26; // ecx
  int v27; // edx
  wchar_t v28; // ax
  int v29; // eax
  int v30; // eax
  int v31; // ebx
  DWORD v32; // eax
  _DWORD *v33; // eax
  int v34; // esi
  int v35; // [esp+4h] [ebp-A50h]
  __int64 v36; // [esp+14h] [ebp-A40h] BYREF
  int v37; // [esp+1Ch] [ebp-A38h]
  wchar_t pszSrc[262]; // [esp+20h] [ebp-A34h] BYREF
  wchar_t FileName[262]; // [esp+22Ch] [ebp-828h] BYREF
  wchar_t pszDest[262]; // [esp+438h] [ebp-61Ch] BYREF
  wchar_t Ext[256]; // [esp+644h] [ebp-410h] BYREF
  WCHAR WideCharStr[262]; // [esp+844h] [ebp-210h] BYREF

  v4 = (char *)a1[1];
  v35 = 0;
  v36 = 0;
  v37 = 0;
  *a3 = 0;
  if ( !wcslen(a2) )
    return -1003;
  v6 = *((_DWORD *)v4 + 2);
  if ( v6 != 1 )
  {
    if ( v6 )
    {
      v12 = WideCharStr;
      v13 = 261;
      while ( v13 != -2147483385 )
      {
        v14 = *(WCHAR *)((char *)v12 + (char *)a2 - (char *)WideCharStr);
        if ( !v14 )
          break;
        *v12++ = v14;
        if ( !--v13 )
        {
          --v12;
          break;
        }
      }
      *v12 = 0;
    }
    else
    {
      TranslateNames(a1[12], a2, WideCharStr, 261);
    }
    if ( !MakeIntoValidFilename(WideCharStr, (int)pszSrc, 261, 255, 255, 1, 0x4B0u) )
      goto LABEL_10;
    v10 = ISAMDBLocateTable(v4, pszSrc);
    if ( v10 )
    {
LABEL_12:
      *a3 = v10;
      return 0;
    }
    v15 = NetProtocolType(v4 + 578);
    v16 = 261;
    if ( v15 )
    {
      v17 = pszDest;
      v18 = v4 + 578 - (char *)pszDest;
      while ( v16 != -2147483385 )
      {
        v19 = *(wchar_t *)((char *)v17 + v18);
        if ( !v19 )
          break;
        *v17++ = v19;
        if ( !--v16 )
        {
          --v17;
          break;
        }
      }
      *v17 = 0;
      StringCchCatW(pszDest, 0x105u, pszSrc);
      result = DownloadToLocal((int)v4, pszDest, FileName, 0x105u);
      if ( result )
      {
        if ( result != -1305 )
          return result;
        if ( !a4 )
          return -1305;
        SplitPath(pszSrc, 0, 0, 0, 0, 0, 0, Ext, 0xFFu);
        if ( Ext[0] )
          goto LABEL_47;
        v20 = 261;
        v21 = pszDest;
        while ( v20 != -2147483385 )
        {
          v22 = *(wchar_t *)((char *)v21 + v18);
          if ( !v22 )
            break;
          *v21++ = v22;
          if ( !--v20 )
          {
            --v21;
            break;
          }
        }
        *v21 = 0;
        StringCchCatW(pszSrc, 0x105u, L".txt");
        StringCchCatW(pszDest, 0x105u, pszSrc);
        result = DownloadToLocal((int)v4, pszDest, FileName, 0x105u);
        if ( result )
        {
          if ( result != -1305 )
            return result;
          goto LABEL_47;
        }
      }
      v35 = 1;
    }
    else
    {
      v23 = FileName;
      while ( v16 != -2147483385 )
      {
        v24 = *(wchar_t *)((char *)v23 + v4 - (char *)FileName + 56);
        if ( !v24 )
          break;
        *v23++ = v24;
        if ( !--v16 )
        {
          --v23;
          break;
        }
      }
      *v23 = 0;
      StringCchCatW(FileName, 0x105u, pszSrc);
    }
    v25 = DOSFileExists(FileName);
    switch ( v25 )
    {
      case 0:
        goto LABEL_77;
      case -3:
LABEL_57:
        ErrorSetExtendedInfoSz1(-8161, FileName, 0);
        return -1023;
      case -5:
        ErrorSetExtendedInfoSz1(-8160, a2, 1);
        return -1032;
      case -21:
        return -1021;
    }
    if ( !a4 )
      return -1305;
    SplitPath(pszSrc, 0, 0, 0, 0, 0, 0, Ext, 0xFFu);
    if ( !Ext[0] )
    {
      if ( *((_DWORD *)v4 + 2) )
        StringCchCatW(pszSrc, 0x105u, L".htm");
      else
        StringCchCatW(pszSrc, 0x105u, L".txt");
      v26 = FileName;
      v27 = 261;
      while ( v27 != -2147483385 )
      {
        v28 = *(wchar_t *)((char *)v26 + v4 - (char *)FileName + 56);
        if ( !v28 )
          break;
        *v26++ = v28;
        if ( !--v27 )
        {
          --v26;
          break;
        }
      }
      *v26 = 0;
      StringCchCatW(FileName, 0x105u, pszSrc);
      v29 = DOSFileExists(FileName);
      if ( v29 )
      {
        if ( v29 == -3 )
          goto LABEL_57;
        if ( v29 == -5 )
        {
          ErrorSetExtendedInfoSz1(-8160, pszSrc, 1);
          return -1032;
        }
        if ( v29 != -21 )
        {
LABEL_18:
          ErrorSetExtendedInfoSz1(-8300, pszSrc, 1);
          return -1305;
        }
        return -1021;
      }
LABEL_77:
      if ( !IsAcceptableFileName(pszSrc) )
        return -1809;
      goto LABEL_79;
    }
LABEL_47:
    ErrorSetExtendedInfoSz1(-8300, a2, 1);
    return -1305;
  }
  v7 = pszSrc;
  v8 = 261;
  while ( v8 != -2147483385 )
  {
    v9 = *(wchar_t *)((char *)v7 + (char *)a2 - (char *)pszSrc);
    if ( !v9 )
      break;
    *v7++ = v9;
    if ( !--v8 )
    {
      --v7;
      break;
    }
  }
  *v7 = 0;
  if ( !IsValidJETName(pszSrc, 0x4B0u) )
  {
LABEL_10:
    ErrorSetExtendedInfoSz1(-8198, a2, 1);
    return -1002;
  }
  v10 = ISAMDBLocateTable(v4, pszSrc);
  if ( v10 )
    goto LABEL_12;
  v11 = (_DWORD *)*((_DWORD *)v4 + 4);
  if ( !v11 )
    goto LABEL_18;
  while ( DBlstrcmpi(pszSrc, v11 + 1) )
  {
    v11 = (_DWORD *)*v11;
    if ( !v11 )
      goto LABEL_18;
  }
LABEL_79:
  v30 = ISAMDBAddTable(v4, pszSrc);
  v31 = v30;
  if ( !v30 )
    return -1011;
  *(_DWORD *)(v30 + 896) = v35;
  qmemcpy((void *)(v30 + 12), a1 + 3, 0x348u);
  if ( *((_DWORD *)v4 + 11) == -1 || (v32 = CurrentTaskHandle(), v33 = ISAMDBFindTask(v32), GetImexInfo(v33, &v36) != 1) )
    *(_DWORD *)(v31 + 900) = 2;
  else
    *(_DWORD *)(v31 + 900) = v37;
  if ( *(_DWORD *)(v31 + 900) <= 1u )
  {
    v34 = ExceptionsTableCreate(*((_DWORD *)v4 + 10), *((_DWORD *)v4 + 11), v37, pszSrc, v31 + 908);
    if ( v34 )
    {
      ISAMDBDeleteTable(v4, v31);
      return v34;
    }
  }
  DOSFileSize(FileName, (DWORD *)(v31 + 864));
  *a3 = v31;
  return 0;
}

```

## disassembly

```asm
0x100108e0  sub     esp, 0A50h
0x100108e6  mov     eax, ___security_cookie
0x100108eb  xor     eax, esp
0x100108ed  mov     [esp+0A50h+var_4], eax
0x100108f4  push    ebx
0x100108f5  mov     ebx, [esp+0A54h+arg_8]
0x100108fc  xorps   xmm0, xmm0
0x100108ff  push    ebp
0x10010900  push    esi
0x10010901  mov     esi, [esp+0A5Ch+arg_0]
0x10010908  push    edi
0x10010909  mov     edi, [esp+0A60h+arg_4]
0x10010910  mov     ecx, edi
0x10010912  mov     [esp+0A60h+var_A4C], esi
0x10010916  mov     ebp, [esi+4]
0x10010919  mov     [esp+0A60h+var_A48], ebx
0x1001091d  mov     [esp+0A60h+var_A50], 0
0x10010925  lea     edx, [ecx+2]
0x10010928  movq    [esp+0A60h+var_A40], xmm0
0x1001092e  mov     [esp+0A60h+var_A38], 0
0x10010936  mov     dword ptr [ebx], 0
0x1001093c  lea     esp, [esp+0]
0x10010940  mov     ax, [ecx]
0x10010943  add     ecx, 2
0x10010946  test    ax, ax
0x10010949  jnz     short loc_10010940
0x1001094b  sub     ecx, edx
0x1001094d  sar     ecx, 1
0x1001094f  jnz     short loc_1001095B
0x10010951  mov     eax, 0FFFFFC15h
0x10010956  jmp     loc_10010ECD
0x1001095b  mov     eax, [ebp+8]
0x1001095e  cmp     eax, 1
0x10010961  jnz     loc_10010A24
0x10010967  lea     ecx, [esp+0A60h+pszSrc]
0x1001096b  mov     esi, edi
0x1001096d  mov     eax, ecx
0x1001096f  mov     edx, 105h
0x10010974  sub     esi, eax
0x10010976  lea     eax, [edx+7FFFFEF9h]
0x1001097c  test    eax, eax
0x1001097e  jz      short loc_10010994
0x10010980  movzx   eax, word ptr [esi+ecx]
0x10010984  test    ax, ax
0x10010987  jz      short loc_10010994
0x10010989  mov     [ecx], ax
0x1001098c  add     ecx, 2
0x1001098f  dec     edx
0x10010990  jnz     short loc_10010976
0x10010992  jmp     short loc_10010998
0x10010994  test    edx, edx
0x10010996  jnz     short loc_1001099B
0x10010998  sub     ecx, 2
0x1001099b  xor     eax, eax
0x1001099d  mov     [ecx], ax
0x100109a0  lea     eax, [esp+0A60h+pszSrc]
0x100109a4  push    4B0h; CodePage
0x100109a9  push    eax; lpWideCharStr
0x100109aa  call    _IsValidJETName@8; IsValidJETName(x,x)
0x100109af  test    eax, eax
0x100109b1  jnz     short loc_100109CA
0x100109b3  push    1; int
0x100109b5  push    edi; pszSrc
0x100109b6  push    0FFFFDFFAh; int
0x100109bb  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x100109c0  mov     eax, 0FFFFFC16h
0x100109c5  jmp     loc_10010ECD
0x100109ca  lea     eax, [esp+0A60h+pszSrc]
0x100109ce  push    eax
0x100109cf  push    ebp
0x100109d0  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x100109d5  test    eax, eax
0x100109d7  jz      short loc_100109E0
0x100109d9  mov     [ebx], eax
0x100109db  jmp     loc_10010ECB
0x100109e0  mov     esi, [ebp+10h]
0x100109e3  test    esi, esi
0x100109e5  jz      short loc_10010A09
0x100109e7  lea     eax, [esi+4]
0x100109ea  push    eax
0x100109eb  lea     eax, [esp+0A64h+pszSrc]
0x100109ef  push    eax
0x100109f0  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x100109f5  test    eax, eax
0x100109f7  jz      short loc_10010A01
0x100109f9  mov     esi, [esi]
0x100109fb  test    esi, esi
0x100109fd  jnz     short loc_100109E7
0x100109ff  jmp     short loc_10010A09
0x10010a01  test    esi, esi
0x10010a03  jnz     loc_10010E09
0x10010a09  push    1; int
0x10010a0b  lea     eax, [esp+0A64h+pszSrc]
0x10010a0f  push    eax; pszSrc
0x10010a10  push    0FFFFDF94h; int
0x10010a15  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10010a1a  mov     eax, 0FFFFFAE7h
0x10010a1f  jmp     loc_10010ECD
0x10010a24  test    eax, eax
0x10010a26  lea     eax, [esp+0A60h+WideCharStr]
0x10010a2d  jnz     short loc_10010A40
0x10010a2f  push    105h; int
0x10010a34  push    eax; lpWideCharStr
0x10010a35  push    edi; Src
0x10010a36  push    dword ptr [esi+30h]; int
0x10010a39  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x10010a3e  jmp     short loc_10010A7A
0x10010a40  mov     esi, edi
0x10010a42  lea     ecx, [esp+0A60h+WideCharStr]
0x10010a49  mov     edx, 105h
0x10010a4e  sub     esi, eax
0x10010a50  lea     eax, [edx+7FFFFEF9h]
0x10010a56  test    eax, eax
0x10010a58  jz      short loc_10010A6E
0x10010a5a  movzx   eax, word ptr [esi+ecx]
0x10010a5e  test    ax, ax
0x10010a61  jz      short loc_10010A6E
0x10010a63  mov     [ecx], ax
0x10010a66  add     ecx, 2
0x10010a69  dec     edx
0x10010a6a  jnz     short loc_10010A50
0x10010a6c  jmp     short loc_10010A72
0x10010a6e  test    edx, edx
0x10010a70  jnz     short loc_10010A75
0x10010a72  sub     ecx, 2
0x10010a75  xor     eax, eax
0x10010a77  mov     [ecx], ax
0x10010a7a  push    4B0h; CodePage
0x10010a7f  push    1; int
0x10010a81  push    0FFh; int
0x10010a86  push    0FFh; int
0x10010a8b  push    105h; int
0x10010a90  lea     eax, [esp+0A74h+pszSrc]
0x10010a94  push    eax; int
0x10010a95  lea     eax, [esp+0A78h+WideCharStr]
0x10010a9c  push    eax; lpWideCharStr
0x10010a9d  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x10010aa2  test    eax, eax
0x10010aa4  jz      loc_100109B3
0x10010aaa  lea     eax, [esp+0A60h+pszSrc]
0x10010aae  push    eax
0x10010aaf  push    ebp
0x10010ab0  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x10010ab5  test    eax, eax
0x10010ab7  jnz     loc_100109D9
0x10010abd  lea     esi, [ebp+242h]
0x10010ac3  push    esi
0x10010ac4  call    _NetProtocolType@4; NetProtocolType(x)
0x10010ac9  mov     ebx, [esp+0A60h+arg_C]
0x10010ad0  mov     edx, 105h
0x10010ad5  test    eax, eax
0x10010ad7  jz      loc_10010C45
0x10010add  lea     ecx, [esp+0A60h+pszDest]
0x10010ae4  mov     eax, ecx
0x10010ae6  sub     esi, eax
0x10010ae8  jmp     short loc_10010AF0
0x10010af0  lea     eax, [edx+7FFFFEF9h]
0x10010af6  test    eax, eax
0x10010af8  jz      short loc_10010B0E
0x10010afa  movzx   eax, word ptr [esi+ecx]
0x10010afe  test    ax, ax
0x10010b01  jz      short loc_10010B0E
0x10010b03  mov     [ecx], ax
0x10010b06  add     ecx, 2
0x10010b09  dec     edx
0x10010b0a  jnz     short loc_10010AF0
0x10010b0c  jmp     short loc_10010B12
0x10010b0e  test    edx, edx
0x10010b10  jnz     short loc_10010B15
0x10010b12  sub     ecx, 2
0x10010b15  xor     eax, eax
0x10010b17  mov     [ecx], ax
0x10010b1a  lea     eax, [esp+0A60h+pszSrc]
0x10010b1e  push    eax; pszSrc
0x10010b1f  push    105h; cchDest
0x10010b24  lea     eax, [esp+0A68h+pszDest]
0x10010b2b  push    eax; pszDest
0x10010b2c  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10010b31  push    105h; cchDest
0x10010b36  lea     eax, [esp+0A64h+FileName]
0x10010b3d  push    eax; pszDest
0x10010b3e  lea     eax, [esp+0A68h+pszDest]
0x10010b45  push    eax; pszSrc
0x10010b46  push    ebp; int
0x10010b47  call    DownloadToLocal
0x10010b4c  test    eax, eax
0x10010b4e  jz      loc_10010C3B
0x10010b54  cmp     eax, 0FFFFFAE7h
0x10010b59  jnz     loc_10010ECD
0x10010b5f  test    ebx, ebx
0x10010b61  jz      loc_10010A1A
0x10010b67  push    0FFh; ExtCount
0x10010b6c  lea     eax, [esp+0A64h+Ext]
0x10010b73  push    eax; Ext
0x10010b74  push    0; FilenameCount
0x10010b76  push    0; Filename
0x10010b78  push    0; DirCount
0x10010b7a  push    0; Dir
0x10010b7c  push    0; DriveCount
0x10010b7e  push    0; Drive
0x10010b80  lea     eax, [esp+0A80h+pszSrc]
0x10010b84  push    eax; FullPath
0x10010b85  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x10010b8a  cmp     [esp+0A60h+Ext], 0
0x10010b93  jnz     loc_10010C24
0x10010b99  mov     edx, 105h
0x10010b9e  lea     ecx, [esp+0A60h+pszDest]
0x10010ba5  lea     eax, [edx+7FFFFEF9h]
0x10010bab  test    eax, eax
0x10010bad  jz      short loc_10010BC3
0x10010baf  movzx   eax, word ptr [esi+ecx]
0x10010bb3  test    ax, ax
0x10010bb6  jz      short loc_10010BC3
0x10010bb8  mov     [ecx], ax
0x10010bbb  add     ecx, 2
0x10010bbe  dec     edx
0x10010bbf  jnz     short loc_10010BA5
0x10010bc1  jmp     short loc_10010BC7
0x10010bc3  test    edx, edx
0x10010bc5  jnz     short loc_10010BCA
0x10010bc7  sub     ecx, 2
0x10010bca  xor     eax, eax
0x10010bcc  push    offset aTxt; ".txt"
0x10010bd1  mov     [ecx], ax
0x10010bd4  lea     eax, [esp+0A64h+pszSrc]
0x10010bd8  push    105h; cchDest
0x10010bdd  push    eax; pszDest
0x10010bde  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10010be3  lea     eax, [esp+0A60h+pszSrc]
0x10010be7  push    eax; pszSrc
0x10010be8  push    105h; cchDest
0x10010bed  lea     eax, [esp+0A68h+pszDest]
0x10010bf4  push    eax; pszDest
0x10010bf5  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10010bfa  push    105h; cchDest
0x10010bff  lea     eax, [esp+0A64h+FileName]
0x10010c06  push    eax; pszDest
0x10010c07  lea     eax, [esp+0A68h+pszDest]
0x10010c0e  push    eax; pszSrc
0x10010c0f  push    ebp; int
0x10010c10  call    DownloadToLocal
0x10010c15  test    eax, eax
0x10010c17  jz      short loc_10010C3B
0x10010c19  cmp     eax, 0FFFFFAE7h
0x10010c1e  jnz     loc_10010ECD
0x10010c24  push    1; int
0x10010c26  push    edi; pszSrc
0x10010c27  push    0FFFFDF94h; int
0x10010c2c  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10010c31  mov     eax, 0FFFFFAE7h
0x10010c36  jmp     loc_10010ECD
0x10010c3b  mov     [esp+0A60h+var_A50], 1
0x10010c43  jmp     short loc_10010C96
0x10010c45  lea     ecx, [esp+0A60h+FileName]
0x10010c4c  mov     eax, ebp
0x10010c4e  mov     esi, ecx
0x10010c50  sub     eax, esi
0x10010c52  lea     esi, [eax+38h]
0x10010c55  lea     eax, [edx+7FFFFEF9h]
0x10010c5b  test    eax, eax
0x10010c5d  jz      short loc_10010C73
0x10010c5f  movzx   eax, word ptr [esi+ecx]
0x10010c63  test    ax, ax
0x10010c66  jz      short loc_10010C73
0x10010c68  mov     [ecx], ax
0x10010c6b  add     ecx, 2
0x10010c6e  dec     edx
0x10010c6f  jnz     short loc_10010C55
0x10010c71  jmp     short loc_10010C77
0x10010c73  test    edx, edx
0x10010c75  jnz     short loc_10010C7A
0x10010c77  sub     ecx, 2
0x10010c7a  xor     eax, eax
0x10010c7c  mov     [ecx], ax
0x10010c7f  lea     eax, [esp+0A60h+pszSrc]
0x10010c83  push    eax; pszSrc
0x10010c84  push    105h; cchDest
0x10010c89  lea     eax, [esp+0A68h+FileName]
0x10010c90  push    eax; pszDest
0x10010c91  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10010c96  lea     eax, [esp+0A60h+FileName]
0x10010c9d  push    eax; lpFileName
0x10010c9e  call    _DOSFileExists@4; DOSFileExists(x)
0x10010ca3  test    eax, eax
0x10010ca5  jz      loc_10010DF1
0x10010cab  cmp     eax, 0FFFFFFFDh
0x10010cae  jnz     short loc_10010CCE
0x10010cb0  push    0; int
0x10010cb2  lea     eax, [esp+0A64h+FileName]
0x10010cb9  push    eax; pszSrc
0x10010cba  push    0FFFFE01Fh; int
0x10010cbf  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10010cc4  mov     eax, 0FFFFFC01h
0x10010cc9  jmp     loc_10010ECD
0x10010cce  cmp     eax, 0FFFFFFFBh
0x10010cd1  jnz     short loc_10010CEA
0x10010cd3  push    1; int
0x10010cd5  push    edi; pszSrc
0x10010cd6  push    0FFFFE020h; int
0x10010cdb  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
  ... truncated ...
```
