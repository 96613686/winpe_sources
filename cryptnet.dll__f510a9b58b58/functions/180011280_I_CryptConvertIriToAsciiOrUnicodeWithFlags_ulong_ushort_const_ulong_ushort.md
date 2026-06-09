# I_CryptConvertIriToAsciiOrUnicodeWithFlags(ulong,ushort const *,ulong *,ushort *)

- ea: `0x180011280`
- end: `0x1800119b1`
- name: `?I_CryptConvertIriToAsciiOrUnicodeWithFlags@@YAHKPEBGPEAKPEAG@Z`
- size: `1841`
- prototype: `__int64 __fastcall(DWORD, unsigned __int16 *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001cf90`

## callees

- `0x180003640`
- `0x180005980`
- `0x180007c00`
- `0x18000a990`
- `0x180011280`
- `0x1800119b8`
- `0x180012b4c`
- `0x180012dd4`
- `0x18001bb18`
- `0x18001cef0`
- `0x180026552`
- `0x18002655e`
- `0x1800265b0`
- `0x180026640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800114dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800114dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011856`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001169a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001169a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011848`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011848`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180011711`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180011926`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180011711`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180011926`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x180011337`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x180011378`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x180011337`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x180011378`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180011557`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x1800115a6`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180011557`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x1800115a6`
- `ntdll!wcsstr` at `0x1800113a7`
- `ntdll!wcsstr` at `0x1800113a7`
- `ntdll!wcschr` at `0x18001175b`
- `ntdll!wcschr` at `0x18001175b`

## pseudocode

