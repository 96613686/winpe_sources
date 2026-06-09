# _PkcsImportPlainTextKeyEcc

- ea: `0x18004ae24`
- end: `0x18004b722`
- name: `_PkcsImportPlainTextKeyEcc`
- size: `2302`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180034c30`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180017580`
- `0x180023050`
- `0x180023934`
- `0x180033a10`
- `0x180038920`
- `0x180038970`
- `0x1800398b0`
- `0x180049d50`
- `0x180049dec`
- `0x18004ae24`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b608`
- `CRYPT32!CryptFindOIDInfo` at `0x18004b0dd`
- `CRYPT32!CryptFindOIDInfo` at `0x18004b0dd`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004af18`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004af67`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004afa9`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004af18`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004af67`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004afa9`

## string_xrefs

- `0x18004b016`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b097`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b0f7`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b13c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b340`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b3d6`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b41c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b481`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b54c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b5a1`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b5df`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b629`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b653`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall PkcsImportPlainTextKeyEcc(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r13d
  void *v6; // rdi
  _DWORD *v7; // r14
  _DWORD *v8; // r15
  unsigned int v9; // r12d
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // ecx
  const BYTE *v15; // r8
  _BYTE *v16; // rbx
  DWORD v17; // r9d
  signed int LastError; // eax
  _BYTE *v19; // rax
  int v20; // r13d
  int v21; // esi
  unsigned int v22; // edx
  __int64 v23; // r12
  unsigned __int8 *v24; // rax
  __int64 v25; // r8
  int v26; // ecx
  int v27; // edx
  DWORD v28; // ecx
  PCCRYPT_OID_INFO OIDInfo; // r15
  unsigned int v30; // esi
  _DWORD *v31; // rax
  _DWORD *v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rsi
  __int64 v36; // rdi
  char *v37; // r13
  char *v38; // r13
  unsigned int v39; // ebx
  int v40; // eax
  int v41; // eax
  int *pwszName; // r9
  __int64 v43; // rax
  unsigned int v44; // eax
  int v45; // eax
  size_t v46; // r12
  const void *v47; // r13
  unsigned int v48; // edx
  size_t v49; // rbx
  _DWORD *v50; // rax
  __int64 v51; // rdx
  char *v52; // rcx
  __int64 v53; // r9
  int v54; // eax
  int v55; // eax
  int v56; // eax
  signed int v57; // eax
  __int64 v58; // rcx
  _BYTE *v59; // rax
  __int64 v60; // rdx
  _BYTE *v61; // rax
  _BYTE *v62; // rcx
  __int64 v63; // rax
  DWORD dwFlags[2]; // [rsp+28h] [rbp-61h]
  unsigned int v66; // [rsp+48h] [rbp-41h]
  int v67; // [rsp+4Ch] [rbp-3Dh] BYREF
  __int64 v68; // [rsp+50h] [rbp-39h] BYREF
  void *v69; // [rsp+58h] [rbp-31h] BYREF
  DWORD v70[4]; // [rsp+60h] [rbp-29h] BYREF
  DWORD pcbStructInfo; // [rsp+70h] [rbp-19h] BYREF
  DWORD v72; // [rsp+74h] [rbp-15h] BYREF
  unsigned int Size; // [rsp+78h] [rbp-11h]
  int Size_4; // [rsp+7Ch] [rbp-Dh]
  void **pvStructInfo; // [rsp+80h] [rbp-9h] BYREF
  unsigned int *v76; // [rsp+88h] [rbp-1h] BYREF

  v4 = 0;
  v6 = 0;
  v68 = 0;
  v7 = 0;
  v70[0] = 0;
  v8 = 0;
  v69 = 0;
  v9 = 0;
  v67 = 0;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  v76 = 0;
  v72 = 0;
  if ( !*(_QWORD *)(a3 + 40) || !*(_DWORD *)(a3 + 32) )
  {
    v11 = -2146893819;
    v12 = 3188;
    v13 = 2148073477LL;
    goto LABEL_97;
  }
  v10 = PkcsScanAttrList(*(_QWORD *)(a3 + 48), &v67);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 3195;
    v13 = (unsigned int)v10;
LABEL_97:
    DebugTraceError(v13, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v12);
    goto LABEL_98;
  }
  v14 = v67;
  v15 = *(const BYTE **)(a3 + 24);
  v16 = 0;
  if ( v67 == -1 )
    v14 = 0xFFFFFF;
  Size_4 = v14;
  v67 = v14 != 2;
  if ( v15 )
  {
    v17 = *(_DWORD *)(a3 + 16);
    if ( v17 )
    {
      if ( CryptDecodeObjectEx(1u, (LPCSTR)0x49, v15, v17, 0x8004u, &pDecodePara, &pvStructInfo, &pcbStructInfo) )
        v16 = *pvStructInfo;
      else
        CryptDecodeObjectEx(
          1u,
          (LPCSTR)0x55,
          *(const BYTE **)(a3 + 24),
          *(_DWORD *)(a3 + 16),
          0x8004u,
          &pDecodePara,
          &v76,
          &v72);
    }
  }
  if ( !CryptDecodeObjectEx(
          1u,
          (LPCSTR)0x52,
          *(const BYTE **)(a3 + 40),
          *(_DWORD *)(a3 + 32),
          0x8001u,
          &pDecodePara,
          &v68,
          v70) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = 3256;
    v13 = v11;
    goto LABEL_97;
  }
  v19 = *(_BYTE **)(v68 + 40);
  if ( !v19 )
    goto LABEL_24;
  v20 = *(_DWORD *)(v68 + 32);
  if ( !v20 )
  {
    v4 = 0;
LABEL_24:
    v21 = 0;
    goto LABEL_25;
  }
  if ( (((*v19 - 4) & 0xFC) != 0 || *v19 == 5) && (((_BYTE)v20 - 1) & 1) != 0 )
  {
    v11 = -2146893819;
    DebugTraceError(2148073477LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3273);
LABEL_98:
    v30 = 0;
    goto LABEL_99;
  }
  v21 = 1;
  v4 = (unsigned int)(v20 - 1) >> 1;
