# InetCreateRequestHeaders(ushort const *,int,_CRYPT_RETRIEVE_AUX_INFO *,int *,_FILETIME *)

- ea: `0x180004b40`
- end: `0x1800052c9`
- name: `?InetCreateRequestHeaders@@YAPEAGPEBGHPEAU_CRYPT_RETRIEVE_AUX_INFO@@PEAHPEAU_FILETIME@@@Z`
- size: `1929`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, int, struct _CRYPT_RETRIEVE_AUX_INFO *, int *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180003640`
- `0x180003e7c`
- `0x180004b40`
- `0x180005900`
- `0x180005940`
- `0x1800063b0`
- `0x1800077b0`
- `0x18000a990`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000510f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000510f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005121`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005121`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004c8c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004c8c`
- `ntdll!_ultow` at `0x180004ee1`
- `ntdll!_ultow` at `0x180004ee1`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180004ca3`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180004ca3`

## string_xrefs

- `0x180004f24`: `Cache-Control: max-age = `

## pseudocode

```c
unsigned __int16 *__fastcall InetCreateRequestHeaders(
        const unsigned __int16 *a1,
        int a2,
        struct _CRYPT_RETRIEVE_AUX_INFO *a3,
        int *a4,
        struct _FILETIME *a5)
{
  int v7; // r15d
  const unsigned __int16 *v8; // rdi
  __int64 v9; // rbx
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  unsigned __int16 *v11; // rbp
  __int64 v12; // rsi
  LPWSTR pwszCacheFileNamePrefix; // r8
  void *CacheFile; // r14
  int v15; // r14d
  int v16; // eax
  int v17; // ebp
  __int64 v18; // rax
  int v19; // ebp
  unsigned __int16 *v20; // r12
  struct _FILETIME *v21; // rdi
  int v23; // esi
  __int64 v24; // rax
  unsigned __int64 v25; // r15
  const wchar_t *v26; // r14
  __int64 v27; // r13
  int v28; // ebx
  unsigned __int64 v29; // rcx
  unsigned __int16 *v30; // rax
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rcx
  unsigned __int16 *v33; // rax
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  unsigned __int16 *v36; // rax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // r9
  int v39; // eax
  const wchar_t *v40; // r8
  bool v41; // zf
  unsigned __int64 v42; // rax
  __int64 v43; // rcx
  unsigned __int16 *v44; // rdx
  unsigned __int16 *v45; // rcx
  unsigned __int64 v46; // r15
  wchar_t *v47; // rcx
  unsigned __int16 *i; // rax
  unsigned __int16 *v49; // rcx
  unsigned __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  unsigned __int64 v52; // r8
  unsigned __int64 v53; // rcx
  unsigned __int16 *v54; // rax
  unsigned __int64 v55; // rdx
  __int64 v56; // r8
  unsigned __int64 v57; // rax
  const wchar_t *v58; // r9
  unsigned __int16 *v59; // rdx
  unsigned __int16 *v60; // rcx
  const wchar_t *v61; // rdx
  unsigned __int16 *v62; // r9
  __int64 v63; // rcx
  unsigned __int64 v64; // r8
  unsigned __int16 *v65; // rcx
  LPFILETIME pftCacheResync; // rcx
  LPFILETIME v67; // rbp
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // rcx
  unsigned __int16 *v70; // rax
  unsigned __int64 v71; // rax
  unsigned __int16 *v72; // r8
  __int64 v73; // rcx
  unsigned __int64 v74; // rdx
  unsigned __int16 *v75; // rcx
  const wchar_t *v76; // r9
  unsigned __int64 v77; // rax
  __int64 v78; // rdx
  unsigned __int16 *v79; // r8
  unsigned __int16 *v80; // rcx
  unsigned int v81; // ecx
  int v82; // [rsp+30h] [rbp-158h]
  int v83; // [rsp+34h] [rbp-154h]
  HLOCAL hMem; // [rsp+38h] [rbp-150h]
  int v85; // [rsp+48h] [rbp-140h]
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-128h] BYREF
  wchar_t Buffer[40]; // [rsp+70h] [rbp-118h] BYREF
  WCHAR pwszTime[64]; // [rsp+C0h] [rbp-C8h] BYREF

  v83 = 0;
  v7 = 0;
  v8 = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  LODWORD(v9) = 0;
  v85 = 0;
  v82 = 0;
  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  v11 = CryptnetUrlCacheDir;
  v12 = -1;
  if ( !CryptnetUrlCacheDir )
  {
    hMem = 0;
    operator delete(0);
    goto LABEL_7;
  }
  pwszCacheFileNamePrefix = 0;
  if ( a3 && a3->cbSize > 0x30 && a3->pwszCacheFileNamePrefix )
    pwszCacheFileNamePrefix = a3->pwszCacheFileNamePrefix;
  CacheFile = (void *)I_UrlCacheCreateCacheFile(CryptnetUrlCacheDir, L"MetaData", pwszCacheFileNamePrefix, 0);
  if ( !CacheFile )
  {
    operator delete(v11);
    v16 = 0;
    hMem = 0;
    v15 = 0;
    goto LABEL_21;
  }
  hMem = (HLOCAL)I_UrlCacheReadAndValidateMetaDataFile(CacheFile, (__int64)&SystemTime);
  operator delete(v11);
  I_UrlCacheCloseHandle(CacheFile);
  if ( !hMem || *((_WORD *)hMem + 42) != 1 || *((__int16 *)hMem + 43) >= 0 )
  {
    v8 = *(const unsigned __int16 **)&SystemTime.wYear;
LABEL_7:
    v15 = 0;
    v16 = 0;
    goto LABEL_21;
  }
  v8 = *(const unsigned __int16 **)&SystemTime.wYear;
  v7 = 1;
  if ( *(_QWORD *)&SystemTime.wYear )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*(_QWORD *)&SystemTime.wYear + 2 * v9) );
    if ( (_DWORD)v9 )
    {
      v15 = v9 + 15;
      v83 = 1;
      v17 = 1;
    }
    else
    {
      v15 = 0;
      v17 = 0;
    }
  }
  else
  {
    v15 = 0;
    v17 = 0;
  }
  if ( !*((_DWORD *)hMem + 22) && !*((_DWORD *)hMem + 23) )
    goto LABEL_20;
  SystemTime = 0;
  if ( !FileTimeToSystemTime((const FILETIME *)hMem + 11, &SystemTime) )
    goto LABEL_20;
  if ( !WinHttpTimeFromSystemTime(&SystemTime, pwszTime) )
    goto LABEL_20;
  pwszTime[62] = 0;
  v18 = -1;
  do
    ++v18;
  while ( pwszTime[v18] );
  v85 = v18;
  if ( (_DWORD)v18 )
  {
    v83 = 1;
    v15 += v18 + 19;
    v16 = v17 + 1;
    v82 = v17 + 1;
  }
  else
  {
LABEL_20:
    v16 = v17;
    v82 = v17;
  }
LABEL_21:
  v19 = 0;
  if ( a2 )
  {
    LODWORD(v38) = 0;
    v39 = 0;
    if ( a3 )
    {
      if ( a3->cbSize > 0x38 )
      {
        pftCacheResync = a3->pftCacheResync;
        if ( pftCacheResync )
        {
          if ( pftCacheResync->dwLowDateTime || pftCacheResync->dwHighDateTime )
          {
            *(_QWORD *)&SystemTime.wYear = 0;
            GetSystemTimeAsFileTime((LPFILETIME)&SystemTime);
            v67 = a3->pftCacheResync;
            if ( CompareFileTime((const FILETIME *)&SystemTime, v67) <= 0 )
            {
              v19 = 0;
              LODWORD(v38) = 0;
              v39 = 1;
            }
            else
            {
              v68 = *(_QWORD *)&SystemTime.wYear - *(_QWORD *)v67;
              v19 = 0;
              v39 = 1;
              v38 = v68 / 0x989680;
            }
          }
        }
      }
    }
    if ( v7 && (v81 = *((_DWORD *)hMem + 24)) != 0 )
    {
      if ( !v39 || v81 < (unsigned int)v38 )
        LODWORD(v38) = *((_DWORD *)hMem + 24);
    }
    else if ( !v39 )
    {
      v16 = v82;
      goto LABEL_22;
    }
    _ultow(v38, Buffer, 10);
    Buffer[33] = 0;
    do
      ++v12;
    while ( Buffer[v12] );
    v16 = v82;
    v19 = v12;
    if ( (_DWORD)v12 )
    {
      v15 += v12 + 25;
      v16 = ++v82;
    }
  }
LABEL_22:
  v20 = 0;
  if ( !v16
    || (v23 = v16 - 1,
        v24 = (unsigned int)(v15 + 2 * (v16 - 1) + 1),
        v25 = (unsigned int)v24,
        (v20 = (unsigned __int16 *)PkiNonzeroAlloc(2 * v24)) == 0) )
  {
    v21 = (struct _FILETIME *)hMem;
    *a4 = 0;
    goto LABEL_24;
  }
  v26 = L"\r\n";
  *v20 = 0;
  v27 = 2147483646;
  if ( !(_DWORD)v9 )
  {
    v28 = v82;
LABEL_29:
    v21 = (struct _FILETIME *)hMem;
    goto LABEL_30;
  }
  v28 = v23;
  if ( v25 - 1 <= 0x7FFFFFFE )
  {
    v50 = v25;
    v51 = v20;
    while ( *v51 )
    {
      ++v51;
      if ( !--v50 )
      {
        v52 = 0;
        goto LABEL_91;
      }
    }
    v52 = v25 - v50;
LABEL_91:
    if ( v50 )
    {
      v76 = L"If-None-Match: ";
      v77 = v25 - v52;
      v41 = v25 == v52;
      v78 = 2147483646;
      v79 = &v20[v52];
      if ( !v41 )
      {
        do
        {
          if ( !v78 )
            break;
          if ( !*v76 )
            break;
          *v79++ = *v76++;
          --v78;
          --v77;
        }
        while ( v77 );
      }
      v80 = v79 - 1;
      if ( v77 )
        v80 = v79;
      *v80 = 0;
    }
  }
  StringCchCatW(v20, v25, v8);
  if ( !v23 || !v25 || v25 > 0x7FFFFFFF )
    goto LABEL_29;
  v53 = v25;
  v54 = v20;
  while ( *v54 )
  {
    ++v54;
    if ( !--v53 )
    {
      v55 = 0;
      goto LABEL_100;
    }
  }
  v55 = v25 - v53;
LABEL_100:
  v21 = (struct _FILETIME *)hMem;
  if ( v53 )
  {
    v56 = 2147483646;
    v57 = v25 - v55;
    v41 = v25 == v55;
    v58 = L"\r\n";
    v59 = &v20[v55];
    if ( !v41 )
    {
      do
      {
        if ( !v56 )
          break;
        if ( !*v58 )
          break;
        *v59++ = *v58++;
        --v56;
        --v57;
      }
      while ( v57 );
    }
    v60 = v59 - 1;
    if ( v57 )
      v60 = v59;
    *v60 = 0;
  }
LABEL_30:
  if ( v85 )
  {
    if ( v25 && v25 <= 0x7FFFFFFF )
    {
      v29 = v25;
      v30 = v20;
      while ( *v30 )
      {
        ++v30;
        if ( !--v29 )
        {
          v31 = 0;
          goto LABEL_38;
        }
      }
      v31 = v25 - v29;
LABEL_38:
      if ( v29 )
      {
        v61 = L"If-Modified-Since: ";
        v62 = &v20[v31];
        v63 = 2147483646;
        v64 = v25 - v31;
        if ( v25 != v31 )
        {
          do
          {
            if ( !v63 )
              break;
            if ( !*v61 )
              break;
            *v62++ = *v61++;
            --v63;
            --v64;
          }
          while ( v64 );
        }
        v65 = v62 - 1;
        if ( v64 )
          v65 = v62;
        *v65 = 0;
      }
    }
    StringCchCatW(v20, v25, pwszTime);
    if ( v28 != 1 && v25 && v25 <= 0x7FFFFFFF )
    {
      v69 = v25;
      v70 = v20;
      while ( *v70 )
      {
        ++v70;
        if ( !--v69 )
        {
          v71 = 0;
          goto LABEL_127;
        }
      }
      v71 = v25 - v69;
LABEL_127:
      if ( v69 )
      {
        v72 = &v20[v71];
        v73 = 2147483646;
        v74 = v25 - v71;
        if ( v25 != v71 )
        {
          do
          {
            if ( !v73 )
              break;
            if ( !*v26 )
              break;
            *v72++ = *v26++;
            --v73;
            --v74;
          }
          while ( v74 );
        }
        v75 = v72 - 1;
        if ( v74 )
          v75 = v72;
        *v75 = 0;
      }
    }
  }
  if ( !v19 )
    goto LABEL_56;
  if ( v25 )
  {
    if ( v25 > 0x7FFFFFFF )
      goto LABEL_56;
    v32 = v25;
    v33 = v20;
    while ( *v33 )
    {
      ++v33;
      if ( !--v32 )
      {
        v34 = 0;
        goto LABEL_48;
      }
    }
    v34 = v25 - v32;
LABEL_48:
    if ( v32 )
    {
      v40 = L"Cache-Control: max-age = ";
      v42 = v25 - v34;
      v41 = v25 == v34;
      v43 = 2147483646;
      v44 = &v20[v34];
      if ( !v41 )
      {
        do
        {
          if ( !v43 )
            break;
          if ( !*v40 )
            break;
          *v44++ = *v40++;
          --v43;
          --v42;
        }
        while ( v42 );
      }
      v45 = v44 - 1;
      if ( v42 )
        v45 = v44;
      *v45 = 0;
      v35 = v25;
LABEL_50:
      v36 = v20;
      while ( *v36 )
      {
        ++v36;
        if ( !--v35 )
        {
          v37 = 0;
          goto LABEL_55;
        }
      }
      v37 = v25 - v35;
LABEL_55:
      if ( v35 )
      {
        v46 = v25 - v37;
        v47 = Buffer;
        for ( i = &v20[v37]; v46; --v46 )
        {
          if ( !v27 )
            break;
          if ( !*v47 )
            break;
          *i++ = *v47++;
          --v27;
        }
        v49 = i - 1;
        if ( v46 )
          v49 = i;
        *v49 = 0;
      }
      goto LABEL_56;
    }
  }
  v35 = v25;
  if ( v25 )
    goto LABEL_50;
LABEL_56:
  *a4 = v83;
  if ( v83 )
    *a5 = v21[2];
LABEL_24:
  operator delete(v21);
  return v20;
}

```