```c
__int64 __fastcall I_CryptConvertIriToAsciiOrUnicodeWithFlags(
        DWORD a1,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rdi
  int v5; // r12d
  unsigned int v8; // r13d
  __int64 v9; // r14
  HRESULT PartW; // esi
  __int64 v11; // rbx
  wchar_t *v12; // rsi
  __int64 v13; // rbx
  const unsigned __int16 *v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  void *v19; // rax
  unsigned __int16 *v20; // r14
  void *v21; // rbx
  DWORD v23; // ecx
  PWSTR v24; // rsi
  CHAR *v25; // r12
  HRESULT v26; // eax
  int v27; // ebx
  DWORD v28; // eax
  WCHAR *v29; // rax
  HLOCAL v30; // rsi
  __int64 i; // rax
  unsigned __int64 v32; // r9
  WCHAR *v33; // rcx
  unsigned __int64 cchCount2; // rcx
  const WCHAR *v35; // rdx
  HRESULT v36; // eax
  unsigned __int64 j; // rcx
  wchar_t *v38; // rax
  __int64 v39; // rax
  unsigned __int64 v40; // rbx
  __int64 IriWithHttpSchemePrefix; // rax
  __int64 v42; // rax
  DWORD k; // edx
  __int64 v44; // rcx
  signed int LastError; // eax
  __int64 v46; // rax
  DWORD pcchUnescaped; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v48; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pcchEscaped; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszUnescaped[2]; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD pcchOut; // [rsp+40h] [rbp-C0h] BYREF
  int v52; // [rsp+44h] [rbp-BCh]
  HLOCAL v53; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h]
  int v55; // [rsp+58h] [rbp-A8h]
  _BYTE v56[12]; // [rsp+5Ch] [rbp-A4h]
  PWSTR pszEscaped; // [rsp+68h] [rbp-98h]
  HLOCAL v58; // [rsp+70h] [rbp-90h]
  void *Src[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v60; // [rsp+88h] [rbp-78h]
  __int128 v61; // [rsp+98h] [rbp-68h]
  __int64 v62; // [rsp+A8h] [rbp-58h]
  WCHAR pszOut[40]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t SubStr[2088]; // [rsp+100h] [rbp+0h] BYREF

  pszEscaped = a4;
  pcchEscaped = a1;
  v62 = 0;
  pcchOut = 33;
  v4 = a2;
  v48 = 2084;
  v5 = a1 & 0x20000;
  v52 = 0;
  v53 = 0;
  v58 = 0;
  hMem = 0;
  v8 = 1;
  *(_DWORD *)&v56[8] = 0;
  v55 = a1 & 0x20000;
  *(_QWORD *)v56 = (a1 & 0x20000) != 0;
  *(_OWORD *)Src = 0;
  v60 = 0;
  v61 = 0;
  if ( UrlGetPartW(a2, pszOut, &pcchOut, 1u, 0) || !pcchOut )
  {
    v38 = wcschr(v4, 0x3Au);
    if ( v38 )
    {
      v39 = v38 - v4;
      if ( (unsigned int)v39 > 0x20 )
        goto LABEL_117;
      v40 = (unsigned int)v39;
      memcpy_0(pszOut, v4, v40 * 2);
      if ( v40 >= 33 )
        goto LABEL_102;
      pszOut[v40] = 0;
    }
    else
    {
      if ( *a3 >= 2 && *v4 == 92 && v4[1] == 92 )
        goto LABEL_117;
      IriWithHttpSchemePrefix = GetIriWithHttpSchemePrefix(v4);
      *(_QWORD *)&v56[4] = IriWithHttpSchemePrefix;
      if ( !IriWithHttpSchemePrefix )
        goto LABEL_117;
      v4 = (unsigned __int16 *)IriWithHttpSchemePrefix;
    }
  }
  v9 = -1;
  if ( (a1 & 0x4000000) != 0 )
  {
    v25 = 0;
    pcchUnescaped = 1;
    hMem = 0;
    v26 = UrlUnescapeW(v4, pszUnescaped, &pcchUnescaped, 0);
    v27 = v26;
    if ( v26 == -2147467261 || !v26 )
    {
      v28 = pcchUnescaped;
      if ( !pcchUnescaped )
      {
        v28 = 1;
        pcchUnescaped = 1;
      }
      v29 = (WCHAR *)operator new(saturated_mul(v28, 2u));
      v30 = v29;
      if ( !v29 )
      {
        v27 = -2147024882;
LABEL_87:
        v23 = v27;
        goto LABEL_35;
      }
      v27 = UrlUnescapeW(v4, v29, &pcchUnescaped, 0);
      if ( v27 )
      {
LABEL_96:
        operator delete(v30);
        v30 = hMem;
      }
      else
      {
        v27 = 0;
        for ( i = 0; v4[i]; ++i )
        {
          if ( v4[i] > 0x7Fu )
            goto LABEL_49;
        }
        for ( j = 0; j < pcchUnescaped; ++j )
        {
          if ( *((_WORD *)v30 + j) > 0x7Fu )
          {
            v25 = (CHAR *)operator new(pcchUnescaped + 1);
            if ( !v25 )
            {
              v27 = -2147024882;
              goto LABEL_96;
            }
            v42 = pcchUnescaped;
            for ( k = 0; k < pcchUnescaped; v42 = pcchUnescaped )
            {
              v44 = k++;
              v25[v44] = *((_BYTE *)v30 + 2 * v44);
            }
            v25[v42] = 0;
            if ( !MultiByteToWideChar(0xFDE9u, 0, v25, -1, (LPWSTR)v30, pcchUnescaped + 1) )
            {
              LastError = GetLastError();
              v27 = LastError;
              if ( LastError > 0 )
                v27 = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_96;
            }
            break;
          }
        }
LABEL_49:
        hMem = v30;
      }
      if ( v25 )
        operator delete(v25);
      if ( !v27 )
      {
        v5 = v55;
        v4 = (unsigned __int16 *)v30;
        goto LABEL_4;
      }
    }
    if ( v27 >= 0 )
      v27 = -2147467259;
    goto LABEL_87;
  }
LABEL_4:
  PartW = UrlGetPartW(v4, SubStr, &v48, 2u, 0);
  if ( PartW )
  {
    v32 = 0;
    v33 = pszOut;
    do
    {
      if ( !*v33 )
        break;
      ++v32;
      ++v33;
    }
    while ( v32 < 5 );
    cchCount2 = 0;
    v35 = L"ldap";
    do
    {
      if ( !*v35 )
        break;
      ++cchCount2;
      ++v35;
    }
    while ( cchCount2 < 5 );
    if ( CompareStringW(0x409u, 1u, pszOut, v32, L"ldap", cchCount2) != 2 )
    {
      if ( PartW >= 0 )
        PartW = -2147467259;
      v23 = PartW;
      goto LABEL_35;
    }
    if ( !(unsigned int)LdapCrackUrl(0, v4, (__int64)Src) )
      goto LABEL_16;
    v52 = 1;
    if ( !Src[0] )
    {
      LODWORD(v11) = 0;
      SubStr[0] = 0;
      v48 = 0;
      goto LABEL_6;
    }
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)Src[0] + v11) );
    v48 = v11;
    if ( (unsigned int)v11 < 0x824 )
    {
      memcpy_0(SubStr, Src[0], 2LL * (unsigned int)v11);
      if ( 2 * (unsigned __int64)(unsigned int)v11 < 0x1048 )
      {
        SubStr[(unsigned int)v11] = 0;
        goto LABEL_6;
      }
LABEL_102:
      _report_rangecheckfailure();
    }
LABEL_117:
    v23 = 87;
    goto LABEL_35;
  }
  LODWORD(v11) = v48;
LABEL_6:
  if ( (_DWORD)v11 && (v5 || (pcchEscaped & 0x2000000) != 0) )
  {
    v12 = wcsstr(v4, SubStr);
    if ( !v12 )
    {
      v23 = 13;
      goto LABEL_35;
    }
    v13 = v48;
    if ( !(unsigned int)I_ConvertIdnHostNameToAsciiOrUnicode(*(unsigned int *)v56, SubStr, &v53) )
      goto LABEL_16;
    v14 = &v12[v13];
    if ( v53 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)v53 + v15) );
    }
    else
    {
      LODWORD(v15) = 0;
    }
    if ( v14 )
    {
      do
        ++v9;
      while ( v14[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    v16 = v12 - v4;
    v17 = (unsigned int)(v16 + v9 + 1 + v15);
    v18 = (unsigned int)v17;
    v19 = (void *)PkiZeroAlloc(2 * v17);
    v58 = v19;
    v20 = (unsigned __int16 *)v19;
    if ( !v19 )
      goto LABEL_16;
    memcpy_0(v19, v4, 2LL * (unsigned int)v16);
    StringCchCatW(v20, v18, (const unsigned __int16 *)v53);
    StringCchCatW(v20, v18, v14);
    v4 = v20;
  }
  else
  {
    if ( v4 )
    {
      do
        ++v9;
      while ( v4[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    v18 = (int)v9 + 1;
  }
  if ( (pcchEscaped & 0x40000) != 0 )
  {
    pcchEscaped = 1;
    v36 = UrlEscapeW(v4, pszUnescaped, &pcchEscaped, 0xA0040000);
    if ( v36 != -2147467261 )
      goto LABEL_68;
    if ( pcchEscaped > *a3 )
    {
      *a3 = pcchEscaped;
      goto LABEL_34;
    }
    v24 = pszEscaped;
    v36 = UrlEscapeW(v4, pszEscaped, a3, 0xA0040000);
    if ( v36 )
    {
LABEL_68:
      if ( v36 >= 0 )
        v36 = -2147467259;
      v23 = v36;
      goto LABEL_35;
    }
    if ( *a3 )
    {
      v46 = *a3 - 1;
      if ( v24[v46] == 47 && v18 > 1 && v4[v18 - 2] != 47 )
      {
        v24[v46] = 0;
        --*a3;
      }
    }
  }
  else
  {
    if ( (unsigned int)v18 > *a3 )
    {
      *a3 = v18;
LABEL_34:
      v23 = -2146893784;
LABEL_35:
      SetLastError(v23);
LABEL_16:
      v21 = *(void **)&v56[4];
      v8 = 0;
      goto LABEL_17;
    }
    v24 = pszEscaped;
    memcpy_0(pszEscaped, v4, 2 * v18);
  }
  v21 = *(void **)&v56[4];
  if ( *(_QWORD *)&v56[4] )
  {
    memmove_0(v24, v24 + 7, 2LL * *a3 - 14);
    *a3 -= 7;
    v24[*a3] = 0;
  }
LABEL_17:
  if ( v52 )
    LdapFreeUrlComponents(Src);
  if ( v53 )
    operator delete(v53);
  if ( v58 )
    operator delete(v58);
  if ( hMem )
    operator delete(hMem);
  if ( v21 )
    operator delete(v21);
  return v8;
}

```