LABEL_25:
  v22 = *(_DWORD *)(v68 + 8);
  v23 = v22;
  v24 = *(unsigned __int8 **)(v68 + 24);
  Size = v22;
  if ( v22 <= v4 )
    v23 = v4;
  if ( v24 )
  {
    if ( v16 )
    {
      v25 = v16 - v24;
      do
      {
        v26 = v24[v25];
        v27 = *v24 - v26;
        if ( v27 )
          break;
        ++v24;
      }
      while ( v26 );
      if ( v27 )
      {
        v11 = -2146893819;
        DebugTraceError(2148073477LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3297);
LABEL_35:
        v9 = 0;
        goto LABEL_98;
      }
    }
    else
    {
      v16 = v24;
    }
  }
  else if ( !v16 )
  {
    if ( !v76 )
    {
      v57 = GetLastError();
      v11 = v57;
      if ( v57 > 0 )
        v11 = (unsigned __int16)v57 | 0x80070000;
      DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3556);
      v9 = 0;
      goto LABEL_98;
    }
    v46 = *v76;
    v47 = (const void *)*((_QWORD *)v76 + 1);
    v48 = v46 + v22 + 4;
    v66 = v48;
    if ( v21 )
    {
      v48 += *(_DWORD *)(v68 + 32) - 1;
      v66 = v48;
    }
    v49 = v48;
    v50 = (_DWORD *)SafeAllocaAllocateFromHeap(v48);
    v8 = v50;
    if ( !v50 )
    {
      v11 = -2146893810;
      DebugTraceError(2148073486LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3490);
      v9 = v66;
      goto LABEL_98;
    }
    memset_0(v50, 0, v49);
    memcpy_0(v8 + 1, v47, v46);
    v51 = v68;
    v52 = (char *)v8 + v46 + 4;
    if ( v21 )
    {
      memcpy_0(v52, (const void *)(*(_QWORD *)(v68 + 40) + 1LL), (unsigned int)(*(_DWORD *)(v68 + 32) - 1));
      v51 = v68;
      v52 = (char *)v8 + v46 + (unsigned int)(*(_DWORD *)(v68 + 32) - 1) + 4;
    }
    memcpy_0(v52, *(const void **)(v51 + 16), *(unsigned int *)(v51 + 8));
    v53 = (v67 ^ 1u) + 196618;
    *v8 = v67 != 0 ? 1447772997 : 1447314245;
    v54 = PkcsCreateKeyObject(&v69, a4, a2, v53);
    v11 = v54;
    if ( v54 >= 0 )
    {
      v6 = v69;
      v9 = v66;
      v55 = KspImportEccPrivateKey((__int64)v69, v8, v66, 2, 1);
      v11 = v55;
      if ( v55 >= 0 )
      {
        v30 = 0;
        goto LABEL_88;
      }
      DebugTraceError((unsigned int)v55, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3546);
    }
    else
    {
      DebugTraceError((unsigned int)v54, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3530);
      v6 = v69;
      v9 = v66;
    }
    v30 = 0;
    goto LABEL_99;
  }
  v28 = -2147483647;
  if ( v67 )
    v28 = 1073741825;
  OIDInfo = CryptFindOIDInfo(v28, v16, 0x40000003u);
  if ( !OIDInfo )
  {
    v11 = -2146893819;
    DebugTraceError(2148073477LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3338);
    v8 = 0;
    goto LABEL_35;
  }
  v30 = v23 + 2 * (v23 + 4);
  v31 = (_DWORD *)SafeAllocaAllocateFromHeap(v30);
  v7 = v31;
  if ( !v31 )
  {
    v11 = -2146893810;
    DebugTraceError(2148073486LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3347);
    v8 = 0;
    v9 = 0;
    goto LABEL_99;
  }
  memset_0(v31, 0, (unsigned int)(v23 + 2 * (v23 + 4)));
  v7[1] = v23;
  v32 = v7 + 2;
  v33 = v68;
  if ( v4 && (v34 = *(_QWORD *)(v68 + 40)) != 0 )
  {
    v35 = v4;
    v36 = (unsigned int)v23 - v4;
    memcpy_0((char *)v32 + v36, (const void *)(v34 + 1), v4);
    v37 = (char *)v7 + v23 + 8;
    memcpy_0(&v37[v36], (const void *)(v35 + *(_QWORD *)(v68 + 40) + 1LL), (unsigned int)v35);
    v33 = v68;
    v38 = &v37[(unsigned int)v23];
  }
  else
  {
    v38 = (char *)v32 + (unsigned int)(2 * v23);
  }
  memcpy_0(&v38[(unsigned int)v23 - Size], *(const void **)(v33 + 16), Size);
  if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDSA") )
  {
    if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDH") )
    {
      if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDSA_P256") )
      {
        if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDSA_P384") )
        {
          if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDSA_P521") )
          {
            if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDH_P256") )
            {
              if ( wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDH_P384") )
              {
                v39 = 0;
                if ( !wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDH_P521") )
                {
                  v39 = 196617;
                  *v7 = 910902085;
                }
              }
              else
              {
                v39 = 196616;
                *v7 = 877347653;
              }
            }
            else
            {
              v39 = 196615;
              *v7 = 843793221;
            }
          }
          else
          {
            v39 = 196614;
            *v7 = 911426373;
          }
        }
        else
        {
          v39 = 196613;
          *v7 = 877871941;
        }
      }
      else
      {
        v39 = 196612;
        *v7 = 844317509;
      }
    }
    else
    {
      v39 = 196618;
      *v7 = 1447772997;
    }
  }
  else
  {
    v39 = 196619;
    *v7 = 1447314245;
  }
  v40 = PkcsCreateKeyObject(&v69, a4, a2, v39);
  v11 = v40;
  if ( v40 < 0 )
  {
    DebugTraceError((unsigned int)v40, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3425);
    v6 = v69;
LABEL_65:
    v30 = v23 + 2 * (v23 + 4);
    v8 = 0;
    v9 = 0;
    goto LABEL_99;
  }
  v41 = wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDSA");
  v6 = v69;
  if ( !v41 || !wcsicmp(*(const wchar_t **)&OIDInfo[1].cbSize, L"ECDH") )
  {
    pwszName = (int *)OIDInfo->pwszName;
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)pwszName + v43) );
    dwFlags[0] = 2 * v43 + 2;
    v44 = SPCryptSetKeyProperty(a4, (__int64)v6, (__int64)L"ECCCurveName", pwszName, *(size_t *)dwFlags, 0x80000000);
    v11 = v44;
    if ( v44 )
    {
      DebugTraceError(v44, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3443);
      goto LABEL_65;
    }
  }
  v30 = v23 + 2 * (v23 + 4);
  v45 = KspImportEccPrivateKey((__int64)v6, v7, v30, 2, 0);
  v11 = v45;
  if ( v45 < 0 )
  {
    DebugTraceError((unsigned int)v45, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3460);
    v8 = 0;
    v9 = 0;
    goto LABEL_99;
  }
  v9 = 0;
