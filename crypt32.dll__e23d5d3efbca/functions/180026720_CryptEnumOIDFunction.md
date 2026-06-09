# CryptEnumOIDFunction

- ea: `0x180026720`
- end: `0x180026d43`
- name: `CryptEnumOIDFunction`
- size: `1571`
- prototype: `BOOL __stdcall(DWORD dwEncodingType, LPCSTR pszFuncName, LPCSTR pszOID, DWORD dwFlags, void *pvArg, PFN_CRYPT_ENUM_OID_FUNC pfnEnumOIDFunc)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008720`
- `0x180009da0`
- `0x180025000`
- `0x180026220`
- `0x180029494`
- `0x18007d748`
- `0x1800ad7c0`
- `0x1800b4e60`

## callees

- `0x180025fb4`
- `0x180026720`
- `0x180028d60`
- `0x180031884`
- `0x1800bec20`
- `0x1800bf4ea`
- `0x1800bf564`
- `0x1800bf63c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d38`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800268f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180026c75`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180026cc9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800268f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180026c75`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180026cc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800267bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002688e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180026a61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180026b2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800267bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002688e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180026a61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180026b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800268c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800268c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c86`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002696a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002696a`

## pseudocode

```c
BOOL __stdcall CryptEnumOIDFunction(
        DWORD dwEncodingType,
        LPCSTR pszFuncName,
        LPCSTR pszOID,
        DWORD dwFlags,
        void *pvArg,
        PFN_CRYPT_ENUM_OID_FUNC pfnEnumOIDFunc)
{
  DWORD v6; // eax
  DWORD v7; // r14d
  LPCSTR v9; // rsi
  char *v10; // r12
  LPCSTR v11; // r15
  DWORD v12; // ebx
  HKEY v13; // rdi
  __int64 v14; // rax
  CHAR *v15; // r8
  __int64 v16; // rax
  CHAR *v17; // rcx
  __int64 v18; // rdx
  CHAR *v19; // rax
  HKEY v20; // rdi
  __int64 v21; // rax
  char *v22; // rax
  DWORD v23; // r13d
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  CHAR *v28; // r8
  _BYTE *v29; // rcx
  CHAR *v30; // rax
  HKEY v31; // rsi
  DWORD v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rax
  CHAR *v35; // r8
  _BYTE *v36; // rdx
  CHAR *v37; // rax
  HKEY v38; // r15
  __int64 v39; // rax
  DWORD v40; // edx
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v43; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v44; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v45; // [rsp+5Ch] [rbp-A4h] BYREF
  LPCSTR v46; // [rsp+60h] [rbp-A0h]
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v48; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  HKEY v51; // [rsp+88h] [rbp-78h] BYREF
  HKEY v52; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v53; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 **v54; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 **v55; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int *v56; // [rsp+B0h] [rbp-50h] BYREF
  LPCSTR v57; // [rsp+B8h] [rbp-48h]
  void *v58; // [rsp+C0h] [rbp-40h]
  PFN_CRYPT_ENUM_OID_FUNC v59; // [rsp+C8h] [rbp-38h]
  char v60; // [rsp+D0h] [rbp-30h] BYREF
  char Buffer[47]; // [rsp+D1h] [rbp-2Fh] BYREF
  CHAR SubKey[13]; // [rsp+100h] [rbp+0h] BYREF
  char String[115]; // [rsp+10Dh] [rbp+Dh] BYREF
  CHAR Name[128]; // [rsp+180h] [rbp+80h] BYREF
  CHAR v65[128]; // [rsp+200h] [rbp+100h] BYREF

  v6 = dwEncodingType;
  v57 = pszFuncName;
  v7 = 0;
  v58 = pvArg;
  v9 = pszFuncName;
  v59 = pfnEnumOIDFunc;
  v10 = 0;
  hKey = 0;
  if ( dwEncodingType != -1 )
  {
    dwEncodingType = (unsigned __int16)dwEncodingType;
    v32 = HIWORD(v6);
    if ( !(_WORD)dwEncodingType )
      dwEncodingType = v32;
    v22 = EncodingTypeToRegName(dwEncodingType);
    v10 = v22;
    if ( !v22 )
      return (int)v22;
  }
  hMem = (HLOCAL)pszOID;
  v11 = pszOID;
  v46 = pszOID;
  if ( pszOID )
  {
    hMem = (HLOCAL)pszOID;
    v46 = pszOID;
    if ( (unsigned __int64)pszOID <= 0xFFFF )
    {
      v60 = 35;
      ltoa((int)pszOID, Buffer, 10);
      v11 = &v60;
      v46 = &v60;
    }
  }
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Cryptography\\OID", 0, 0x20019u, &hKey) )
    goto LABEL_26;
  v12 = 0;
  memset_0(SubKey, 0, 0x80u);
  while ( 1 )
  {
    v13 = hKey;
    phkResult = 0;
    cchName = 0;
    if ( !v10 || !*v10 )
    {
      cchName = 128;
      if ( RegEnumKeyExA(hKey, v12, SubKey, &cchName, 0, 0, 0, 0) )
        goto LABEL_25;
      ++v12;
      goto LABEL_18;
    }
    if ( v12 )
      goto LABEL_25;
    v14 = -1;
    do
      ++v14;
    while ( v10[v14] );
    if ( (int)v14 >= 128 )
      goto LABEL_25;
    v12 = 1;
    v15 = SubKey;
    v16 = 2147483646;
    v17 = v10;
    v18 = 128;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v15++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v19 = v15 - 1;
    if ( v18 )
      v19 = v15;
    *v19 = 0;
    if ( !v18 )
      break;
LABEL_18:
    if ( RegOpenKeyExA(v13, SubKey, 0, 0x20019u, &phkResult) )
      goto LABEL_25;
    v20 = phkResult;
    if ( !phkResult )
      goto LABEL_25;
    v21 = -1;
    do
      ++v21;
    while ( SubKey[v21] );
    if ( (unsigned int)v21 >= 0xD && CompareStringA(0x409u, 1u, SubKey, 13, "EncodingType ", 13) == 2 )
    {
      v48 = o_atol_0(String);
      if ( v48 < 0x10000 )
      {
        v23 = 0;
        memset_0(v65, 0, sizeof(v65));
        while ( 1 )
        {
          v51 = 0;
          v43 = 0;
          if ( v9 && *v9 )
          {
            if ( v23++ )
              goto LABEL_78;
            v25 = -1;
            do
              ++v25;
            while ( v9[v25] );
            v26 = 128;
            if ( (int)v25 >= 128 )
              goto LABEL_78;
            v27 = 2147483646;
            v28 = v65;
            v29 = v9;
            do
            {
              if ( !v27 )
                break;
              if ( !*v29 )
                break;
              *v28++ = *v29++;
              --v27;
              --v26;
            }
            while ( v26 );
            v30 = v28 - 1;
            if ( v26 )
              v30 = v28;
            *v30 = 0;
            if ( !v26 )
            {
              SetLastError(0x8007007A);
LABEL_78:
              v31 = 0;
              goto LABEL_47;
            }
          }
          else
          {
            v40 = v23;
            v43 = 128;
            ++v23;
            if ( RegEnumKeyExA(v20, v40, v65, &v43, 0, 0, 0, 0) )
              goto LABEL_78;
          }
          v31 = 0;
          if ( !RegOpenKeyExA(v20, v65, 0, 0x20019u, &v51) )
            v31 = v51;
LABEL_47:
          if ( !v31 )
          {
            v9 = v57;
            break;
          }
          memset_0(Name, 0, sizeof(Name));
          while ( 1 )
          {
            v52 = 0;
            v44 = 0;
            if ( v11 && *v11 )
            {
              if ( v7 )
                goto LABEL_76;
              v39 = -1;
              do
                ++v39;
              while ( v11[v39] );
              v33 = 128;
              if ( (int)v39 >= 128 )
                goto LABEL_76;
              v34 = 2147483646;
              v35 = Name;
              v36 = v11;
              do
              {
                if ( !v34 )
                  break;
                if ( !*v36 )
                  break;
                *v35++ = *v36++;
                --v34;
                --v33;
              }
              while ( v33 );
              v37 = v35 - 1;
              if ( v33 )
                v37 = v35;
              *v37 = 0;
              if ( !v33 )
              {
                SetLastError(0x8007007A);
                goto LABEL_76;
              }
            }
            else
            {
              v44 = 128;
              if ( RegEnumKeyExA(v31, v7, Name, &v44, 0, 0, 0, 0) )
                goto LABEL_76;
            }
            ++v7;
            if ( RegOpenKeyExA(v31, Name, 0, 0x20019u, &v52) )
              goto LABEL_76;
            v38 = v52;
            if ( !v52 )
              break;
            hMem = 0;
            v45 = 0;
            v56 = 0;
            v55 = 0;
            v54 = 0;
            v53 = 0;
            if ( (unsigned int)GetRegValues(v52, &hMem, &v45, &v56, &v55, &v54, &v53) )
            {
              ((void (__fastcall *)(_QWORD, CHAR *, CHAR *, _QWORD, unsigned int *, unsigned __int16 **, unsigned __int8 **, unsigned int *, void *))v59)(
                v48,
                v65,
                Name,
                v45,
                v56,
                v55,
                v54,
                v53,
                v58);
              if ( hMem )
                PkiDefaultCryptFree(hMem);
            }
            RegCloseKey(v38);
            v11 = v46;
          }
          v11 = v46;
LABEL_76:
          RegCloseKey(v31);
          v9 = v57;
          v7 = 0;
        }
      }
    }
    RegCloseKey(v20);
  }
  SetLastError(0x8007007A);
LABEL_25:
  RegCloseKey(hKey);
LABEL_26:
  if ( v10 )
    PkiDefaultCryptFree(v10);
  LODWORD(v22) = 1;
  return (int)v22;
}

```