## disassembly

```asm
0x180011280  mov     [rsp-8+arg_0], rbx
0x180011285  push    rbp
0x180011286  push    rsi
0x180011287  push    rdi
0x180011288  push    r12
0x18001128a  push    r13
0x18001128c  push    r14
0x18001128e  push    r15
0x180011290  lea     rbp, [rsp-1060h]
0x180011298  mov     eax, 1160h
0x18001129d  call    _alloca_probe
0x1800112a2  sub     rsp, rax
0x1800112a5  mov     rax, cs:__security_cookie
0x1800112ac  xor     rax, rsp
0x1800112af  mov     [rbp+1090h+var_40], rax
0x1800112b6  xor     r14d, r14d
0x1800112b9  mov     [rsp+1190h+pszEscaped], r9
0x1800112be  xor     eax, eax
0x1800112c0  mov     [rsp+1190h+pcchEscaped], ecx
0x1800112c4  xorps   xmm0, xmm0
0x1800112c7  mov     [rbp+1090h+var_10E8], rax
0x1800112cb  mov     r12d, ecx
0x1800112ce  mov     [rsp+1190h+pcchOut], 21h ; '!'
0x1800112d6  mov     rdi, rdx
0x1800112d9  mov     [rsp+1190h+var_115C], 824h
0x1800112e1  and     r12d, 20000h
0x1800112e8  mov     [rsp+1190h+var_114C], r14d
0x1800112ed  mov     r15, r8
0x1800112f0  mov     [rsp+1190h+var_1148], r14
0x1800112f5  mov     esi, ecx
0x1800112f7  mov     [rsp+1190h+var_1120], r14
0x1800112fc  setnz   al
0x1800112ff  mov     [rsp+1190h+hMem], r14
0x180011304  lea     r13d, [r14+1]
0x180011308  mov     [rsp+1190h+var_1130], r14
0x18001130d  mov     r9d, r13d; dwPart
0x180011310  mov     [rsp+1190h+var_1138], r12d
0x180011315  lea     r8, [rsp+1190h+pcchOut]; pcchOut
0x18001131a  mov     [rsp+1190h+var_1134], eax
0x18001131e  lea     rdx, [rbp+1090h+pszOut]; pszOut
0x180011322  mov     [rsp+1190h+dwFlags], r14d; dwFlags
0x180011327  mov     rcx, rdi; pszIn
0x18001132a  movups  xmmword ptr [rsp+1190h+Src], xmm0
0x18001132f  movups  [rbp+1090h+var_1108], xmm0
0x180011333  movups  [rbp+1090h+var_10F8], xmm0
0x180011337  call    cs:__imp_UrlGetPartW
0x18001133d  test    eax, eax
0x18001133f  jnz     loc_180011753
0x180011345  cmp     [rsp+1190h+pcchOut], r14d
0x18001134a  jz      loc_180011753
0x180011350  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011354  bt      esi, 1Ah
0x180011358  jb      loc_18001153A
0x18001135e  mov     r9d, 2; dwPart
0x180011364  mov     [rsp+1190h+dwFlags], 0; dwFlags
0x18001136c  lea     r8, [rsp+1190h+var_115C]; pcchOut
0x180011371  mov     rcx, rdi; pszIn
0x180011374  lea     rdx, [rbp+1090h+SubStr]; pszOut
0x180011378  call    cs:__imp_UrlGetPartW
0x18001137e  xor     r8d, r8d
0x180011381  mov     esi, eax
0x180011383  test    eax, eax
0x180011385  jnz     loc_18001164B
0x18001138b  mov     ebx, [rsp+1190h+var_115C]
0x18001138f  test    ebx, ebx
0x180011391  jz      loc_1800114A7
0x180011397  test    r12d, r12d
0x18001139a  jz      loc_1800118E7
0x1800113a0  lea     rdx, [rbp+1090h+SubStr]; SubStr
0x1800113a4  mov     rcx, rdi; Str
0x1800113a7  call    cs:__imp_wcsstr
0x1800113ad  mov     rsi, rax
0x1800113b0  test    rax, rax
0x1800113b3  jz      loc_1800118FA
0x1800113b9  mov     ecx, [rsp+1190h+var_1134]
0x1800113bd  lea     r8, [rsp+1190h+var_1148]
0x1800113c2  mov     ebx, [rsp+1190h+var_115C]
0x1800113c6  lea     rdx, [rbp+1090h+SubStr]
0x1800113ca  call    I_ConvertIdnHostNameToAsciiOrUnicode
0x1800113cf  xor     r8d, r8d
0x1800113d2  test    eax, eax
0x1800113d4  jz      short loc_180011434
0x1800113d6  lea     r12, [rsi+rbx*2]
0x1800113da  mov     rax, [rsp+1190h+var_1148]
0x1800113df  test    rax, rax
0x1800113e2  jz      loc_1800116E7
0x1800113e8  mov     rcx, r14
0x1800113eb  inc     rcx
0x1800113ee  cmp     [rax+rcx*2], r8w
0x1800113f3  jnz     short loc_1800113EB
0x1800113f5  test    r12, r12
0x1800113f8  jz      loc_1800116EF
0x1800113fe  inc     r14
0x180011401  cmp     [r12+r14*2], r8w
0x180011406  jnz     short loc_1800113FE
0x180011408  lea     eax, [r14+1]
0x18001140c  sub     rsi, rdi
0x18001140f  sar     rsi, 1
0x180011412  add     eax, esi
0x180011414  add     ecx, eax
0x180011416  mov     ebx, ecx
0x180011418  add     rcx, rcx; uBytes
0x18001141b  call    PkiZeroAlloc
0x180011420  xor     r8d, r8d
0x180011423  mov     [rsp+1190h+var_1120], rax
0x180011428  mov     r14, rax
0x18001142b  test    rax, rax
0x18001142e  jnz     loc_1800115D0
0x180011434  mov     rbx, [rsp+1190h+var_1130]
0x180011439  mov     r13d, r8d
0x18001143c  cmp     [rsp+1190h+var_114C], r8d
0x180011441  jnz     loc_18001197B
0x180011447  mov     rax, [rsp+1190h+var_1148]
0x18001144c  test    rax, rax
0x18001144f  jnz     loc_18001198A
0x180011455  mov     rax, [rsp+1190h+var_1120]
0x18001145a  test    rax, rax
0x18001145d  jnz     loc_180011997
0x180011463  mov     rax, [rsp+1190h+hMem]
0x180011468  test    rax, rax
0x18001146b  jnz     loc_180011636
0x180011471  test    rbx, rbx
0x180011474  jnz     loc_1800119A4
0x18001147a  mov     eax, r13d
0x18001147d  mov     rcx, [rbp+1090h+var_40]
0x180011484  xor     rcx, rsp; StackCookie
0x180011487  call    __security_check_cookie
0x18001148c  mov     rbx, [rsp+1190h+arg_0]
0x180011494  add     rsp, 1160h
0x18001149b  pop     r15
0x18001149d  pop     r14
0x18001149f  pop     r13
0x1800114a1  pop     r12
0x1800114a3  pop     rdi
0x1800114a4  pop     rsi
0x1800114a5  pop     rbp
0x1800114a6  retn
0x1800114a7  test    rdi, rdi
0x1800114aa  jz      loc_180011643
0x1800114b0  inc     r14
0x1800114b3  cmp     [rdi+r14*2], r8w
0x1800114b8  jnz     short loc_1800114B0
0x1800114ba  lea     eax, [r14+1]
0x1800114be  movsxd  rbx, eax
0x1800114c1  test    [rsp+1190h+pcchEscaped], 40000h
0x1800114c9  jnz     loc_1800116F7
0x1800114cf  cmp     ebx, [r15]
0x1800114d2  jbe     short loc_1800114EA
0x1800114d4  mov     [r15], ebx
0x1800114d7  mov     ecx, 80090028h; dwErrCode
0x1800114dc  call    cs:__imp_SetLastError
0x1800114e2  xor     r8d, r8d
0x1800114e5  jmp     loc_180011434
0x1800114ea  mov     rsi, [rsp+1190h+pszEscaped]
0x1800114ef  lea     r8, [rbx+rbx]; Size
0x1800114f3  mov     rcx, rsi; void *
0x1800114f6  mov     rdx, rdi; Src
0x1800114f9  call    memcpy_0
0x1800114fe  xor     r8d, r8d
0x180011501  mov     rbx, [rsp+1190h+var_1130]
0x180011506  test    rbx, rbx
0x180011509  jz      loc_18001143C
0x18001150f  mov     r8d, [r15]
0x180011512  lea     rdx, [rsi+0Eh]; Src
0x180011516  mov     rcx, rsi; void *
0x180011519  lea     r8, ds:0FFFFFFFFFFFFFFF2h[r8*2]; Size
0x180011521  call    memmove_0
0x180011526  add     dword ptr [r15], 0FFFFFFF9h
0x18001152a  mov     ecx, [r15]
0x18001152d  xor     r8d, r8d
0x180011530  mov     [rsi+rcx*2], r8w
0x180011535  jmp     loc_18001143C
0x18001153a  xor     r12d, r12d
0x18001153d  mov     [rsp+1190h+pcchUnescaped], r13d
0x180011542  xor     r9d, r9d; dwFlags
0x180011545  mov     [rsp+1190h+hMem], r12
0x18001154a  lea     r8, [rsp+1190h+pcchUnescaped]; pcchUnescaped
0x18001154f  mov     rcx, rdi; pszUrl
0x180011552  lea     rdx, [rsp+1190h+pszUnescaped]; pszUnescaped
0x180011557  call    cs:__imp_UrlUnescapeW
0x18001155d  mov     ebx, eax
0x18001155f  cmp     eax, 80004003h
0x180011564  jnz     loc_1800117D4
0x18001156a  mov     eax, [rsp+1190h+pcchUnescaped]
0x18001156e  test    eax, eax
0x180011570  jz      loc_18001162A
0x180011576  mov     ecx, eax
0x180011578  mov     eax, 2
0x18001157d  mul     rcx
0x180011580  cmovb   rax, r14
0x180011584  mov     rcx, rax; uBytes
0x180011587  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001158c  mov     rsi, rax
0x18001158f  test    rax, rax
0x180011592  jz      loc_1800117EC
0x180011598  xor     r9d, r9d; dwFlags
0x18001159b  lea     r8, [rsp+1190h+pcchUnescaped]; pcchUnescaped
0x1800115a0  mov     rdx, rax; pszUnescaped
0x1800115a3  mov     rcx, rdi; pszUrl
0x1800115a6  call    cs:__imp_UrlUnescapeW
0x1800115ac  mov     ebx, eax
0x1800115ae  test    eax, eax
0x1800115b0  jnz     loc_18001186B
0x1800115b6  xor     ebx, ebx
0x1800115b8  mov     eax, ebx
0x1800115ba  cmp     [rdi+rax*2], bx
0x1800115be  jz      loc_180011733
0x1800115c4  cmp     word ptr [rdi+rax*2], 7Fh
0x1800115c9  ja      short loc_180011607
0x1800115cb  add     rax, r13
0x1800115ce  jmp     short loc_1800115BA
0x1800115d0  mov     r8d, esi
0x1800115d3  mov     rdx, rdi; Src
0x1800115d6  add     r8, r8; Size
0x1800115d9  mov     rcx, r14; void *
0x1800115dc  call    memcpy_0
0x1800115e1  mov     r8, [rsp+1190h+var_1148]; unsigned __int16 *
0x1800115e6  mov     rdx, rbx; unsigned __int64
0x1800115e9  mov     rcx, r14; unsigned __int16 *
0x1800115ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800115f1  mov     r8, r12; unsigned __int16 *
0x1800115f4  mov     rdx, rbx; unsigned __int64
0x1800115f7  mov     rcx, r14; unsigned __int16 *
0x1800115fa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800115ff  mov     rdi, r14
0x180011602  jmp     loc_1800114C1
0x180011607  mov     [rsp+1190h+hMem], rsi
0x18001160c  test    r12, r12
0x18001160f  jnz     loc_18001187D
0x180011615  test    ebx, ebx
0x180011617  jnz     loc_1800117DC
0x18001161d  mov     r12d, [rsp+1190h+var_1138]
0x180011622  mov     rdi, rsi
0x180011625  jmp     loc_18001135E
0x18001162a  mov     eax, r13d
0x18001162d  mov     [rsp+1190h+pcchUnescaped], eax
0x180011631  jmp     loc_180011576
0x180011636  mov     rcx, rax; hMem
0x180011639  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001163e  jmp     loc_180011471
0x180011643  mov     r14d, r8d
0x180011646  jmp     loc_1800114BA
0x18001164b  mov     r9, r8
0x18001164e  lea     rcx, [rbp+1090h+pszOut]
0x180011652  cmp     r8w, [rcx]
0x180011656  jz      short loc_180011665
0x180011658  add     r9, r13; cchCount1
0x18001165b  add     rcx, 2
0x18001165f  cmp     r9, 5
0x180011663  jb      short loc_180011652
0x180011665  lea     r10, aLdap; "ldap"
0x18001166c  mov     rcx, r8
0x18001166f  mov     rdx, r10
0x180011672  cmp     r8w, [rdx]
0x180011676  jz      short loc_180011685
0x180011678  add     rcx, r13
0x18001167b  add     rdx, 2
0x18001167f  cmp     rcx, 5
0x180011683  jb      short loc_180011672
0x180011685  mov     [rsp+1190h+cchCount2], ecx; cchCount2
0x180011689  lea     r8, [rbp+1090h+pszOut]; lpString1
0x18001168d  mov     ecx, 409h; Locale
0x180011692  mov     qword ptr [rsp+1190h+dwFlags], r10; lpString2
0x180011697  mov     edx, r13d; dwCmpFlags
0x18001169a  call    cs:__imp_CompareStringW
0x1800116a0  cmp     eax, 2
0x1800116a3  jnz     loc_1800118D6
0x1800116a9  lea     r8, [rsp+1190h+Src]
0x1800116ae  mov     rdx, rdi
0x1800116b1  xor     ecx, ecx
0x1800116b3  call    LdapCrackUrl
0x1800116b8  xor     r8d, r8d
0x1800116bb  test    eax, eax
0x1800116bd  jz      loc_180011434
0x1800116c3  mov     rdx, [rsp+1190h+Src]; Src
0x1800116c8  mov     [rsp+1190h+var_114C], r13d
0x1800116cd  test    rdx, rdx
0x1800116d0  jnz     loc_18001188A
0x1800116d6  mov     ebx, r8d
0x1800116d9  mov     [rbp+1090h+SubStr], r8w
0x1800116de  mov     [rsp+1190h+var_115C], ebx
0x1800116e2  jmp     loc_18001138F
0x1800116e7  mov     ecx, r8d
0x1800116ea  jmp     loc_1800113F5
0x1800116ef  mov     r14d, r8d
0x1800116f2  jmp     loc_180011408
0x1800116f7  mov     esi, 0A0040000h
0x1800116fc  mov     [rsp+1190h+pcchEscaped], r13d
0x180011701  mov     r9d, esi; dwFlags
0x180011704  lea     r8, [rsp+1190h+pcchEscaped]; pcchEscaped
0x180011709  lea     rdx, [rsp+1190h+pszUnescaped]; pszEscaped
0x18001170e  mov     rcx, rdi; pszUrl
0x180011711  call    cs:__imp_UrlEscapeW
0x180011717  cmp     eax, 80004003h
0x18001171c  jz      loc_180011904
0x180011722  test    eax, eax
0x180011724  mov     ebx, 80004005h
0x180011729  cmovns  eax, ebx
0x18001172c  mov     ecx, eax
0x18001172e  jmp     loc_1800114DC
  ... truncated ...
```