LABEL_88:
  if ( Size_4 == 0xFFFFFF || (v56 = PkcsAddKeyUsageProperty(v6), v11 = v56, v56 >= 0) )
  {
    *a1 = v6;
    v6 = 0;
  }
  else
  {
    DebugTraceError((unsigned int)v56, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3567);
  }
  v7 = 0;
  v8 = 0;
LABEL_99:
  if ( pvStructInfo )
    ((void (*)(void))pDecodePara.pfnFree)();
  if ( v76 )
    ((void (*)(void))pDecodePara.pfnFree)();
  if ( v7 )
  {
    v58 = v30;
    v59 = v7;
    if ( v30 )
    {
      do
      {
        *v59++ = 0;
        --v58;
      }
      while ( v58 );
    }
    MSCryptFree(v7);
  }
  if ( v8 )
  {
    v60 = v9;
    v61 = v8;
    if ( v9 )
    {
      do
      {
        *v61++ = 0;
        --v60;
      }
      while ( v60 );
    }
    MSCryptFree(v8);
  }
  v62 = (_BYTE *)v68;
  if ( v68 )
  {
    v63 = v70[0];
    if ( v70[0] )
    {
      do
      {
        *v62++ = 0;
        --v63;
      }
      while ( v63 );
      v62 = (_BYTE *)v68;
    }
    MSCryptFree(v62);
  }
  if ( v6 )
    DeleteKeyObject(v6);
  return v11;
}

