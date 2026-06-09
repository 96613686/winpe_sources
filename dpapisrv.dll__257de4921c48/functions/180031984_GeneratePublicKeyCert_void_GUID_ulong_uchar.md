# GeneratePublicKeyCert(void *,_GUID *,ulong *,uchar * *)

- ea: `0x180031984`
- end: `0x18003207c`
- name: `?GeneratePublicKeyCert@@YAHPEAXPEAU_GUID@@PEAKPEAPEAE@Z`
- size: `1784`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey, struct _GUID *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800310e0`
- `0x1800313c8`

## callees

- `0x180007f10`
- `0x18001e1b4`
- `0x180031984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031a72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031bdc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031a72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031bdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031fd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032012`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032026`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003203c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032051`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031fd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032012`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032026`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003203c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032051`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031a90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031b5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031d09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031db6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031f34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031a90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031b5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031d09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031db6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031f34`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180031a2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180031ad5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180031a2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180031ad5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031e62`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031e62`
- `bcrypt!BCryptExportKey` at `0x180031b32`
- `bcrypt!BCryptExportKey` at `0x180031baa`
- `bcrypt!BCryptExportKey` at `0x180031b32`
- `bcrypt!BCryptExportKey` at `0x180031baa`
- `ncrypt!NCryptOpenStorageProvider` at `0x180031bfc`
- `ncrypt!NCryptOpenStorageProvider` at `0x180031bfc`
- `ncrypt!NCryptFinalizeKey` at `0x180031c8f`
- `ncrypt!NCryptFinalizeKey` at `0x180031c8f`
- `ncrypt!NCryptCreatePersistedKey` at `0x180031c3b`
- `ncrypt!NCryptCreatePersistedKey` at `0x180031c3b`
- `ncrypt!NCryptSetProperty` at `0x180031c6e`
- `ncrypt!NCryptSetProperty` at `0x180031c6e`
- `ncrypt!NCryptFreeObject` at `0x180031fe8`
- `ncrypt!NCryptFreeObject` at `0x180031ffe`
- `ncrypt!NCryptFreeObject` at `0x180031fe8`
- `ncrypt!NCryptFreeObject` at `0x180031ffe`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180031cc7`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180031d48`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180031cc7`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180031d48`
- `CRYPT32!CryptEncodeObject` at `0x180031d89`
- `CRYPT32!CryptEncodeObject` at `0x180031df9`
- `CRYPT32!CryptEncodeObject` at `0x180031d89`
- `CRYPT32!CryptEncodeObject` at `0x180031df9`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x180031f07`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x180031f92`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x180031f07`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x180031f92`

## string_xrefs

- `0x180031a62`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180031aab`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180031b00`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180031bcc`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180031ceb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall GeneratePublicKeyCert(
        BCRYPT_KEY_HANDLE hKey,
        struct _GUID *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  unsigned int v6; // r12d
  struct _CERT_PUBLIC_KEY_INFO *v7; // rsi
  unsigned __int8 *v8; // rdi
  DWORD LastError; // eax
  NTSTATUS v10; // ebx
  __int64 v11; // r9
  const char *v12; // rdx
  DWORD v13; // ecx
  HLOCAL v14; // rax
  DWORD v15; // eax
  __int64 v16; // r9
  const char *v17; // rdx
  __int64 v18; // rcx
  UCHAR *v19; // r14
  NTSTATUS v20; // ebx
  __int64 v21; // r9
  const char *v22; // rdx
  DWORD v23; // eax
  __int64 v24; // r9
  HLOCAL v25; // rax
  __int128 v26; // xmm0
  BYTE *pbEncoded; // rax
  unsigned int v28; // eax
  ULONG cbInput[2]; // [rsp+58h] [rbp-B0h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-A8h] BYREF
  DWORD nSize[2]; // [rsp+68h] [rbp-A0h] BYREF
  DWORD pcbEncoded[2]; // [rsp+70h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-90h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+80h] [rbp-88h] BYREF
  _QWORD pvStructInfo[2]; // [rsp+88h] [rbp-80h] BYREF
  const char *v37; // [rsp+98h] [rbp-70h] BYREF
  int v38; // [rsp+A0h] [rbp-68h]
  DWORD v39; // [rsp+A8h] [rbp-60h]
  HLOCAL v40; // [rsp+B0h] [rbp-58h]
  int v41; // [rsp+B8h] [rbp-50h] BYREF
  const char **v42; // [rsp+C0h] [rbp-48h]
  _DWORD v43[4]; // [rsp+C8h] [rbp-40h] BYREF
  struct _GUID *v44; // [rsp+D8h] [rbp-30h]
  _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+E0h] [rbp-28h] BYREF
  DWORD v46; // [rsp+F8h] [rbp-10h]
  HLOCAL v47; // [rsp+100h] [rbp-8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+108h] [rbp+0h] BYREF
  __int64 v49; // [rsp+110h] [rbp+8h]
  DWORD v50; // [rsp+118h] [rbp+10h]
  HLOCAL v51; // [rsp+120h] [rbp+18h]
  __int128 v52; // [rsp+128h] [rbp+20h]
  __int128 v53; // [rsp+138h] [rbp+30h]
  __int128 v54; // [rsp+148h] [rbp+40h]
  int v55; // [rsp+158h] [rbp+50h]
  struct _GUID *v56; // [rsp+160h] [rbp+58h]
  int v57; // [rsp+168h] [rbp+60h]
  int v58; // [rsp+170h] [rbp+68h]
  struct _GUID *v59; // [rsp+178h] [rbp+70h]
  int v60; // [rsp+180h] [rbp+78h]
  int v61; // [rsp+188h] [rbp+80h]
  __int64 v62; // [rsp+190h] [rbp+88h]

  v6 = 0;
  memset_0(v43, 0, 0xD0u);
  v7 = 0;
  v38 = 4;
  nSize[1] = 0;
  v42 = &v37;
  *(_QWORD *)pcbEncoded = 0;
  pvStructInfo[1] = &v41;
  v41 = 1;
  v37 = "2.5.4.3";
  pvStructInfo[0] = 1;
  phKey = 0;
  v8 = 0;
  phProvider = 0;
  cbInput[0] = 0;
  hMem = 0;
  v40 = 0;
  v39 = 0;
  cbInput[1] = 0;
  nSize[0] = 0;
  if ( !GetComputerNameExW(ComputerNameDnsDomain, 0, nSize) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError != 234 && LastError != 111 )
    {
      v11 = 2976;
      v12 = "dwError";
LABEL_5:
      DebugTraceError((unsigned int)v10, v12, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v11);
      v13 = v10;
LABEL_6:
      SetLastError(v13);
      goto LABEL_49;
    }
  }
  v39 = 2 * nSize[0];
  v14 = LocalAlloc(0, 2 * nSize[0]);
  v40 = v14;
  if ( !v14 )
  {
    DebugTraceError(
      8,
      "ERROR_NOT_ENOUGH_MEMORY",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      2986);
    v13 = 8;
    goto LABEL_6;
  }
  if ( !GetComputerNameExW(ComputerNameDnsDomain, (LPWSTR)v14, nSize) )
  {
    v15 = GetLastError();
    v16 = 2995;
    v17 = "GetLastError()";
    v18 = v15;
LABEL_11:
    DebugTraceError(v18, v17, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v16);
    goto LABEL_49;
  }
  v10 = BCryptExportKey(hKey, 0, L"CAPIPRIVATEBLOB", 0, 0, cbInput, 0);
  if ( v10 < 0 )
  {
    v11 = 3008;
    v12 = "ntStatus";
    goto LABEL_5;
  }
  v19 = (UCHAR *)LocalAlloc(0, cbInput[0]);
  if ( !v19 )
  {
    v16 = 3016;
    v17 = "ERROR_NOT_ENOUGH_MEMORY";
    v18 = 8;
    goto LABEL_11;
  }
  v20 = BCryptExportKey(hKey, 0, L"CAPIPRIVATEBLOB", v19, cbInput[0], cbInput, 0);
  if ( v20 < 0 )
  {
    v21 = 3029;
    v22 = "ntStatus";
LABEL_18:
    DebugTraceError((unsigned int)v20, v22, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v21);
    SetLastError(v20);
    goto LABEL_48;
  }
  v20 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  if ( v20 )
  {
    v21 = 3042;
LABEL_21:
    v22 = "Status";
    goto LABEL_18;
  }
  v20 = NCryptCreatePersistedKey(phProvider, &phKey, L"RSA", 0, 0, 0);
  if ( v20 )
  {
    v21 = 3055;
    goto LABEL_21;
  }
  v20 = NCryptSetProperty(phKey, L"CAPIPRIVATEBLOB", v19, cbInput[0], 0);
  if ( v20 )
  {
    v21 = 3067;
    goto LABEL_21;
  }
  v20 = NCryptFinalizeKey(phKey, 0);
  if ( v20 )
  {
    v21 = 3077;
    goto LABEL_21;
  }
  if ( CryptExportPublicKeyInfo(phKey, 1u, 1u, 0, &nSize[1]) )
  {
    v7 = (struct _CERT_PUBLIC_KEY_INFO *)LocalAlloc(0, nSize[1]);
    if ( v7 )
    {
      if ( CryptExportPublicKeyInfo(phKey, 1u, 1u, v7, &nSize[1]) )
      {
        if ( CryptEncodeObject(1u, (LPCSTR)7, pvStructInfo, 0, pcbEncoded) )
        {
          v25 = LocalAlloc(0, pcbEncoded[0]);
          hMem = v25;
          if ( v25 )
          {
            if ( CryptEncodeObject(1u, (LPCSTR)7, pvStructInfo, (BYTE *)v25, pcbEncoded) )
            {
              pSignatureAlgorithm.pszObjId = "1.3.14.3.2.29";
              v47 = hMem;
              v46 = pcbEncoded[0];
              v43[0] = 2;
              v44 = a2;
              v43[2] = 16;
              pSignatureAlgorithm.Parameters.cbData = 0;
              pSignatureAlgorithm.Parameters.pbData = 0;
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              v51 = hMem;
              v50 = pcbEncoded[0];
              v49 = *(_QWORD *)&SystemTimeAsFileTime + 315360000000000LL;
              v52 = *(_OWORD *)&v7->Algorithm.pszObjId;
              v53 = *(_OWORD *)&v7->Algorithm.Parameters.pbData;
              v26 = *(_OWORD *)&v7->PublicKey.pbData;
              v58 = 16;
              v55 = 16;
              v59 = a2;
              v56 = a2;
              v54 = v26;
              v60 = 0;
              v57 = 0;
              v61 = 0;
              v62 = 0;
              if ( CryptSignAndEncodeCertificate(phKey, 1u, 1u, (LPCSTR)2, v43, &pSignatureAlgorithm, 0, 0, &cbInput[1]) )
              {
                pbEncoded = (BYTE *)LocalAlloc(0, cbInput[1]);
                v8 = pbEncoded;
                if ( pbEncoded )
                {
                  if ( CryptSignAndEncodeCertificate(
                         phKey,
                         1u,
                         1u,
                         (LPCSTR)2,
                         v43,
                         &pSignatureAlgorithm,
                         0,
                         pbEncoded,
                         &cbInput[1]) )
                  {
                    v6 = 1;
                    v28 = cbInput[1];
                    *a4 = v8;
                    v8 = 0;
                    *a3 = v28;
                    goto LABEL_48;
                  }
                  v23 = GetLastError();
                  v24 = 3201;
                }
                else
                {
                  v23 = GetLastError();
                  v24 = 3187;
                }
              }
              else
              {
                v23 = GetLastError();
                v24 = 3180;
              }
            }
            else
            {
              v23 = GetLastError();
              v24 = 3136;
            }
          }
          else
          {
            v23 = GetLastError();
            v24 = 3127;
          }
        }
        else
        {
          v23 = GetLastError();
          v24 = 3120;
        }
      }
      else
      {
        v23 = GetLastError();
        v24 = 3106;
      }
    }
    else
    {
      v23 = GetLastError();
      v24 = 3097;
    }
  }
  else
  {
    v23 = GetLastError();
    v24 = 3091;
  }
  DebugTraceError(v23, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v24);
