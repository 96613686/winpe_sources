# _PkcsExportPlainTextKeyEcc

- ea: `0x1800256f0`
- end: `0x180025e53`
- name: `_PkcsExportPlainTextKeyEcc`
- size: `1891`
- prototype: `__int64 __fastcall(__int64, __int64, __int16, _BYTE *, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180034e80`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180025018`
- `0x1800256f0`
- `0x18003623c`
- `0x180038970`
- `0x1800398b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d62`
- `bcrypt!BCryptGetProperty` at `0x18002586b`
- `bcrypt!BCryptGetProperty` at `0x1800258b5`
- `bcrypt!BCryptGetProperty` at `0x18002586b`
- `bcrypt!BCryptGetProperty` at `0x1800258b5`
- `CRYPT32!CryptEncodeObjectEx` at `0x180025af3`
- `CRYPT32!CryptEncodeObjectEx` at `0x180025ca7`
- `CRYPT32!CryptEncodeObjectEx` at `0x180025af3`
- `CRYPT32!CryptEncodeObjectEx` at `0x180025ca7`
- `CRYPT32!CryptEncodeObject` at `0x1800257ea`
- `CRYPT32!CryptEncodeObject` at `0x1800258eb`
- `CRYPT32!CryptEncodeObject` at `0x180025a94`
- `CRYPT32!CryptEncodeObject` at `0x180025c1b`
- `CRYPT32!CryptEncodeObject` at `0x180025d00`
- `CRYPT32!CryptEncodeObject` at `0x180025d52`
- `CRYPT32!CryptEncodeObject` at `0x1800257ea`
- `CRYPT32!CryptEncodeObject` at `0x1800258eb`
- `CRYPT32!CryptEncodeObject` at `0x180025a94`
- `CRYPT32!CryptEncodeObject` at `0x180025c1b`
- `CRYPT32!CryptEncodeObject` at `0x180025d00`
- `CRYPT32!CryptEncodeObject` at `0x180025d52`

## string_xrefs

- `0x180025793`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18002581f`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18002596e`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180025b7c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180025dc5`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall PkcsExportPlainTextKeyEcc(
        __int64 a1,
        __int64 a2,
        __int16 a3,
        _BYTE *a4,
        unsigned int a5,
        _DWORD *a6)
{
  _DWORD *v6; // r12
  __int16 v9; // r15
  int Property; // esi
  signed int LastError; // eax
  __int64 v12; // r9
  PUCHAR v13; // rbx
  signed int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  size_t v18; // rbx
  void *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rcx
  signed int v23; // eax
  signed int v24; // eax
  DWORD v25; // edi
  unsigned int v26; // eax
  DWORD v27; // r13d
  unsigned int v28; // ecx
  unsigned int v29; // eax
  DWORD v30; // ebx
  DWORD v31; // ecx
  _DWORD *v32; // rdx
  signed int v33; // eax
  signed int v34; // eax
  signed int v35; // eax
  signed int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rdx
  _BYTE *v39; // rax
  unsigned int dwFlags; // [rsp+28h] [rbp-91h]
  ULONG pcbResult; // [rsp+40h] [rbp-79h] BYREF
  DWORD pcbEncoded; // [rsp+44h] [rbp-75h] BYREF
  DWORD v44; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v45; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD v46; // [rsp+50h] [rbp-69h] BYREF
  _DWORD *v47; // [rsp+58h] [rbp-61h] BYREF
  PUCHAR v48; // [rsp+60h] [rbp-59h]
  __int128 v49; // [rsp+68h] [rbp-51h] BYREF
  __int128 v50; // [rsp+78h] [rbp-41h]
  size_t Size[2]; // [rsp+88h] [rbp-31h]
  __int64 v52; // [rsp+98h] [rbp-21h]
  __int128 v53; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v54; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v55; // [rsp+C0h] [rbp+7h]
  __int64 pvStructInfo; // [rsp+118h] [rbp+5Fh] BYREF
  __int16 v57; // [rsp+120h] [rbp+67h] BYREF

  pvStructInfo = a2;
  v6 = 0;
  v57 = 0;
  v45 = 0;
  v44 = 0;
  v46 = 0;
  pcbEncoded = 0;
  pcbResult = 0;
  v48 = 0;
  v55 = 0;
  v52 = 0;
  v9 = a3 & 0x3000;
  v47 = 0;
  v53 = 0;
  v54 = 0;
  v49 = 0;
  v50 = 0;
  *(_OWORD *)Size = 0;
  if ( (a3 & 0x3000) != 0x3000 )
  {
    if ( (a3 & 0x3000) == 0 )
      v9 = 12288;
    if ( a2 && (v9 & 0x2000) != 0 )
    {
      if ( !CryptEncodeObject(1u, (LPCSTR)0x49, &pvStructInfo, 0, &pcbEncoded) )
      {
        LastError = GetLastError();
        Property = LastError;
        if ( LastError > 0 )
          Property = (unsigned __int16)LastError | 0x80070000;
        v12 = 2807;
        goto LABEL_13;
      }
    }
    else
    {
      if ( (v9 & 0x1000) == 0 )
      {
        Property = -2146893815;
        v20 = 2865;
        v21 = 2148073481LL;
        goto LABEL_77;
      }
      Property = BCryptGetProperty(*(BCRYPT_HANDLE *)(a1 + 104), L"ECCParameters", 0, 0, &pcbResult, 0);
      if ( Property )
        goto LABEL_14;
      v48 = (PUCHAR)SafeAllocaAllocateFromHeap(pcbResult);
      v13 = v48;
      if ( !v48 )
        goto LABEL_87;
      Property = BCryptGetProperty(*(BCRYPT_HANDLE *)(a1 + 104), L"ECCParameters", v48, pcbResult, &pcbResult, 0);
      if ( Property )
      {
LABEL_14:
        if ( Property >= 0 )
          goto LABEL_81;
        goto LABEL_78;
      }
      LODWORD(v53) = pcbResult;
      *((_QWORD *)&v53 + 1) = v13;
      if ( !CryptEncodeObject(1u, (LPCSTR)0x55, &v53, 0, &pcbEncoded) )
      {
        v14 = GetLastError();
        Property = v14;
        if ( v14 > 0 )
          Property = (unsigned __int16)v14 | 0x80070000;
        v12 = 2854;
        goto LABEL_13;
      }
    }
    v15 = PkcsAllocAndExportKeyBlob(
            *(_QWORD *)(a1 + 112),
            a1,
            (__int64)L"ECCPRIVATEBLOB",
            (__int64 *)&v47,
            &v45,
            dwFlags);
    Property = v15;
    if ( v15 < 0 )
    {
      v16 = 2880;
      v17 = (unsigned int)v15;
LABEL_28:
      DebugTraceError(v17, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v16);
      v6 = v47;
      goto LABEL_78;
    }
    if ( v45 < 8 )
    {
      Property = -2146893821;
      v16 = 2887;
      v17 = 2148073475LL;
      goto LABEL_28;
    }
    v6 = v47;
    *((_QWORD *)&v50 + 1) = pvStructInfo;
    LODWORD(v49) = 1;
    *(_QWORD *)&v50 = (char *)v47 + (unsigned int)(2 * v47[1]) + 8;
    DWORD2(v49) = v47[1];
    v18 = (unsigned int)v47[1];
    LODWORD(v52) = 0;
    LODWORD(Size[0]) = 2 * v18 + 1;
    v19 = (void *)SafeAllocaAllocateFromHeap(LODWORD(Size[0]));
    Size[1] = (size_t)v19;
    if ( v19 )
    {
      memset_0(v19, 0, LODWORD(Size[0]));
      *(_BYTE *)Size[1] = 4;
      memcpy_0((void *)(Size[1] + 1), v6 + 2, v18);
      memcpy_0((void *)(v18 + Size[1] + 1), (char *)v6 + (unsigned int)v6[1] + 8, v18);
      v22 = *(unsigned int *)(a1 + 40);
      if ( (_DWORD)v22 == 0xFFFFFF )
      {
        v22 = 2;
        if ( *v6 != 844317509 && *v6 != 877871941 && *v6 != 911426373 && *v6 != 1447314245 )
          v22 = 6;
      }
      PkcsMapCngToCertKeyUsage(v22, &v54, &v57);
      if ( !CryptEncodeObject(1u, (LPCSTR)0x1A, &v54, 0, &v46) )
      {
        v23 = GetLastError();
        Property = v23;
        if ( v23 > 0 )
          Property = (unsigned __int16)v23 | 0x80070000;
        v12 = 2954;
        goto LABEL_13;
      }
      if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x52, &v49, 0, 0, 0, &v44) )
      {
        v24 = GetLastError();
        Property = v24;
        if ( v24 > 0 )
          Property = (unsigned __int16)v24 | 0x80070000;
        v12 = 2969;
        goto LABEL_13;
      }
      v25 = v46;
      v26 = 74;
      v27 = pcbEncoded;
      if ( v46 )
        v26 = 140;
      v28 = v26 + pcbEncoded;
      if ( v26 + pcbEncoded >= v26 )
      {
        v29 = v28 + v46;
        if ( v28 + v46 >= v28 )
        {
          v30 = v44;
          v31 = v29 + v44;
          if ( v29 + v44 >= v29 )
          {
            *a6 = v31;
            if ( !a4 )
              goto LABEL_81;
            if ( a5 < v31 )
            {
              Property = -2146893784;
              DebugTraceError(
                2148073512LL,
                "status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
                3003);
              goto LABEL_79;
            }
            memset_0(a4, 0, v31);
            v32 = a4 + 56;
            if ( v25 )
            {
              *((_QWORD *)a4 + 6) = v32;
              *((_QWORD *)a4 + 8) = a4 + 72;
              *((_DWORD *)a4 + 20) = 1;
              *((_QWORD *)a4 + 9) = a4 + 112;
              *((_QWORD *)a4 + 11) = a4 + 96;
              *v32 = 1;
              *((_DWORD *)a4 + 24) = v25;
              *((_QWORD *)a4 + 13) = *((_QWORD *)a4 + 9) + 10LL;
              strcpy(*((char **)a4 + 9), "2.5.29.15");
              if ( !CryptEncodeObject(1u, (LPCSTR)0x1A, &v54, *((BYTE **)a4 + 13), (DWORD *)a4 + 24) )
              {
                v33 = GetLastError();
                Property = v33;
                if ( v33 > 0 )
                  Property = (unsigned __int16)v33 | 0x80070000;
                v12 = 3044;
                goto LABEL_13;
              }
              v32 = (_DWORD *)(*((_QWORD *)a4 + 13) + *((unsigned int *)a4 + 24));
              v30 = v44;
              v27 = pcbEncoded;
            }
            *((_QWORD *)a4 + 5) = v32;
            *((_DWORD *)a4 + 4) = v27;
            *((_QWORD *)a4 + 3) = (char *)v32 + v30;
            *((_QWORD *)a4 + 1) = (char *)v32 + v30 + (unsigned __int64)v27;
            *((_DWORD *)a4 + 8) = v30;
            if ( CryptEncodeObjectEx(1u, (LPCSTR)0x52, &v49, 0, 0, v32, (DWORD *)a4 + 8) )
            {
              if ( pvStructInfo && (v9 & 0x2000) != 0 )
              {
                if ( !CryptEncodeObject(1u, (LPCSTR)0x49, &pvStructInfo, *((BYTE **)a4 + 3), (DWORD *)a4 + 4) )
                {
                  v35 = GetLastError();
                  Property = v35;
                  if ( v35 > 0 )
                    Property = (unsigned __int16)v35 | 0x80070000;
                  v12 = 3091;
                  goto LABEL_13;
                }
              }
              else if ( (v9 & 0x1000) != 0
                     && !CryptEncodeObject(1u, (LPCSTR)0x55, &v53, *((BYTE **)a4 + 3), (DWORD *)a4 + 4) )
              {
                v36 = GetLastError();
                Property = v36;
                if ( v36 > 0 )
                  Property = (unsigned __int16)v36 | 0x80070000;
                v12 = 3107;
                goto LABEL_13;
              }
              strcpy(*((char **)a4 + 1), "1.2.840.10045.2.1");
              goto LABEL_81;
            }
            v34 = GetLastError();
            Property = v34;
            if ( v34 > 0 )
              Property = (unsigned __int16)v34 | 0x80070000;
            v12 = 3074;
LABEL_13:
            DebugTraceError(
              (unsigned int)Property,
              "status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
              v12);
            goto LABEL_14;
          }
        }
      }
      Property = -2146893819;
      v20 = 2990;
      v21 = 2148073477LL;
    }
    else
    {
      Property = -2146893810;
      v20 = 2908;
      v21 = 2148073486LL;
    }