```

## disassembly

```asm
0x18004ae24  mov     rax, rsp
0x18004ae27  mov     [rax+20h], r9
0x18004ae2b  mov     [rax+10h], rdx
0x18004ae2f  mov     [rax+8], rcx
0x18004ae33  push    rbp
0x18004ae34  push    rbx
0x18004ae35  push    rsi
0x18004ae36  push    rdi
0x18004ae37  push    r12
0x18004ae39  push    r13
0x18004ae3b  push    r14
0x18004ae3d  push    r15
0x18004ae3f  lea     rbp, [rax-57h]
0x18004ae43  sub     rsp, 98h
0x18004ae4a  xor     r13d, r13d
0x18004ae4d  mov     rsi, r8
0x18004ae50  mov     edi, r13d
0x18004ae53  mov     [rbp+4Fh+var_88], r13
0x18004ae57  mov     r14d, r13d
0x18004ae5a  mov     [rbp+4Fh+var_78], r13d
0x18004ae5e  mov     r15d, r13d
0x18004ae61  mov     [rbp+4Fh+var_80], r13
0x18004ae65  mov     r12d, r13d
0x18004ae68  mov     [rbp+4Fh+var_8C], r13d
0x18004ae6c  mov     [rbp+4Fh+var_58], r13
0x18004ae70  mov     [rbp+4Fh+pcbStructInfo], r13d
0x18004ae74  mov     [rbp+4Fh+var_50], r13
0x18004ae78  mov     [rbp+4Fh+var_64], r13d
0x18004ae7c  cmp     [r8+28h], r13
0x18004ae80  jz      loc_18004B643
0x18004ae86  cmp     [r8+20h], r13d
0x18004ae8a  jz      loc_18004B643
0x18004ae90  mov     rcx, [r8+30h]
0x18004ae94  lea     rdx, [rbp+4Fh+var_8C]
0x18004ae98  call    _PkcsScanAttrList
0x18004ae9d  mov     ebx, eax
0x18004ae9f  test    eax, eax
0x18004aea1  jns     short loc_18004AEB0
0x18004aea3  mov     r9d, 0C7Bh
0x18004aea9  mov     ecx, eax
0x18004aeab  jmp     loc_18004B653
0x18004aeb0  mov     ecx, [rbp+4Fh+var_8C]
0x18004aeb3  mov     eax, 0FFFFFFh
0x18004aeb8  mov     r8, [rsi+18h]; pbEncoded
0x18004aebc  cmp     ecx, 0FFFFFFFFh
0x18004aebf  mov     rbx, r13
0x18004aec2  cmovz   ecx, eax
0x18004aec5  mov     eax, r13d
0x18004aec8  cmp     ecx, 2
0x18004aecb  mov     dword ptr [rbp+4Fh+Size+4], ecx
0x18004aece  setnz   al
0x18004aed1  mov     [rbp+4Fh+var_8C], eax
0x18004aed4  test    r8, r8
0x18004aed7  jz      loc_18004AF73
0x18004aedd  mov     r9d, [rsi+10h]; cbEncoded
0x18004aee1  test    r9d, r9d
0x18004aee4  jz      loc_18004AF73
0x18004aeea  lea     rax, [rbp+4Fh+pcbStructInfo]
0x18004aeee  mov     edx, 49h ; 'I'; lpszStructType
0x18004aef3  mov     [rsp+38h], rax; pcbStructInfo
0x18004aef8  lea     rax, [rbp+4Fh+var_58]
0x18004aefc  mov     [rsp+0D0h+pvStructInfo], rax; pvStructInfo
0x18004af01  lea     rax, pDecodePara
0x18004af08  mov     [rsp+0D0h+pDecodePara], rax; pDecodePara
0x18004af0d  lea     ecx, [rdx-48h]; dwCertEncodingType
0x18004af10  mov     [rsp+0D0h+dwFlags], 8004h; dwFlags
0x18004af18  call    cs:__imp_CryptDecodeObjectEx
0x18004af1f  nop     dword ptr [rax+rax+00h]
0x18004af24  test    eax, eax
0x18004af26  jz      short loc_18004AF31
0x18004af28  mov     rax, [rbp+4Fh+var_58]
0x18004af2c  mov     rbx, [rax]
0x18004af2f  jmp     short loc_18004AF73
0x18004af31  mov     r9d, [rsi+10h]; cbEncoded
0x18004af35  lea     rax, [rbp+4Fh+var_64]
0x18004af39  mov     r8, [rsi+18h]; pbEncoded
0x18004af3d  mov     edx, 55h ; 'U'; lpszStructType
0x18004af42  mov     [rsp+38h], rax; pcbStructInfo
0x18004af47  lea     rax, [rbp+4Fh+var_50]
0x18004af4b  mov     [rsp+0D0h+pvStructInfo], rax; pvStructInfo
0x18004af50  lea     rax, pDecodePara
0x18004af57  mov     [rsp+0D0h+pDecodePara], rax; pDecodePara
0x18004af5c  lea     ecx, [rdx-54h]; dwCertEncodingType
0x18004af5f  mov     [rsp+0D0h+dwFlags], 8004h; dwFlags
0x18004af67  call    cs:__imp_CryptDecodeObjectEx
0x18004af6e  nop     dword ptr [rax+rax+00h]
0x18004af73  mov     r9d, [rsi+20h]; cbEncoded
0x18004af77  lea     rax, [rbp+4Fh+var_78]
0x18004af7b  mov     r8, [rsi+28h]; pbEncoded
0x18004af7f  mov     edx, 52h ; 'R'; lpszStructType
0x18004af84  mov     [rsp+38h], rax; pcbStructInfo
0x18004af89  lea     rax, [rbp+4Fh+var_88]
0x18004af8d  mov     [rsp+0D0h+pvStructInfo], rax; pvStructInfo
0x18004af92  lea     rax, pDecodePara
0x18004af99  mov     [rsp+0D0h+pDecodePara], rax; pDecodePara
0x18004af9e  lea     ecx, [rdx-51h]; dwCertEncodingType
0x18004afa1  mov     [rsp+0D0h+dwFlags], 8001h; dwFlags
0x18004afa9  call    cs:__imp_CryptDecodeObjectEx
0x18004afb0  nop     dword ptr [rax+rax+00h]
0x18004afb5  test    eax, eax
0x18004afb7  jnz     short loc_18004AFE1
0x18004afb9  call    cs:__imp_GetLastError
0x18004afc0  nop     dword ptr [rax+rax+00h]
0x18004afc5  mov     ebx, eax
0x18004afc7  test    eax, eax
0x18004afc9  jle     short loc_18004AFD4
0x18004afcb  movzx   ebx, ax
0x18004afce  or      ebx, 80070000h
0x18004afd4  mov     r9d, 0CB8h
0x18004afda  mov     ecx, ebx
0x18004afdc  jmp     loc_18004B653
0x18004afe1  mov     rcx, [rbp+4Fh+var_88]
0x18004afe5  mov     rax, [rcx+28h]
0x18004afe9  test    rax, rax
0x18004afec  jz      short loc_18004B04B
0x18004afee  mov     r13d, [rcx+20h]
0x18004aff2  xor     r9d, r9d
0x18004aff5  test    r13d, r13d
0x18004aff8  jz      short loc_18004B048
0x18004affa  mov     dl, [rax]
0x18004affc  lea     eax, [rdx-4]
0x18004afff  test    al, 0FCh
0x18004b001  jnz     short loc_18004B008
0x18004b003  cmp     dl, 5
0x18004b006  jnz     short loc_18004B03B
0x18004b008  lea     eax, [r13-1]
0x18004b00c  test    al, 1
0x18004b00e  jz      short loc_18004B03B
0x18004b010  mov     r9d, 0CC9h
0x18004b016  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b01d  lea     rdx, aStatus_0; "status"
0x18004b024  mov     ecx, 80090005h
0x18004b029  mov     ebx, 80090005h
0x18004b02e  call    DebugTraceError
0x18004b033  xor     r13d, r13d
0x18004b036  jmp     loc_18004B666
0x18004b03b  dec     r13d
0x18004b03e  mov     esi, 1
0x18004b043  shr     r13d, 1
0x18004b046  jmp     short loc_18004B051
0x18004b048  xor     r13d, r13d
0x18004b04b  mov     esi, r13d
0x18004b04e  xor     r9d, r9d
0x18004b051  mov     edx, [rcx+8]
0x18004b054  mov     r12d, edx
0x18004b057  mov     rax, [rcx+18h]
0x18004b05b  cmp     edx, r13d
0x18004b05e  mov     dword ptr [rbp+4Fh+Size], edx
0x18004b061  cmovbe  r12d, r13d
0x18004b065  test    rax, rax
0x18004b068  jz      short loc_18004B0BC
0x18004b06a  test    rbx, rbx
0x18004b06d  jnz     short loc_18004B074
0x18004b06f  mov     rbx, rax
0x18004b072  jmp     short loc_18004B0C5
0x18004b074  mov     r8, rbx
0x18004b077  sub     r8, rax
0x18004b07a  movzx   edx, byte ptr [rax]
0x18004b07d  movzx   ecx, byte ptr [rax+r8]
0x18004b082  sub     edx, ecx
0x18004b084  jnz     short loc_18004B08D
0x18004b086  inc     rax
0x18004b089  test    ecx, ecx
0x18004b08b  jnz     short loc_18004B07A
0x18004b08d  test    edx, edx
0x18004b08f  jz      short loc_18004B0C5
0x18004b091  mov     r9d, 0CE1h
0x18004b097  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b09e  lea     rdx, aStatus_0; "status"
0x18004b0a5  mov     ecx, 80090005h
0x18004b0aa  mov     ebx, 80090005h
0x18004b0af  call    DebugTraceError
0x18004b0b4  mov     r12d, edi
0x18004b0b7  jmp     loc_18004B033
0x18004b0bc  test    rbx, rbx
0x18004b0bf  jz      loc_18004B43C
0x18004b0c5  mov     r8d, 40000003h; dwGroupId
0x18004b0cb  mov     rdx, rbx; pvKey
0x18004b0ce  mov     ecx, 80000001h
0x18004b0d3  cmp     [rbp+4Fh+var_8C], r9d
0x18004b0d7  jz      short loc_18004B0DD
0x18004b0d9  lea     ecx, [r8-2]; dwKeyType
0x18004b0dd  call    cs:__imp_CryptFindOIDInfo
0x18004b0e4  nop     dword ptr [rax+rax+00h]
0x18004b0e9  mov     r15, rax
0x18004b0ec  test    rax, rax
0x18004b0ef  jnz     short loc_18004B119
0x18004b0f1  mov     r9d, 0D0Ah
0x18004b0f7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b0fe  lea     rdx, aStatus_0; "status"
0x18004b105  mov     ecx, 80090005h
0x18004b10a  mov     ebx, 80090005h
0x18004b10f  call    DebugTraceError
0x18004b114  mov     r15, rdi
0x18004b117  jmp     short loc_18004B0B4
0x18004b119  lea     esi, [r12+4]
0x18004b11e  lea     esi, [r12+rsi*2]
0x18004b122  mov     ecx, esi
0x18004b124  mov     [rbp+4Fh+arg_10], esi
0x18004b127  mov     ebx, esi
0x18004b129  call    SafeAllocaAllocateFromHeap
0x18004b12e  mov     r14, rax
0x18004b131  test    rax, rax
0x18004b134  jnz     short loc_18004B167
0x18004b136  mov     r9d, 0D13h
0x18004b13c  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b143  lea     rdx, aStatus_0; "status"
0x18004b14a  mov     ecx, 8009000Eh
0x18004b14f  mov     ebx, 8009000Eh
0x18004b154  call    DebugTraceError
0x18004b159  xor     r13d, r13d
0x18004b15c  mov     r15, rdi
0x18004b15f  mov     r12d, edi
0x18004b162  jmp     loc_18004B668
0x18004b167  mov     r8, rbx; Size
0x18004b16a  xor     edx, edx; Val
0x18004b16c  mov     rcx, r14; void *
0x18004b16f  call    memset_0
0x18004b174  mov     [r14+4], r12d
0x18004b178  lea     r8, [r14+8]
0x18004b17c  mov     rdx, [rbp+4Fh+var_88]
0x18004b180  test    r13d, r13d
0x18004b183  jz      short loc_18004B1D7
0x18004b185  mov     rcx, [rdx+28h]
0x18004b189  test    rcx, rcx
0x18004b18c  jz      short loc_18004B1D7
0x18004b18e  mov     eax, r12d
0x18004b191  mov     esi, r13d
0x18004b194  sub     eax, r13d
0x18004b197  lea     rdx, [rcx+1]; Src
0x18004b19b  mov     edi, eax
0x18004b19d  lea     rcx, [rax+r8]; void *
0x18004b1a1  mov     r8d, r13d; Size
0x18004b1a4  call    memcpy_0
0x18004b1a9  mov     rax, [rbp+4Fh+var_88]
0x18004b1ad  lea     r13, [r12+8]
0x18004b1b2  add     r13, r14
0x18004b1b5  mov     ebx, r12d
0x18004b1b8  mov     r8d, esi; Size
0x18004b1bb  mov     rdx, [rax+28h]
0x18004b1bf  inc     rdx
0x18004b1c2  lea     rcx, [rdi+r13]; void *
0x18004b1c6  add     rdx, rsi; Src
0x18004b1c9  call    memcpy_0
0x18004b1ce  mov     rdx, [rbp+4Fh+var_88]
0x18004b1d2  add     r13, rbx
0x18004b1d5  jmp     short loc_18004B1DE
0x18004b1d7  lea     r13d, [r12+r12]
0x18004b1db  add     r13, r8
0x18004b1de  mov     eax, dword ptr [rbp+4Fh+Size]
0x18004b1e1  mov     rdx, [rdx+10h]; Src
0x18004b1e5  sub     r12d, eax
0x18004b1e8  mov     ecx, r12d
0x18004b1eb  mov     r8d, eax; Size
0x18004b1ee  add     rcx, r13; void *
0x18004b1f1  call    memcpy_0
0x18004b1f6  mov     rcx, [r15+30h]; String1
0x18004b1fa  lea     rdx, aEcdsa; "ECDSA"
0x18004b201  call    _wcsicmp
0x18004b206  xor     r13d, r13d
0x18004b209  test    eax, eax
0x18004b20b  jnz     short loc_18004B21E
0x18004b20d  mov     ebx, 3000Bh
0x18004b212  mov     dword ptr [r14], 56444345h
0x18004b219  jmp     loc_18004B316
0x18004b21e  mov     rcx, [r15+30h]; String1
0x18004b222  lea     rdx, aEcdh; "ECDH"
0x18004b229  call    _wcsicmp
0x18004b22e  test    eax, eax
0x18004b230  jnz     short loc_18004B243
0x18004b232  mov     ebx, 3000Ah
0x18004b237  mov     dword ptr [r14], 564B4345h
0x18004b23e  jmp     loc_18004B316
0x18004b243  mov     rcx, [r15+30h]; String1
0x18004b247  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x18004b24e  call    _wcsicmp
0x18004b253  test    eax, eax
0x18004b255  jnz     short loc_18004B268
0x18004b257  mov     ebx, 30004h
0x18004b25c  mov     dword ptr [r14], 32534345h
0x18004b263  jmp     loc_18004B316
0x18004b268  mov     rcx, [r15+30h]; String1
0x18004b26c  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x18004b273  call    _wcsicmp
0x18004b278  test    eax, eax
0x18004b27a  jnz     short loc_18004B28D
0x18004b27c  mov     ebx, 30005h
0x18004b281  mov     dword ptr [r14], 34534345h
0x18004b288  jmp     loc_18004B316
0x18004b28d  mov     rcx, [r15+30h]; String1
0x18004b291  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x18004b298  call    _wcsicmp
0x18004b29d  test    eax, eax
0x18004b29f  jnz     short loc_18004B2AF
0x18004b2a1  mov     ebx, 30006h
0x18004b2a6  mov     dword ptr [r14], 36534345h
0x18004b2ad  jmp     short loc_18004B316
0x18004b2af  mov     rcx, [r15+30h]; String1
0x18004b2b3  lea     rdx, aEcdhP256; "ECDH_P256"
0x18004b2ba  call    _wcsicmp
  ... truncated ...
```