LABEL_48:
  LocalFree(v19);
LABEL_49:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( v8 )
    LocalFree(v8);
  if ( v7 )
    LocalFree(v7);
  if ( hMem )
    LocalFree(hMem);
  if ( v40 )
    LocalFree(v40);
  return v6;
}

```

## disassembly

```asm
0x180031984  mov     rax, rsp
0x180031987  mov     [rax+8], rbx
0x18003198b  mov     [rax+18h], r8
0x18003198f  mov     [rax+10h], rdx
0x180031993  push    rbp
0x180031994  push    rsi
0x180031995  push    rdi
0x180031996  push    r12
0x180031998  push    r13
0x18003199a  push    r14
0x18003199c  push    r15
0x18003199e  lea     rbp, [rax-0C8h]
0x1800319a5  sub     rsp, 190h
0x1800319ac  mov     r15, rcx
0x1800319af  xor     edx, edx; Val
0x1800319b1  lea     rcx, [rbp+0C0h+var_100]; void *
0x1800319b5  mov     r8d, 0D0h; Size
0x1800319bb  mov     r13, r9
0x1800319be  xor     r12d, r12d
0x1800319c1  call    memset_0
0x1800319c6  xor     esi, esi
0x1800319c8  mov     [rbp+0C0h+var_128], 4
0x1800319cf  lea     rax, [rbp+0C0h+var_130]
0x1800319d3  mov     [rsp+1C0h+nSize+4], esi
0x1800319d7  mov     [rbp+0C0h+var_108], rax
0x1800319db  lea     r8, [rsp+1C0h+nSize]; nSize
0x1800319e0  lea     rax, [rbp+0C0h+var_110]
0x1800319e4  mov     qword ptr [rsp+1C0h+pcbEncoded], rsi
0x1800319e9  mov     [rbp+0C0h+var_138], rax
0x1800319ed  lea     ebx, [rsi+1]
0x1800319f0  lea     rax, a2543; "2.5.4.3"
0x1800319f7  mov     [rbp+0C0h+var_110], ebx
0x1800319fa  xor     edx, edx; lpBuffer
0x1800319fc  mov     [rbp+0C0h+var_130], rax
0x180031a00  lea     ecx, [rsi+2]; NameType
0x180031a03  mov     [rbp+0C0h+pvStructInfo], rbx
0x180031a07  mov     [rsp+1C0h+phKey], rsi
0x180031a0c  xor     edi, edi
0x180031a0e  mov     [rsp+1C0h+phProvider], rsi
0x180031a13  mov     [rsp+1C0h+cbInput], esi
0x180031a17  mov     [rsp+1C0h+hMem], rsi
0x180031a1c  mov     [rbp+0C0h+var_118], rsi
0x180031a20  mov     [rbp+0C0h+var_120], esi
0x180031a23  mov     [rsp+1C0h+cbInput+4], esi
0x180031a27  mov     [rsp+1C0h+nSize], esi
0x180031a2b  call    cs:__imp_GetComputerNameExW
0x180031a32  nop     dword ptr [rax+rax+00h]
0x180031a37  test    eax, eax
0x180031a39  jnz     short loc_180031A83
0x180031a3b  call    cs:__imp_GetLastError
0x180031a42  nop     dword ptr [rax+rax+00h]
0x180031a47  mov     ebx, eax
0x180031a49  cmp     eax, 0EAh
0x180031a4e  jz      short loc_180031A83
0x180031a50  cmp     eax, 6Fh ; 'o'
0x180031a53  jz      short loc_180031A83
0x180031a55  mov     r9d, 0BA0h
0x180031a5b  lea     rdx, aDwerror; "dwError"
0x180031a62  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031a69  mov     ecx, ebx
0x180031a6b  call    DebugTraceError
0x180031a70  mov     ecx, ebx; dwErrCode
0x180031a72  call    cs:__imp_SetLastError
0x180031a79  nop     dword ptr [rax+rax+00h]
0x180031a7e  jmp     loc_180031FDE
0x180031a83  mov     eax, [rsp+1C0h+nSize]
0x180031a87  xor     ecx, ecx; uFlags
0x180031a89  add     eax, eax
0x180031a8b  mov     edx, eax; uBytes
0x180031a8d  mov     [rbp+0C0h+var_120], eax
0x180031a90  call    cs:__imp_LocalAlloc
0x180031a97  nop     dword ptr [rax+rax+00h]
0x180031a9c  mov     [rbp+0C0h+var_118], rax
0x180031aa0  test    rax, rax
0x180031aa3  jnz     short loc_180031AC8
0x180031aa5  mov     r9d, 0BAAh
0x180031aab  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031ab2  lea     rdx, aErrorNotEnough; "ERROR_NOT_ENOUGH_MEMORY"
0x180031ab9  lea     ecx, [rax+8]
0x180031abc  call    DebugTraceError
0x180031ac1  mov     ecx, 8
0x180031ac6  jmp     short loc_180031A72
0x180031ac8  lea     r8, [rsp+1C0h+nSize]; nSize
0x180031acd  mov     rdx, rax; lpBuffer
0x180031ad0  mov     ecx, 2; NameType
0x180031ad5  call    cs:__imp_GetComputerNameExW
0x180031adc  nop     dword ptr [rax+rax+00h]
0x180031ae1  test    eax, eax
0x180031ae3  jnz     short loc_180031B11
0x180031ae5  call    cs:__imp_GetLastError
0x180031aec  nop     dword ptr [rax+rax+00h]
0x180031af1  mov     r9d, 0BB3h
0x180031af7  lea     rdx, aGetlasterror; "GetLastError()"
0x180031afe  mov     ecx, eax
0x180031b00  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031b07  call    DebugTraceError
0x180031b0c  jmp     loc_180031FDE
0x180031b11  lea     rax, [rsp+1C0h+cbInput]
0x180031b16  mov     [rsp+1C0h+dwFlags], esi; dwFlags
0x180031b1a  mov     [rsp+1C0h+pcbResult], rax; pcbResult
0x180031b1f  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x180031b26  xor     r9d, r9d; pbOutput
0x180031b29  mov     [rsp+1C0h+cbOutput], esi; cbOutput
0x180031b2d  xor     edx, edx; hExportKey
0x180031b2f  mov     rcx, r15; hKey
0x180031b32  call    cs:__imp_BCryptExportKey
0x180031b39  nop     dword ptr [rax+rax+00h]
0x180031b3e  mov     ebx, eax
0x180031b40  test    eax, eax
0x180031b42  jns     short loc_180031B56
0x180031b44  mov     r9d, 0BC0h
0x180031b4a  lea     rdx, aNtstatus; "ntStatus"
0x180031b51  jmp     loc_180031A62
0x180031b56  mov     edx, [rsp+1C0h+cbInput]; uBytes
0x180031b5a  xor     ecx, ecx; uFlags
0x180031b5c  call    cs:__imp_LocalAlloc
0x180031b63  nop     dword ptr [rax+rax+00h]
0x180031b68  mov     r14, rax
0x180031b6b  test    rax, rax
0x180031b6e  jnz     short loc_180031B85
0x180031b70  mov     r9d, 0BC8h
0x180031b76  lea     rdx, aErrorNotEnough; "ERROR_NOT_ENOUGH_MEMORY"
0x180031b7d  lea     ecx, [rax+8]
0x180031b80  jmp     loc_180031B00
0x180031b85  lea     rax, [rsp+1C0h+cbInput]
0x180031b8a  mov     [rsp+1C0h+dwFlags], esi; dwFlags
0x180031b8e  mov     [rsp+1C0h+pcbResult], rax; pcbResult
0x180031b93  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x180031b9a  mov     eax, [rsp+1C0h+cbInput]
0x180031b9e  mov     r9, r14; pbOutput
0x180031ba1  xor     edx, edx; hExportKey
0x180031ba3  mov     [rsp+1C0h+cbOutput], eax; cbOutput
0x180031ba7  mov     rcx, r15; hKey
0x180031baa  call    cs:__imp_BCryptExportKey
0x180031bb1  nop     dword ptr [rax+rax+00h]
0x180031bb6  xor     r15d, r15d
0x180031bb9  mov     ebx, eax
0x180031bbb  test    eax, eax
0x180031bbd  jns     short loc_180031BED
0x180031bbf  mov     r9d, 0BD5h
0x180031bc5  lea     rdx, aNtstatus; "ntStatus"
0x180031bcc  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031bd3  mov     ecx, ebx
0x180031bd5  call    DebugTraceError
0x180031bda  mov     ecx, ebx; dwErrCode
0x180031bdc  call    cs:__imp_SetLastError
0x180031be3  nop     dword ptr [rax+rax+00h]
0x180031be8  jmp     loc_180031FCF
0x180031bed  xor     r8d, r8d; dwFlags
0x180031bf0  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180031bf7  lea     rcx, [rsp+1C0h+phProvider]; phProvider
0x180031bfc  call    cs:__imp_NCryptOpenStorageProvider
0x180031c03  nop     dword ptr [rax+rax+00h]
0x180031c08  mov     ebx, eax
0x180031c0a  test    eax, eax
0x180031c0c  jz      short loc_180031C1D
0x180031c0e  mov     r9d, 0BE2h
0x180031c14  lea     rdx, aStatus; "Status"
0x180031c1b  jmp     short loc_180031BCC
0x180031c1d  mov     rcx, [rsp+1C0h+phProvider]; hProvider
0x180031c22  lea     r8, aRsa; "RSA"
0x180031c29  mov     dword ptr [rsp+1C0h+pcbResult], r15d; dwFlags
0x180031c2e  lea     rdx, [rsp+1C0h+phKey]; phKey
0x180031c33  xor     r9d, r9d; pszKeyName
0x180031c36  mov     [rsp+1C0h+cbOutput], r15d; dwLegacyKeySpec
0x180031c3b  call    cs:__imp_NCryptCreatePersistedKey
0x180031c42  nop     dword ptr [rax+rax+00h]
0x180031c47  mov     ebx, eax
0x180031c49  test    eax, eax
0x180031c4b  jz      short loc_180031C55
0x180031c4d  mov     r9d, 0BEFh
0x180031c53  jmp     short loc_180031C14
0x180031c55  mov     r9d, [rsp+1C0h+cbInput]; cbInput
0x180031c5a  lea     rdx, pszBlobType; "CAPIPRIVATEBLOB"
0x180031c61  mov     rcx, [rsp+1C0h+phKey]; hObject
0x180031c66  mov     r8, r14; pbInput
0x180031c69  mov     [rsp+1C0h+cbOutput], r15d; dwFlags
0x180031c6e  call    cs:__imp_NCryptSetProperty
0x180031c75  nop     dword ptr [rax+rax+00h]
0x180031c7a  mov     ebx, eax
0x180031c7c  test    eax, eax
0x180031c7e  jz      short loc_180031C88
0x180031c80  mov     r9d, 0BFBh
0x180031c86  jmp     short loc_180031C14
0x180031c88  mov     rcx, [rsp+1C0h+phKey]; hKey
0x180031c8d  xor     edx, edx; dwFlags
0x180031c8f  call    cs:__imp_NCryptFinalizeKey
0x180031c96  nop     dword ptr [rax+rax+00h]
0x180031c9b  mov     ebx, eax
0x180031c9d  test    eax, eax
0x180031c9f  jz      short loc_180031CAC
0x180031ca1  mov     r9d, 0C05h
0x180031ca7  jmp     loc_180031C14
0x180031cac  mov     rcx, [rsp+1C0h+phKey]; hCryptProvOrNCryptKey
0x180031cb1  lea     rax, [rsp+1C0h+nSize+4]
0x180031cb6  xor     r9d, r9d; pInfo
0x180031cb9  mov     qword ptr [rsp+1C0h+cbOutput], rax; pcbInfo
0x180031cbe  lea     ebx, [r9+1]
0x180031cc2  mov     r8d, ebx; dwCertEncodingType
0x180031cc5  mov     edx, ebx; dwKeySpec
0x180031cc7  call    cs:__imp_CryptExportPublicKeyInfo
0x180031cce  nop     dword ptr [rax+rax+00h]
0x180031cd3  test    eax, eax
0x180031cd5  jnz     short loc_180031D03
0x180031cd7  call    cs:__imp_GetLastError
0x180031cde  nop     dword ptr [rax+rax+00h]
0x180031ce3  mov     r9d, 0C13h
0x180031ce9  mov     ecx, eax
0x180031ceb  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031cf2  lea     rdx, aGetlasterror; "GetLastError()"
0x180031cf9  call    DebugTraceError
0x180031cfe  jmp     loc_180031FCF
0x180031d03  mov     edx, [rsp+1C0h+nSize+4]; uBytes
0x180031d07  xor     ecx, ecx; uFlags
0x180031d09  call    cs:__imp_LocalAlloc
0x180031d10  nop     dword ptr [rax+rax+00h]
0x180031d15  mov     rsi, rax
0x180031d18  test    rax, rax
0x180031d1b  jnz     short loc_180031D31
0x180031d1d  call    cs:__imp_GetLastError
0x180031d24  nop     dword ptr [rax+rax+00h]
0x180031d29  mov     r9d, 0C19h
0x180031d2f  jmp     short loc_180031CE9
0x180031d31  mov     rcx, [rsp+1C0h+phKey]; hCryptProvOrNCryptKey
0x180031d36  lea     rax, [rsp+1C0h+nSize+4]
0x180031d3b  mov     r9, rsi; pInfo
0x180031d3e  mov     qword ptr [rsp+1C0h+cbOutput], rax; pcbInfo
0x180031d43  mov     r8d, ebx; dwCertEncodingType
0x180031d46  mov     edx, ebx; dwKeySpec
0x180031d48  call    cs:__imp_CryptExportPublicKeyInfo
0x180031d4f  nop     dword ptr [rax+rax+00h]
0x180031d54  test    eax, eax
0x180031d56  jnz     short loc_180031D6F
0x180031d58  call    cs:__imp_GetLastError
0x180031d5f  nop     dword ptr [rax+rax+00h]
0x180031d64  mov     r9d, 0C22h
0x180031d6a  jmp     loc_180031CE9
0x180031d6f  xor     r9d, r9d; pbEncoded
0x180031d72  lea     rax, [rsp+1C0h+pcbEncoded]
0x180031d77  lea     r8, [rbp+0C0h+pvStructInfo]; pvStructInfo
0x180031d7b  mov     qword ptr [rsp+1C0h+cbOutput], rax; pcbEncoded
0x180031d80  mov     ecx, ebx; dwCertEncodingType
0x180031d82  lea     r15d, [r9+7]
0x180031d86  mov     edx, r15d; lpszStructType
0x180031d89  call    cs:__imp_CryptEncodeObject
0x180031d90  nop     dword ptr [rax+rax+00h]
0x180031d95  test    eax, eax
0x180031d97  jnz     short loc_180031DB0
0x180031d99  call    cs:__imp_GetLastError
0x180031da0  nop     dword ptr [rax+rax+00h]
0x180031da5  mov     r9d, 0C30h
0x180031dab  jmp     loc_180031CE9
0x180031db0  mov     edx, [rsp+1C0h+pcbEncoded]; uBytes
0x180031db4  xor     ecx, ecx; uFlags
0x180031db6  call    cs:__imp_LocalAlloc
0x180031dbd  nop     dword ptr [rax+rax+00h]
0x180031dc2  mov     [rsp+1C0h+hMem], rax
0x180031dc7  test    rax, rax
0x180031dca  jnz     short loc_180031DE3
0x180031dcc  call    cs:__imp_GetLastError
0x180031dd3  nop     dword ptr [rax+rax+00h]
0x180031dd8  mov     r9d, 0C37h
0x180031dde  jmp     loc_180031CE9
0x180031de3  lea     rcx, [rsp+1C0h+pcbEncoded]
0x180031de8  mov     r9, rax; pbEncoded
0x180031deb  mov     qword ptr [rsp+1C0h+cbOutput], rcx; pcbEncoded
0x180031df0  lea     r8, [rbp+0C0h+pvStructInfo]; pvStructInfo
0x180031df4  mov     ecx, ebx; dwCertEncodingType
0x180031df6  mov     rdx, r15; lpszStructType
0x180031df9  call    cs:__imp_CryptEncodeObject
0x180031e00  nop     dword ptr [rax+rax+00h]
0x180031e05  test    eax, eax
0x180031e07  jnz     short loc_180031E20
0x180031e09  call    cs:__imp_GetLastError
0x180031e10  nop     dword ptr [rax+rax+00h]
0x180031e15  mov     r9d, 0C40h
0x180031e1b  jmp     loc_180031CE9
0x180031e20  mov     rbx, [rbp+0C0h+arg_8]
0x180031e27  lea     rax, a13143229; "1.3.14.3.2.29"
0x180031e2e  mov     [rbp+0C0h+pSignatureAlgorithm.pszObjId], rax
0x180031e32  lea     rcx, [rbp+0C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180031e36  mov     rax, [rsp+1C0h+hMem]
0x180031e3b  mov     r15d, 10h
0x180031e41  mov     [rbp+0C0h+var_C8], rax
0x180031e45  mov     eax, [rsp+1C0h+pcbEncoded]
0x180031e49  mov     [rbp+0C0h+var_D0], eax
0x180031e4c  mov     [rbp+0C0h+var_100], 2
0x180031e53  mov     [rbp+0C0h+var_F0], rbx
0x180031e57  mov     [rbp+0C0h+var_F8], r15d
0x180031e5b  mov     [rbp+0C0h+pSignatureAlgorithm.Parameters.cbData], edi
0x180031e5e  mov     [rbp+0C0h+pSignatureAlgorithm.Parameters.pbData], rdi
0x180031e62  call    cs:__imp_GetSystemTimeAsFileTime
0x180031e69  nop     dword ptr [rax+rax+00h]
0x180031e6e  mov     rax, [rsp+1C0h+hMem]
0x180031e73  mov     rcx, 11ED178C6C000h
0x180031e7d  add     rcx, qword ptr [rbp+0C0h+SystemTimeAsFileTime.dwLowDateTime]
0x180031e81  mov     [rbp+0C0h+var_A8], rax
0x180031e85  mov     eax, [rsp+1C0h+pcbEncoded]
0x180031e89  mov     [rbp+0C0h+var_B0], eax
0x180031e8c  lea     rax, [rsp+1C0h+cbInput+4]
  ... truncated ...
```