## disassembly

```asm
0x180026720  mov     [rsp-8+arg_8], rbx
0x180026725  push    rbp
0x180026726  push    rsi
0x180026727  push    rdi
0x180026728  push    r12
0x18002672a  push    r13
0x18002672c  push    r14
0x18002672e  push    r15
0x180026730  lea     rbp, [rsp-190h]
0x180026738  sub     rsp, 290h
0x18002673f  mov     rax, cs:__security_cookie
0x180026746  xor     rax, rsp
0x180026749  mov     [rbp+1C0h+var_40], rax
0x180026750  mov     eax, ecx
0x180026752  mov     [rbp+1C0h+var_208], rdx
0x180026756  mov     rcx, [rbp+1C0h+pvArg]
0x18002675d  xor     r14d, r14d
0x180026760  mov     [rbp+1C0h+var_200], rcx
0x180026764  mov     rbx, r8
0x180026767  mov     rcx, [rbp+1C0h+pfnEnumOIDFunc]
0x18002676e  mov     rsi, rdx
0x180026771  mov     [rbp+1C0h+var_1F8], rcx
0x180026775  mov     r12d, r14d
0x180026778  mov     [rsp+2C0h+hKey], r14
0x18002677d  cmp     eax, 0FFFFFFFFh
0x180026780  jnz     loc_180026A89
0x180026786  mov     [rsp+2C0h+hMem], rbx
0x18002678b  mov     r15, rbx
0x18002678e  mov     [rsp+2C0h+var_260], rbx
0x180026793  test    rbx, rbx
0x180026796  jnz     loc_180026CDF
0x18002679c  lea     rax, [rsp+2C0h+hKey]
0x1800267a1  mov     r9d, 20019h; samDesired
0x1800267a7  xor     r8d, r8d; ulOptions
0x1800267aa  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800267af  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Cryptography\\OID"
0x1800267b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800267bd  call    cs:__imp_RegOpenKeyExA
0x1800267c3  test    eax, eax
0x1800267c5  jnz     loc_18002690D
0x1800267cb  mov     r13d, 80h
0x1800267d1  lea     rcx, [rbp+1C0h+SubKey]; void *
0x1800267d5  mov     r8d, r13d; Size
0x1800267d8  xor     edx, edx; Val
0x1800267da  mov     ebx, r14d
0x1800267dd  call    memset_0
0x1800267e2  mov     rdi, [rsp+2C0h+hKey]
0x1800267e7  mov     [rbp+1C0h+var_240], r14
0x1800267eb  mov     [rsp+2C0h+cchName], r14d
0x1800267f0  test    r12, r12
0x1800267f3  jz      loc_1800268CD
0x1800267f9  cmp     [r12], r14b
0x1800267fd  jz      loc_1800268CD
0x180026803  test    ebx, ebx
0x180026805  jnz     loc_180026902
0x18002680b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002680f  inc     rax
0x180026812  cmp     [r12+rax], r14b
0x180026816  jnz     short loc_18002680F
0x180026818  cmp     eax, r13d
0x18002681b  jge     loc_180026902
0x180026821  inc     ebx
0x180026823  lea     r8, [rbp+1C0h+SubKey]
0x180026827  mov     eax, 7FFFFFFEh
0x18002682c  mov     rcx, r12
0x18002682f  mov     rdx, r13
0x180026832  test    rax, rax
0x180026835  jz      short loc_180026851
0x180026837  mov     r9b, [rcx]
0x18002683a  test    r9b, r9b
0x18002683d  jz      short loc_180026851
0x18002683f  mov     [r8], r9b
0x180026842  inc     rcx
0x180026845  inc     r8
0x180026848  dec     rax
0x18002684b  sub     rdx, 1
0x18002684f  jnz     short loc_180026832
0x180026851  mov     rax, rdx
0x180026854  neg     rax
0x180026857  lea     rax, [r8-1]
0x18002685b  sbb     ecx, ecx
0x18002685d  not     ecx
0x18002685f  and     ecx, 8007007Ah; dwErrCode
0x180026865  test    rdx, rdx
0x180026868  cmovnz  rax, r8
0x18002686c  mov     [rax], r14b
0x18002686f  jz      loc_180026D38
0x180026875  lea     rax, [rbp+1C0h+var_240]
0x180026879  mov     r9d, 20019h; samDesired
0x18002687f  xor     r8d, r8d; ulOptions
0x180026882  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180026887  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x18002688b  mov     rcx, rdi; hKey
0x18002688e  call    cs:__imp_RegOpenKeyExA
0x180026894  test    eax, eax
0x180026896  jnz     short loc_180026902
0x180026898  mov     rdi, [rbp+1C0h+var_240]
0x18002689c  test    rdi, rdi
0x18002689f  jz      short loc_180026902
0x1800268a1  lea     rcx, [rbp+1C0h+SubKey]
0x1800268a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800268a9  inc     rax
0x1800268ac  cmp     [rcx+rax], r14b
0x1800268b0  jnz     short loc_1800268A9
0x1800268b2  mov     ecx, 0Dh
0x1800268b7  cmp     eax, ecx
0x1800268b9  jnb     loc_180026949
0x1800268bf  mov     rcx, rdi; hKey
0x1800268c2  call    cs:__imp_RegCloseKey
0x1800268c8  jmp     loc_1800267E2
0x1800268cd  mov     [rsp+2C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800268d2  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x1800268d7  mov     [rsp+2C0h+lpcchClass], r14; lpcchClass
0x1800268dc  lea     r8, [rbp+1C0h+SubKey]; lpName
0x1800268e0  mov     [rsp+2C0h+lpClass], r14; lpClass
0x1800268e5  mov     edx, ebx; dwIndex
0x1800268e7  mov     rcx, rdi; hKey
0x1800268ea  mov     [rsp+2C0h+phkResult], r14; lpReserved
0x1800268ef  mov     [rsp+2C0h+cchName], r13d
0x1800268f4  call    cs:__imp_RegEnumKeyExA
0x1800268fa  test    eax, eax
0x1800268fc  jz      loc_180026AAA
0x180026902  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180026907  call    cs:__imp_RegCloseKey
0x18002690d  test    r12, r12
0x180026910  jz      short loc_18002691A
0x180026912  mov     rcx, r12; hMem
0x180026915  call    PkiDefaultCryptFree
0x18002691a  mov     eax, 1
0x18002691f  mov     rcx, [rbp+1C0h+var_40]
0x180026926  xor     rcx, rsp; StackCookie
0x180026929  call    __security_check_cookie
0x18002692e  mov     rbx, [rsp+2C0h+arg_8]
0x180026936  add     rsp, 290h
0x18002693d  pop     r15
0x18002693f  pop     r14
0x180026941  pop     r13
0x180026943  pop     r12
0x180026945  pop     rdi
0x180026946  pop     rsi
0x180026947  pop     rbp
0x180026948  retn
0x180026949  mov     dword ptr [rsp+2C0h+lpClass], ecx; cchCount2
0x18002694d  lea     rax, aEncodingtype; "EncodingType "
0x180026954  mov     r9d, ecx; cchCount1
0x180026957  mov     [rsp+2C0h+phkResult], rax; lpString2
0x18002695c  mov     ecx, 409h; Locale
0x180026961  lea     r8, [rbp+1C0h+SubKey]; lpString1
0x180026965  mov     edx, 1; dwCmpFlags
0x18002696a  call    cs:__imp_CompareStringA
0x180026970  cmp     eax, 2
0x180026973  jnz     loc_1800268BF
0x180026979  lea     rcx, [rbp+1C0h+String]; String
0x18002697d  call    _o_atol_0
0x180026982  mov     [rsp+2C0h+var_250], eax
0x180026986  test    eax, eax
0x180026988  js      loc_1800268BF
0x18002698e  cmp     eax, 0FFFFh
0x180026993  jg      loc_1800268BF
0x180026999  xor     edx, edx; Val
0x18002699b  lea     rcx, [rbp+1C0h+var_C0]; void *
0x1800269a2  mov     r8d, 80h; Size
0x1800269a8  mov     r13d, r14d
0x1800269ab  call    memset_0
0x1800269b0  mov     [rbp+1C0h+var_238], r14
0x1800269b4  mov     [rsp+2C0h+var_26C], r14d
0x1800269b9  test    rsi, rsi
0x1800269bc  jz      loc_180026C98
0x1800269c2  cmp     [rsi], r14b
0x1800269c5  jz      loc_180026C98
0x1800269cb  mov     eax, r13d
0x1800269ce  inc     r13d
0x1800269d1  test    eax, eax
0x1800269d3  jnz     loc_180026CD7
0x1800269d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800269dd  inc     rax
0x1800269e0  cmp     [rsi+rax], r14b
0x1800269e4  jnz     short loc_1800269DD
0x1800269e6  mov     edx, 80h
0x1800269eb  cmp     eax, edx
0x1800269ed  jge     loc_180026CD7
0x1800269f3  mov     eax, 7FFFFFFEh
0x1800269f8  lea     r8, [rbp+1C0h+var_C0]
0x1800269ff  mov     rcx, rsi
0x180026a02  test    rax, rax
0x180026a05  jz      short loc_180026A21
0x180026a07  mov     r9b, [rcx]
0x180026a0a  test    r9b, r9b
0x180026a0d  jz      short loc_180026A21
0x180026a0f  mov     [r8], r9b
0x180026a12  inc     rcx
0x180026a15  inc     r8
0x180026a18  dec     rax
0x180026a1b  sub     rdx, 1
0x180026a1f  jnz     short loc_180026A02
0x180026a21  mov     rax, rdx
0x180026a24  neg     rax
0x180026a27  lea     rax, [r8-1]
0x180026a2b  sbb     ecx, ecx
0x180026a2d  not     ecx
0x180026a2f  and     ecx, 8007007Ah; dwErrCode
0x180026a35  test    rdx, rdx
0x180026a38  cmovnz  rax, r8
0x180026a3c  mov     [rax], r14b
0x180026a3f  jz      loc_180026D19
0x180026a45  lea     rax, [rbp+1C0h+var_238]
0x180026a49  mov     r9d, 20019h; samDesired
0x180026a4f  xor     r8d, r8d; ulOptions
0x180026a52  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180026a57  lea     rdx, [rbp+1C0h+var_C0]; lpSubKey
0x180026a5e  mov     rcx, rdi; hKey
0x180026a61  call    cs:__imp_RegOpenKeyExA
0x180026a67  test    eax, eax
0x180026a69  mov     rsi, r14
0x180026a6c  cmovz   rsi, [rbp+1C0h+var_238]
0x180026a71  test    rsi, rsi
0x180026a74  jnz     loc_180026C06
0x180026a7a  mov     rsi, [rbp+1C0h+var_208]
0x180026a7e  mov     r13d, 80h
0x180026a84  jmp     loc_1800268BF
0x180026a89  movzx   ecx, ax
0x180026a8c  shr     eax, 10h
0x180026a8f  test    ecx, ecx
0x180026a91  cmovz   ecx, eax; unsigned int
0x180026a94  call    ?EncodingTypeToRegName@@YAPEADK@Z; EncodingTypeToRegName(ulong)
0x180026a99  mov     r12, rax
0x180026a9c  test    rax, rax
0x180026a9f  jnz     loc_180026786
0x180026aa5  jmp     loc_18002691F
0x180026aaa  inc     ebx
0x180026aac  jmp     loc_180026875
0x180026ab1  mov     ecx, 80h
0x180026ab6  cmp     eax, ecx
0x180026ab8  jge     loc_180026C83
0x180026abe  mov     eax, 7FFFFFFEh
0x180026ac3  lea     r8, [rbp+1C0h+Name]
0x180026aca  mov     rdx, r15
0x180026acd  test    rax, rax
0x180026ad0  jz      short loc_180026AEC
0x180026ad2  mov     r9b, [rdx]
0x180026ad5  test    r9b, r9b
0x180026ad8  jz      short loc_180026AEC
0x180026ada  mov     [r8], r9b
0x180026add  inc     rdx
0x180026ae0  inc     r8
0x180026ae3  dec     rax
0x180026ae6  sub     rcx, 1
0x180026aea  jnz     short loc_180026ACD
0x180026aec  mov     rax, rcx
0x180026aef  neg     rax
0x180026af2  lea     rax, [r8-1]
0x180026af6  sbb     edx, edx
0x180026af8  not     edx
0x180026afa  and     edx, 8007007Ah
0x180026b00  test    rcx, rcx
0x180026b03  cmovnz  rax, r8
0x180026b07  mov     [rax], r10b
0x180026b0a  jz      loc_180026D21
0x180026b10  lea     rax, [rbp+1C0h+var_230]
0x180026b14  mov     r9d, 20019h; samDesired
0x180026b1a  xor     r8d, r8d; ulOptions
0x180026b1d  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180026b22  lea     rdx, [rbp+1C0h+Name]; lpSubKey
0x180026b29  mov     rcx, rsi; hKey
0x180026b2c  inc     r14d
0x180026b2f  call    cs:__imp_RegOpenKeyExA
0x180026b35  xor     ecx, ecx
0x180026b37  test    eax, eax
0x180026b39  jnz     loc_180026C83
0x180026b3f  mov     r15, [rbp+1C0h+var_230]
0x180026b43  test    r15, r15
0x180026b46  jz      loc_180026D2E
0x180026b4c  lea     rax, [rbp+1C0h+var_228]
0x180026b50  mov     [rsp+2C0h+hMem], rcx
0x180026b55  mov     [rsp+2C0h+lpcchClass], rax; unsigned int **
0x180026b5a  lea     r9, [rbp+1C0h+var_210]; unsigned int **
0x180026b5e  lea     rax, [rbp+1C0h+var_220]
0x180026b62  mov     [rsp+2C0h+var_264], ecx
0x180026b66  mov     [rsp+2C0h+lpClass], rax; unsigned __int8 ***
0x180026b6b  lea     r8, [rsp+2C0h+var_264]; unsigned int *
0x180026b70  lea     rax, [rbp+1C0h+var_218]
0x180026b74  mov     [rbp+1C0h+var_210], rcx
0x180026b78  mov     [rbp+1C0h+var_218], rcx
0x180026b7c  lea     rdx, [rsp+2C0h+hMem]; void **
0x180026b81  mov     [rbp+1C0h+var_220], rcx
0x180026b85  mov     [rbp+1C0h+var_228], rcx
0x180026b89  mov     rcx, r15; hKey
0x180026b8c  mov     [rsp+2C0h+phkResult], rax; unsigned __int16 ***
0x180026b91  call    ?GetRegValues@@YAHPEAUHKEY__@@PEAPEAXPEAKPEAPEAKPEAPEAPEAGPEAPEAPEAE3@Z; GetRegValues(HKEY__ *,void * *,ulong *,ulong * *,ushort * * *,uchar * * *,ulong * *)
0x180026b96  test    eax, eax
0x180026b98  jz      short loc_180026BF6
0x180026b9a  mov     rax, [rbp+1C0h+var_200]
0x180026b9e  lea     r8, [rbp+1C0h+Name]
0x180026ba5  mov     r9d, [rsp+2C0h+var_264]
0x180026baa  lea     rdx, [rbp+1C0h+var_C0]
0x180026bb1  mov     ecx, [rsp+2C0h+var_250]
0x180026bb5  mov     [rsp+2C0h+var_280], rax
0x180026bba  mov     rax, [rbp+1C0h+var_228]
0x180026bbe  mov     [rsp+2C0h+lpftLastWriteTime], rax
0x180026bc3  mov     rax, [rbp+1C0h+var_220]
  ... truncated ...
```