## disassembly

```asm
0x180004b40  mov     [rsp+arg_8], rbx
0x180004b45  push    rbp
0x180004b46  push    rsi
0x180004b47  push    rdi
0x180004b48  push    r12
0x180004b4a  push    r13
0x180004b4c  push    r14
0x180004b4e  push    r15
0x180004b50  sub     rsp, 150h
0x180004b57  mov     rax, cs:__security_cookie
0x180004b5e  xor     rax, rsp
0x180004b61  mov     [rsp+188h+var_48], rax
0x180004b69  mov     rax, [rsp+188h+arg_20]
0x180004b71  mov     r13, r8
0x180004b74  mov     [rsp+188h+var_130], rax
0x180004b79  mov     r12d, edx
0x180004b7c  xor     eax, eax
0x180004b7e  mov     [rsp+188h+var_138], r9
0x180004b83  mov     [rsp+188h+var_154], eax
0x180004b87  mov     r15d, eax
0x180004b8a  mov     edi, eax
0x180004b8c  mov     qword ptr [rsp+188h+SystemTime.wYear], rax
0x180004b91  mov     ebx, eax
0x180004b93  mov     dword ptr [rsp+188h+var_140], eax
0x180004b97  mov     [rsp+188h+var_158], eax
0x180004b9b  mov     r14, rcx
0x180004b9e  mov     dword ptr [rsp+188h+var_148], eax
0x180004ba2  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x180004ba7  mov     rbp, rax
0x180004baa  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180004bb1  test    rax, rax
0x180004bb4  jz      loc_180004D3C
0x180004bba  xor     r8d, r8d; void *
0x180004bbd  test    r13, r13
0x180004bc0  jz      short loc_180004BCD
0x180004bc2  cmp     dword ptr [r13+0], 30h ; '0'
0x180004bc7  ja      loc_180004E8E
0x180004bcd  mov     r9, r14
0x180004bd0  mov     dword ptr [rsp+188h+var_168], ebx; int
0x180004bd4  lea     rdx, aMetadata; "MetaData"
0x180004bdb  mov     rcx, rbp; Src
0x180004bde  call    I_UrlCacheCreateCacheFile
0x180004be3  mov     r14, rax
0x180004be6  test    rax, rax
0x180004be9  jz      loc_1800051EB
0x180004bef  lea     rax, [rsp+188h+SystemTime]
0x180004bf4  xor     r9d, r9d
0x180004bf7  xor     r8d, r8d
0x180004bfa  mov     [rsp+188h+var_168], rax; __int64
0x180004bff  xor     edx, edx
0x180004c01  mov     rcx, r14; hFile
0x180004c04  call    I_UrlCacheReadAndValidateMetaDataFile
0x180004c09  mov     rcx, rbp; hMem
0x180004c0c  mov     [rsp+188h+hMem], rax
0x180004c11  mov     rdi, rax
0x180004c14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c19  mov     rcx, r14; hObject
0x180004c1c  call    I_UrlCacheCloseHandle
0x180004c21  test    rdi, rdi
0x180004c24  jnz     loc_1800052B5
0x180004c2a  mov     rdi, qword ptr [rsp+188h+SystemTime.wYear]
0x180004c2f  mov     r14d, ebx
0x180004c32  mov     eax, ebx
0x180004c34  jmp     loc_180004CDF
0x180004c39  cmp     [rdi+56h], bx
0x180004c3d  jge     short loc_180004C2A
0x180004c3f  mov     rdi, qword ptr [rsp+188h+SystemTime.wYear]
0x180004c44  mov     r15d, eax
0x180004c47  test    rdi, rdi
0x180004c4a  jz      loc_1800051E1
0x180004c50  mov     rbx, rsi
0x180004c53  inc     rbx
0x180004c56  cmp     word ptr [rdi+rbx*2], 0
0x180004c5b  jnz     short loc_180004C53
0x180004c5d  test    ebx, ebx
0x180004c5f  jnz     loc_1800050E1
0x180004c65  mov     r14d, dword ptr [rsp+188h+var_148]
0x180004c6a  mov     ebp, r14d
0x180004c6d  mov     rcx, [rsp+188h+hMem]
0x180004c72  add     rcx, 58h ; 'X'; lpFileTime
0x180004c76  cmp     dword ptr [rcx], 0
0x180004c79  jz      loc_180004E9E
0x180004c7f  xorps   xmm0, xmm0
0x180004c82  lea     rdx, [rsp+188h+SystemTime]; lpSystemTime
0x180004c87  movups  xmmword ptr [rsp+188h+SystemTime.wYear], xmm0
0x180004c8c  call    cs:__imp_FileTimeToSystemTime
0x180004c92  test    eax, eax
0x180004c94  jz      short loc_180004CD9
0x180004c96  lea     rdx, [rsp+188h+pwszTime]; pwszTime
0x180004c9e  lea     rcx, [rsp+188h+SystemTime]; pst
0x180004ca3  call    cs:__imp_WinHttpTimeFromSystemTime
0x180004ca9  test    eax, eax
0x180004cab  jz      short loc_180004CD9
0x180004cad  xor     eax, eax
0x180004caf  lea     rcx, [rsp+188h+pwszTime]
0x180004cb7  mov     [rsp+188h+var_4C], ax
0x180004cbf  mov     rax, rsi
0x180004cc2  inc     rax
0x180004cc5  cmp     word ptr [rcx+rax*2], 0
0x180004cca  jnz     short loc_180004CC2
0x180004ccc  mov     [rsp+188h+var_140], rax
0x180004cd1  test    eax, eax
0x180004cd3  jnz     loc_180005250
0x180004cd9  mov     eax, ebp
0x180004cdb  mov     [rsp+188h+var_158], eax
0x180004cdf  xor     ebp, ebp
0x180004ce1  mov     [rsp+188h+var_148], rbp
0x180004ce6  test    r12d, r12d
0x180004ce9  jnz     loc_180004EAD
0x180004cef  xor     r12d, r12d
0x180004cf2  test    eax, eax
0x180004cf4  jnz     short loc_180004D4E
0x180004cf6  mov     rcx, [rsp+188h+var_138]
0x180004cfb  mov     rdi, [rsp+188h+hMem]
0x180004d00  mov     dword ptr [rcx], 0
0x180004d06  mov     rcx, rdi; hMem
0x180004d09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004d0e  mov     rax, r12
0x180004d11  mov     rcx, [rsp+188h+var_48]
0x180004d19  xor     rcx, rsp; StackCookie
0x180004d1c  call    __security_check_cookie
0x180004d21  mov     rbx, [rsp+188h+arg_8]
0x180004d29  add     rsp, 150h
0x180004d30  pop     r15
0x180004d32  pop     r14
0x180004d34  pop     r13
0x180004d36  pop     r12
0x180004d38  pop     rdi
0x180004d39  pop     rsi
0x180004d3a  pop     rbp
0x180004d3b  retn
0x180004d3c  mov     rcx, rbp; hMem
0x180004d3f  mov     [rsp+188h+hMem], rbx
0x180004d44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004d49  jmp     loc_180004C2F
0x180004d4e  lea     esi, [rax-1]
0x180004d51  lea     eax, ds:1[rsi*2]
0x180004d58  add     eax, r14d
0x180004d5b  mov     r15d, eax
0x180004d5e  lea     rcx, [rax+rax]; uBytes
0x180004d62  call    PkiNonzeroAlloc
0x180004d67  mov     r12, rax
0x180004d6a  test    rax, rax
0x180004d6d  jz      short loc_180004CF6
0x180004d6f  xor     eax, eax
0x180004d71  lea     r14, asc_1800296A0; "\r\n"
0x180004d78  mov     [r12], ax
0x180004d7d  mov     r13d, 7FFFFFFEh
0x180004d83  test    ebx, ebx
0x180004d85  jnz     loc_180004FB7
0x180004d8b  mov     ebx, [rsp+188h+var_158]
0x180004d8f  mov     rdi, [rsp+188h+hMem]
0x180004d94  cmp     dword ptr [rsp+188h+var_140], 0
0x180004d99  jz      short loc_180004DF1
0x180004d9b  test    r15, r15
0x180004d9e  jz      short loc_180004DD3
0x180004da0  cmp     r15, 7FFFFFFFh
0x180004da7  ja      short loc_180004DD3
0x180004da9  mov     rcx, r15
0x180004dac  mov     rax, r12
0x180004daf  nop
0x180004db0  cmp     word ptr [rax], 0
0x180004db4  jz      short loc_180004DC4
0x180004db6  add     rax, 2
0x180004dba  sub     rcx, 1
0x180004dbe  jnz     short loc_180004DB0
0x180004dc0  xor     eax, eax
0x180004dc2  jmp     short loc_180004DCA
0x180004dc4  mov     rax, r15
0x180004dc7  sub     rax, rcx
0x180004dca  test    rcx, rcx
0x180004dcd  jnz     loc_180005094
0x180004dd3  lea     r8, [rsp+188h+pwszTime]; unsigned __int16 *
0x180004ddb  mov     rdx, r15; unsigned __int64
0x180004dde  mov     rcx, r12; unsigned __int16 *
0x180004de1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004de6  lea     eax, [rbx-1]
0x180004de9  test    eax, eax
0x180004deb  jnz     loc_18000515B
0x180004df1  test    ebp, ebp
0x180004df3  jz      short loc_180004E6A
0x180004df5  test    r15, r15
0x180004df8  jz      short loc_180004E33
0x180004dfa  cmp     r15, 7FFFFFFFh
0x180004e01  ja      short loc_180004E6A
0x180004e03  mov     rcx, r15
0x180004e06  mov     rax, r12
0x180004e09  nop     dword ptr [rax+00000000h]
0x180004e10  cmp     word ptr [rax], 0
0x180004e14  jz      short loc_180004E24
0x180004e16  add     rax, 2
0x180004e1a  sub     rcx, 1
0x180004e1e  jnz     short loc_180004E10
0x180004e20  xor     edx, edx
0x180004e22  jmp     short loc_180004E2A
0x180004e24  mov     rdx, r15
0x180004e27  sub     rdx, rcx
0x180004e2a  test    rcx, rcx
0x180004e2d  jnz     loc_180004F21
0x180004e33  mov     rcx, r15
0x180004e36  test    r15, r15
0x180004e39  jz      short loc_180004E6A
0x180004e3b  cmp     rcx, 7FFFFFFFh
0x180004e42  ja      short loc_180004E6A
0x180004e44  mov     rax, r12
0x180004e47  cmp     word ptr [rax], 0
0x180004e4b  jz      short loc_180004E5B
0x180004e4d  add     rax, 2
0x180004e51  sub     rcx, 1
0x180004e55  jnz     short loc_180004E47
0x180004e57  xor     eax, eax
0x180004e59  jmp     short loc_180004E61
0x180004e5b  mov     rax, r15
0x180004e5e  sub     rax, rcx
0x180004e61  test    rcx, rcx
0x180004e64  jnz     loc_180004F73
0x180004e6a  mov     eax, [rsp+188h+var_154]
0x180004e6e  mov     rcx, [rsp+188h+var_138]
0x180004e73  mov     [rcx], eax
0x180004e75  test    eax, eax
0x180004e77  jz      loc_180004D06
0x180004e7d  mov     rcx, [rsp+188h+var_130]
0x180004e82  mov     rax, [rdi+10h]
0x180004e86  mov     [rcx], rax
0x180004e89  jmp     loc_180004D06
0x180004e8e  mov     rcx, [r13+30h]
0x180004e92  test    rcx, rcx
0x180004e95  cmovnz  r8, rcx
0x180004e99  jmp     loc_180004BCD
0x180004e9e  cmp     dword ptr [rcx+4], 0
0x180004ea2  jz      loc_180004CD9
0x180004ea8  jmp     loc_180004C7F
0x180004ead  xor     r9d, r9d
0x180004eb0  xor     eax, eax
0x180004eb2  test    r13, r13
0x180004eb5  jz      short loc_180004EC2
0x180004eb7  cmp     dword ptr [r13+0], 38h ; '8'
0x180004ebc  ja      loc_1800050F0
0x180004ec2  test    r15d, r15d
0x180004ec5  jnz     loc_180005270
0x180004ecb  test    eax, eax
0x180004ecd  jz      loc_180005267
0x180004ed3  mov     r8d, 0Ah; Radix
0x180004ed9  lea     rdx, [rsp+188h+Buffer]; Buffer
0x180004ede  mov     ecx, r9d; Value
0x180004ee1  call    cs:__imp__ultow
0x180004ee7  xor     eax, eax
0x180004ee9  mov     [rsp+188h+var_D6], ax
0x180004ef1  lea     rax, [rsp+188h+Buffer]
0x180004ef6  inc     rsi
0x180004ef9  cmp     word ptr [rax+rsi*2], 0
0x180004efe  jnz     short loc_180004EF6
0x180004f00  mov     eax, [rsp+188h+var_158]
0x180004f04  mov     rbp, rsi
0x180004f07  test    esi, esi
0x180004f09  jz      loc_180004CEF
0x180004f0f  add     r14d, 19h
0x180004f13  add     r14d, esi
0x180004f16  inc     eax
0x180004f18  mov     [rsp+188h+var_158], eax
0x180004f1c  jmp     loc_180004CEF
0x180004f21  mov     rax, r15
0x180004f24  lea     r8, aCacheControlMa; "Cache-Control: max-age = "
0x180004f2b  sub     rax, rdx
0x180004f2e  mov     rcx, r13
0x180004f31  lea     rdx, [r12+rdx*2]
0x180004f35  jz      short loc_180004F5B
0x180004f37  test    rcx, rcx
0x180004f3a  jz      short loc_180004F5B
0x180004f3c  movzx   r9d, word ptr [r8]
0x180004f40  test    r9w, r9w
0x180004f44  jz      short loc_180004F5B
0x180004f46  mov     [rdx], r9w
0x180004f4a  add     r8, 2
0x180004f4e  add     rdx, 2
0x180004f52  dec     rcx
0x180004f55  sub     rax, 1
0x180004f59  jnz     short loc_180004F37
0x180004f5b  test    rax, rax
0x180004f5e  lea     rcx, [rdx-2]
0x180004f62  cmovnz  rcx, rdx
0x180004f66  xor     eax, eax
0x180004f68  mov     [rcx], ax
0x180004f6b  mov     rcx, r15
0x180004f6e  jmp     loc_180004E44
0x180004f73  sub     r15, rax
0x180004f76  lea     rcx, [rsp+188h+Buffer]
0x180004f7b  lea     rax, [r12+rax*2]
0x180004f7f  jz      short loc_180004FA2
0x180004f81  test    r13, r13
0x180004f84  jz      short loc_180004FA2
0x180004f86  movzx   edx, word ptr [rcx]
0x180004f89  test    dx, dx
0x180004f8c  jz      short loc_180004FA2
0x180004f8e  mov     [rax], dx
0x180004f91  add     rcx, 2
0x180004f95  add     rax, 2
0x180004f99  dec     r13
0x180004f9c  sub     r15, 1
0x180004fa0  jnz     short loc_180004F81
  ... truncated ...
```