LABEL_77:
    DebugTraceError(v21, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v20);
    goto LABEL_78;
  }
  Property = -2146893819;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
      (unsigned int)"status",
      5,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
      229);
LABEL_78:
  if ( a4 )
  {
LABEL_79:
    v37 = a5;
    if ( a5 )
    {
      do
      {
        *a4++ = 0;
        --v37;
      }
      while ( v37 );
    }
  }
LABEL_81:
  if ( v48 )
    MSCryptFree(v48);
  if ( v6 )
  {
    v38 = v45;
    v39 = v6;
    if ( v45 )
    {
      do
      {
        *v39++ = 0;
        --v38;
      }
      while ( v38 );
    }
    MSCryptFree(v6);
  }
LABEL_87:
  if ( Size[1] )
    MSCryptFree(Size[1]);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800256f0  mov     [rsp-8+arg_0], rbx
0x1800256f5  mov     [rsp-8+pvStructInfo], rdx
0x1800256fa  push    rbp
0x1800256fb  push    rsi
0x1800256fc  push    rdi
0x1800256fd  push    r12
0x1800256ff  push    r13
0x180025701  push    r14
0x180025703  push    r15
0x180025705  lea     rbp, [rsp-17h]
0x18002570a  sub     rsp, 0D0h
0x180025711  xor     eax, eax
0x180025713  xorps   xmm0, xmm0
0x180025716  xor     r12d, r12d
0x180025719  mov     [rbp+47h+arg_10], ax
0x18002571d  mov     [rbp+47h+var_B4], eax
0x180025720  mov     r15d, r8d
0x180025723  mov     [rbp+47h+var_B8], eax
0x180025726  xorps   xmm1, xmm1
0x180025729  mov     [rbp+47h+var_B0], eax
0x18002572c  mov     r14, r9
0x18002572f  mov     [rbp+47h+var_BC], eax
0x180025732  mov     r13, rcx
0x180025735  mov     [rbp+47h+pcbResult], eax
0x180025738  mov     [rbp+47h+var_A0], rax
0x18002573c  mov     [rbp+47h+var_40], rax
0x180025740  mov     [rbp+47h+var_68], rax
0x180025744  mov     eax, 3000h
0x180025749  and     r15d, eax
0x18002574c  mov     [rbp+47h+var_A8], r12
0x180025750  movups  [rbp+47h+var_60], xmm0
0x180025754  movups  [rbp+47h+var_50], xmm1
0x180025758  movups  [rbp+47h+var_98], xmm0
0x18002575c  movups  [rbp+47h+var_88], xmm0
0x180025760  movups  xmmword ptr [rbp+47h+Size], xmm0
0x180025764  cmp     r15d, eax
0x180025767  jnz     short loc_1800257C0
0x180025769  mov     esi, 80090005h
0x18002576e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025775  lea     rax, WPP_GLOBAL_Control
0x18002577c  cmp     rcx, rax
0x18002577f  jz      loc_180025DD8
0x180025785  test    byte ptr [rcx+1Ch], 1
0x180025789  jz      loc_180025DD8
0x18002578f  mov     rcx, [rcx+10h]
0x180025793  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002579a  mov     dword ptr [rsp+100h+var_D0], 0AE5h
0x1800257a2  lea     r9, aStatus_0; "status"
0x1800257a9  mov     qword ptr [rsp+100h+dwFlags], r8
0x1800257ae  mov     dword ptr [rsp+100h+pcbEncoded], 80090005h
0x1800257b6  call    WPP_SF_sDsd
0x1800257bb  jmp     loc_180025DD8
0x1800257c0  test    r15d, r15d
0x1800257c3  cmovz   r15d, eax
0x1800257c7  test    rdx, rdx
0x1800257ca  jz      short loc_180025841
0x1800257cc  bt      r15d, 0Dh
0x1800257d1  jnb     short loc_180025841
0x1800257d3  xor     r9d, r9d; pbEncoded
0x1800257d6  lea     rax, [rbp+47h+var_BC]
0x1800257da  lea     r8, [rbp+47h+pvStructInfo]; pvStructInfo
0x1800257de  mov     [rsp+100h+pcbEncoded], rax; pcbEncoded
0x1800257e3  lea     edx, [r9+49h]; lpszStructType
0x1800257e7  lea     ecx, [rdx-48h]; dwCertEncodingType
0x1800257ea  call    cs:__imp_CryptEncodeObject
0x1800257f1  nop     dword ptr [rax+rax+00h]
0x1800257f6  test    eax, eax
0x1800257f8  jnz     loc_180025921
0x1800257fe  call    cs:__imp_GetLastError
0x180025805  nop     dword ptr [rax+rax+00h]
0x18002580a  mov     esi, eax
0x18002580c  test    eax, eax
0x18002580e  jle     short loc_180025819
0x180025810  movzx   esi, ax
0x180025813  or      esi, 80070000h
0x180025819  mov     r9d, 0AF7h
0x18002581f  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180025826  mov     ecx, esi
0x180025828  lea     rdx, aStatus_0; "status"
0x18002582f  call    DebugTraceError
0x180025834  test    esi, esi
0x180025836  js      loc_180025DD8
0x18002583c  jmp     loc_180025DF2
0x180025841  bt      r15d, 0Ch
0x180025846  jnb     loc_180025DB5
0x18002584c  mov     rcx, [rcx+68h]; hObject
0x180025850  lea     rax, [rbp+47h+pcbResult]
0x180025854  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x180025859  lea     rdx, aEccparameters; "ECCParameters"
0x180025860  xor     r9d, r9d; cbOutput
0x180025863  mov     [rsp+100h+pcbEncoded], rax; pcbResult
0x180025868  xor     r8d, r8d; pbOutput
0x18002586b  call    cs:__imp_BCryptGetProperty
0x180025872  nop     dword ptr [rax+rax+00h]
0x180025877  mov     esi, eax
0x180025879  test    eax, eax
0x18002587b  jnz     short loc_180025834
0x18002587d  mov     ecx, [rbp+47h+pcbResult]
0x180025880  call    SafeAllocaAllocateFromHeap
0x180025885  mov     [rbp+47h+var_A0], rax
0x180025889  mov     rbx, rax
0x18002588c  test    rax, rax
0x18002588f  jz      loc_180025E27
0x180025895  mov     r9d, [rbp+47h+pcbResult]; cbOutput
0x180025899  lea     rax, [rbp+47h+pcbResult]
0x18002589d  mov     rcx, [r13+68h]; hObject
0x1800258a1  lea     rdx, aEccparameters; "ECCParameters"
0x1800258a8  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x1800258ad  mov     r8, rbx; pbOutput
0x1800258b0  mov     [rsp+100h+pcbEncoded], rax; pcbResult
0x1800258b5  call    cs:__imp_BCryptGetProperty
0x1800258bc  nop     dword ptr [rax+rax+00h]
0x1800258c1  mov     esi, eax
0x1800258c3  test    eax, eax
0x1800258c5  jnz     loc_180025834
0x1800258cb  mov     eax, [rbp+47h+pcbResult]
0x1800258ce  lea     r8, [rbp+47h+var_60]; pvStructInfo
0x1800258d2  mov     dword ptr [rbp+47h+var_60], eax
0x1800258d5  lea     edx, [rsi+55h]; lpszStructType
0x1800258d8  lea     rax, [rbp+47h+var_BC]
0x1800258dc  mov     qword ptr [rbp+47h+var_60+8], rbx
0x1800258e0  xor     r9d, r9d; pbEncoded
0x1800258e3  mov     [rsp+100h+pcbEncoded], rax; pcbEncoded
0x1800258e8  lea     ecx, [rsi+1]; dwCertEncodingType
0x1800258eb  call    cs:__imp_CryptEncodeObject
0x1800258f2  nop     dword ptr [rax+rax+00h]
0x1800258f7  test    eax, eax
0x1800258f9  jnz     short loc_180025921
0x1800258fb  call    cs:__imp_GetLastError
0x180025902  nop     dword ptr [rax+rax+00h]
0x180025907  mov     esi, eax
0x180025909  test    eax, eax
0x18002590b  jle     short loc_180025916
0x18002590d  movzx   esi, ax
0x180025910  or      esi, 80070000h
0x180025916  mov     r9d, 0B26h
0x18002591c  jmp     loc_18002581F
0x180025921  mov     rcx, [r13+70h]
0x180025925  lea     rax, [rbp+47h+var_B4]
0x180025929  lea     r9, [rbp+47h+var_A8]
0x18002592d  mov     [rsp+100h+pcbEncoded], rax
0x180025932  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x180025939  mov     rdx, r13
0x18002593c  call    _PkcsAllocAndExportKeyBlob
0x180025941  mov     esi, eax
0x180025943  test    eax, eax
0x180025945  jns     short loc_180025951
0x180025947  mov     r9d, 0B40h
0x18002594d  mov     ecx, eax
0x18002594f  jmp     short loc_180025967
0x180025951  cmp     [rbp+47h+var_B4], 8
0x180025955  jnb     short loc_180025983
0x180025957  mov     esi, 80090003h
0x18002595c  mov     r9d, 0B47h
0x180025962  mov     ecx, 80090003h
0x180025967  lea     rdx, aStatus_0; "status"
0x18002596e  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180025975  call    DebugTraceError
0x18002597a  mov     r12, [rbp+47h+var_A8]
0x18002597e  jmp     loc_180025DD8
0x180025983  mov     r12, [rbp+47h+var_A8]
0x180025987  mov     rax, [rbp+47h+pvStructInfo]
0x18002598b  mov     qword ptr [rbp+47h+var_88+8], rax
0x18002598f  mov     dword ptr [rbp+47h+var_98], 1
0x180025996  mov     eax, [r12+4]
0x18002599b  lea     rcx, [r12+8]
0x1800259a0  add     eax, eax
0x1800259a2  add     rcx, rax
0x1800259a5  mov     qword ptr [rbp+47h+var_88], rcx
0x1800259a9  mov     eax, [r12+4]
0x1800259ae  mov     dword ptr [rbp+47h+var_98+8], eax
0x1800259b1  mov     ebx, [r12+4]
0x1800259b6  mov     dword ptr [rbp+47h+var_68], 0
0x1800259bd  lea     eax, ds:1[rbx*2]
0x1800259c4  mov     ecx, eax
0x1800259c6  mov     dword ptr [rbp+47h+Size], eax
0x1800259c9  call    SafeAllocaAllocateFromHeap
0x1800259ce  mov     [rbp+47h+Size+8], rax
0x1800259d2  test    rax, rax
0x1800259d5  jnz     short loc_1800259EC
0x1800259d7  mov     esi, 8009000Eh
0x1800259dc  mov     r9d, 0B5Ch
0x1800259e2  mov     ecx, 8009000Eh
0x1800259e7  jmp     loc_180025DC5
0x1800259ec  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x1800259f0  lea     rdi, [r12+8]
0x1800259f5  xor     edx, edx; Val
0x1800259f7  mov     rcx, rax; void *
0x1800259fa  call    memset_0
0x1800259ff  mov     rax, [rbp+47h+Size+8]
0x180025a03  mov     r8, rbx; Size
0x180025a06  mov     rdx, rdi; Src
0x180025a09  mov     byte ptr [rax], 4
0x180025a0c  mov     rcx, [rbp+47h+Size+8]
0x180025a10  inc     rcx; void *
0x180025a13  call    memcpy_0
0x180025a18  mov     rcx, [rbp+47h+Size+8]
0x180025a1c  mov     r8, rbx; Size
0x180025a1f  mov     edx, [r12+4]
0x180025a24  inc     rcx
0x180025a27  add     rcx, rbx; void *
0x180025a2a  add     rdx, rdi; Src
0x180025a2d  call    memcpy_0
0x180025a32  mov     ecx, [r13+28h]
0x180025a36  cmp     ecx, 0FFFFFFh
0x180025a3c  jnz     short loc_180025A70
0x180025a3e  cmp     dword ptr [r12], 32534345h
0x180025a46  mov     ecx, 2
0x180025a4b  jz      short loc_180025A70
0x180025a4d  cmp     dword ptr [r12], 34534345h
0x180025a55  jz      short loc_180025A70
0x180025a57  cmp     dword ptr [r12], 36534345h
0x180025a5f  jz      short loc_180025A70
0x180025a61  cmp     dword ptr [r12], 56444345h
0x180025a69  jz      short loc_180025A70
0x180025a6b  mov     ecx, 6
0x180025a70  lea     r8, [rbp+47h+arg_10]
0x180025a74  lea     rdx, [rbp+47h+var_50]
0x180025a78  call    _PkcsMapCngToCertKeyUsage
0x180025a7d  lea     rcx, [rbp+47h+var_B0]
0x180025a81  xor     r9d, r9d; pbEncoded
0x180025a84  mov     [rsp+100h+pcbEncoded], rcx; pcbEncoded
0x180025a89  lea     r8, [rbp+47h+var_50]; pvStructInfo
0x180025a8d  lea     edx, [r9+1Ah]; lpszStructType
0x180025a91  lea     ecx, [rdx-19h]; dwCertEncodingType
0x180025a94  call    cs:__imp_CryptEncodeObject
0x180025a9b  nop     dword ptr [rax+rax+00h]
0x180025aa0  test    eax, eax
0x180025aa2  jnz     short loc_180025ACA
0x180025aa4  call    cs:__imp_GetLastError
0x180025aab  nop     dword ptr [rax+rax+00h]
0x180025ab0  mov     esi, eax
0x180025ab2  test    eax, eax
0x180025ab4  jle     short loc_180025ABF
0x180025ab6  movzx   esi, ax
0x180025ab9  or      esi, 80070000h
0x180025abf  mov     r9d, 0B8Ah
0x180025ac5  jmp     loc_18002581F
0x180025aca  xor     r9d, r9d; dwFlags
0x180025acd  lea     rax, [rbp+47h+var_B8]
0x180025ad1  mov     [rsp+100h+var_D0], rax; pcbEncoded
0x180025ad6  lea     r8, [rbp+47h+var_98]; pvStructInfo
0x180025ada  mov     qword ptr [rsp+100h+dwFlags], 0; pvEncoded
0x180025ae3  mov     [rsp+100h+pcbEncoded], 0; pEncodePara
0x180025aec  lea     edx, [r9+52h]; lpszStructType
0x180025af0  lea     ecx, [rdx-51h]; dwCertEncodingType
0x180025af3  call    cs:__imp_CryptEncodeObjectEx
0x180025afa  nop     dword ptr [rax+rax+00h]
0x180025aff  test    eax, eax
0x180025b01  jnz     short loc_180025B29
0x180025b03  call    cs:__imp_GetLastError
0x180025b0a  nop     dword ptr [rax+rax+00h]
0x180025b0f  mov     esi, eax
0x180025b11  test    eax, eax
0x180025b13  jle     short loc_180025B1E
0x180025b15  movzx   esi, ax
0x180025b18  or      esi, 80070000h
0x180025b1e  mov     r9d, 0B99h
0x180025b24  jmp     loc_18002581F
0x180025b29  mov     edi, [rbp+47h+var_B0]
0x180025b2c  mov     eax, 4Ah ; 'J'
0x180025b31  mov     r13d, [rbp+47h+var_BC]
0x180025b35  test    edi, edi
0x180025b37  lea     ecx, [rax+42h]
0x180025b3a  cmovnz  eax, ecx
0x180025b3d  lea     ecx, [rax+r13]
0x180025b41  cmp     ecx, eax
0x180025b43  jb      loc_180025DA3
0x180025b49  lea     eax, [rcx+rdi]
0x180025b4c  cmp     eax, ecx
0x180025b4e  jb      loc_180025DA3
0x180025b54  mov     ebx, [rbp+47h+var_B8]
0x180025b57  lea     ecx, [rax+rbx]
0x180025b5a  cmp     ecx, eax
0x180025b5c  jb      loc_180025DA3
0x180025b62  mov     rax, [rbp+47h+arg_28]
0x180025b66  mov     [rax], ecx
0x180025b68  test    r14, r14
0x180025b6b  jz      loc_180025DF2
0x180025b71  cmp     [rbp+47h+arg_20], ecx
0x180025b74  jnb     short loc_180025B9E
0x180025b76  mov     r9d, 0BBBh
0x180025b7c  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180025b83  lea     rdx, aStatus_0; "status"
0x180025b8a  mov     ecx, 80090028h
0x180025b8f  mov     esi, 80090028h
0x180025b94  call    DebugTraceError
0x180025b99  jmp     loc_180025DDD
0x180025b9e  mov     r8d, ecx; Size
0x180025ba1  xor     edx, edx; Val
0x180025ba3  mov     rcx, r14; void *
0x180025ba6  call    memset_0
0x180025bab  lea     rdx, [r14+38h]
0x180025baf  test    edi, edi
0x180025bb1  jz      loc_180025C5E
0x180025bb7  lea     rcx, [rdx+10h]
0x180025bbb  mov     [r14+30h], rdx
0x180025bbf  mov     [rdx+8], rcx
0x180025bc3  lea     rbx, [rcx+18h]
0x180025bc7  mov     dword ptr [rcx+8], 1
  ... truncated ...
```
