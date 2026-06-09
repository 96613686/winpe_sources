# CConnection::CreateLoginRecord(void *,_LOGINSTRUCT const *,CExtByteBuffer *)

- ea: `0x100462b10`
- end: `0x100463821`
- name: `?CreateLoginRecord@CConnection@@AEAAJPEAXPEBU_LOGINSTRUCT@@PEAVCExtByteBuffer@@@Z`
- size: `3345`
- prototype: `__int64 __fastcall(CConnection *__hidden this, void *, const struct _LOGINSTRUCT *, struct CExtByteBuffer *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1004642f0`

## callees

- `0x100461cf4`
- `0x100462130`
- `0x100462b10`
- `0x100463828`
- `0x100464e84`
- `0x100465518`
- `0x10046562c`
- `0x10046944c`
- `0x100469868`
- `0x10046ce3c`
- `0x10048babc`
- `0x100546a24`
- `0x100546aa8`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x100462b97`
- `KERNEL32!GetCurrentProcessId` at `0x100462b97`
- `KERNEL32!GetLastError` at `0x100462d27`
- `KERNEL32!GetLastError` at `0x100462d98`
- `KERNEL32!GetLastError` at `0x1004632d4`
- `KERNEL32!GetLastError` at `0x100462d27`
- `KERNEL32!GetLastError` at `0x100462d98`
- `KERNEL32!GetLastError` at `0x1004632d4`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100462ced`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100463051`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100463295`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100462ced`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100463051`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100463295`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CConnection::CreateLoginRecord(
        CTdsParser **this,
        void *a2,
        const struct _LOGINSTRUCT *a3,
        struct CExtByteBuffer *a4)
{
  __int64 v8; // rdi
  char v9; // dl
  char v10; // cl
  char v11; // dl
  int v12; // eax
  __int64 v13; // r9
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r8
  _WORD *v18; // rax
  __int64 v19; // rdi
  DWORD LastError; // eax
  wchar_t *v21; // r8
  __int64 v22; // rdx
  CTdsParser *v23; // rdi
  _BYTE *v24; // rcx
  __int64 i; // rdx
  __int64 v26; // r8
  const unsigned __int16 *v27; // r9
  char v28; // cl
  __int64 v29; // rcx
  unsigned __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdi
  __int64 v34; // r13
  char v35; // cl
  __int64 v36; // r9
  char v37; // al
  unsigned int v38; // ecx
  CTdsParser *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // r9
  BOOL v42; // edx
  int v43; // ecx
  __int64 v44; // rdx
  DWORD v45; // eax
  _BYTE *v46; // rcx
  __int64 j; // rdx
  CSessionRecoveryFeatureExtension *v48; // rax
  struct CFeatureExtension *v49; // rax
  CFeatureExtensionList *v50; // rbx
  __int64 v51; // rax
  char v52; // cl
  __int64 v53; // rax
  unsigned __int64 v54; // rdi
  __int64 v55; // rcx
  int v56; // edx
  __int64 v57; // rax
  __int64 v58; // rax
  char v59; // cl
  __int64 v60; // rax
  __int64 v61; // rax
  char v62; // cl
  __int64 v63; // rdx
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rdi
  __int64 v67; // [rsp+20h] [rbp-E0h]
  int v68[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v69[4]; // [rsp+48h] [rbp-B8h] BYREF
  int Source; // [rsp+4Ch] [rbp-B4h] BYREF
  int v71; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v72; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Destination[144]; // [rsp+60h] [rbp-A0h] BYREF

  v72 = -2;
  Source = 0;
  v8 = *((_QWORD *)a4 + 4);
  *((_QWORD *)a4 + 1) = 94;
  memset_0((void *)v8, 0, 0x5Eu);
  *(_DWORD *)(v8 + 4) = *((unsigned __int16 *)this + 1937) | (*((unsigned __int16 *)this + 1936) << 16);
  *(_DWORD *)(v8 + 8) = *((_DWORD *)a3 + 34);
  *(_DWORD *)(v8 + 12) = 117440512;
  *(_DWORD *)(v8 + 16) = GetCurrentProcessId();
  *(_DWORD *)(v8 + 20) = 0;
  v9 = *(_BYTE *)(v8 + 24) & 0xFC;
  *(_BYTE *)(v8 + 24) = v9;
  *(_BYTE *)(v8 + 24) = v9 & 3 | (*((_DWORD *)a3 + 46) != 0 ? 0x10 : 0) | 0xE0;
  v10 = *(_BYTE *)(v8 + 26) & 0xF0;
  *(_BYTE *)(v8 + 26) = v10;
  v11 = *(_BYTE *)(v8 + 25) & 0xFA | 1;
  *(_BYTE *)(v8 + 25) = v11;
  *(_BYTE *)(v8 + 26) = v10 & 0xDF | (*((_DWORD *)a3 + 59) != 1 ? 0 : 0x20);
  *(_BYTE *)(v8 + 25) = v11 | 2;
  if ( !SystemLocale::CurrentTimeZoneBias((SystemLocale *)v69, v68, 0) )
    *(_DWORD *)(v8 + 28) = v68[0];
  *(_DWORD *)(v8 + 32) = *((_DWORD *)a3 + 49);
  v12 = CConnection::AddToLoginRec(
          (CConnection *)this,
          a4,
          (struct OFFLEN *)(v8 + 36),
          *((const unsigned __int16 **)a3 + 7));
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v15 = 1726473;
LABEL_6:
      v16 = (unsigned int)v12;
LABEL_7:
      _mm_lfence();
      bidTraceHR(0, v15, v16, v13);
      return v14;
    }
    return v14;
  }
  _mm_lfence();
  v17 = *((_QWORD *)a4 + 4);
  if ( !*((_BYTE *)a3 + 140) && !*((_QWORD *)a3 + 42) && !**((_WORD **)a3 + 33)
    || (v18 = (_WORD *)*((_QWORD *)a3 + 10)) != 0 && *v18 )
  {
    v12 = CConnection::AddToLoginRec(
            (CConnection *)this,
            a4,
            (struct OFFLEN *)(v17 + 40),
            *((const unsigned __int16 **)a3 + 4));
    v14 = v12;
    if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v14;
      v15 = 1733641;
      goto LABEL_6;
    }
    _mm_lfence();
    v19 = *((_QWORD *)a4 + 4);
    if ( g_pfnCryptUnprotectMemory )
    {
      memcpy_s(Destination, 0x120u, *((const void *const *)a3 + 5), 0x120u);
      if ( !(unsigned int)((__int64 (__fastcall *)(unsigned __int16 *, __int64, _QWORD))g_pfnCryptUnprotectMemory)(
                            Destination,
                            288,
                            0) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E6B88[0] )
        {
          LastError = GetLastError();
          bidTraceW(0, 1757184, off_1005E6B88[0], LastError);
        }
        v14 = -2147467259;
        if ( (bidGblFlags & 2) == 0 || !off_1005E6B90[0] )
          goto LABEL_25;
        v21 = off_1005E6B90[0];
        v22 = 1759232;
LABEL_24:
        HIDWORD(v67) = HIDWORD(a2);
        bidTraceW(0, v22, v21, this);
LABEL_25:
        v23 = this[486];
        LODWORD(v67) = GetLastError();
        CTdsParser::PostFormattedParserErrorEx(v23, a2, 0x9E28u, 0x80004005, v67);
        return v14;
      }
      v14 = CConnection::AddToLoginRec((CConnection *)this, a4, (struct OFFLEN *)(v19 + 44), Destination);
      memset(Destination, 0, sizeof(Destination));
      if ( (v14 & 0x80000000) != 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v14;
        v16 = v14;
        v15 = 1770505;
        goto LABEL_7;
      }
    }
    else
    {
      v12 = CConnection::AddToLoginRec(
              (CConnection *)this,
              a4,
              (struct OFFLEN *)(v19 + 44),
              *((const unsigned __int16 **)a3 + 5));
      v14 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v14;
        v15 = 1775625;
        goto LABEL_6;
      }
    }
    _mm_lfence();
    v17 = *((_QWORD *)a4 + 4);
    v24 = (_BYTE *)(v17 + *(unsigned __int16 *)(v17 + 44));
    for ( i = 2LL * *(unsigned __int16 *)(v17 + 46); i; --i )
    {
      *v24 = __ROL1__(*v24, 4) ^ 0xA5;
      ++v24;
    }
  }
  v12 = CConnection::AddToLoginRec(
          (CConnection *)this,
          a4,
          (struct OFFLEN *)(v17 + 48),
          *((const unsigned __int16 **)a3 + 12));
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v15 = 1785865;
    goto LABEL_6;
  }
  _mm_lfence();
  v26 = *((_QWORD *)a4 + 4);
  v27 = (const unsigned __int16 *)*((_QWORD *)a3 + 10);
  if ( v27 && *v27 )
  {
    v28 = *(_BYTE *)(v26 + 25) & 0x8F | 0x20;
  }
  else
  {
    v27 = (const unsigned __int16 *)*((_QWORD *)a3 + 11);
    if ( v27 && *v27 )
    {
      v28 = *(_BYTE *)(v26 + 25) & 0x8F | 0x30;
    }
    else
    {
      v27 = (const unsigned __int16 *)*((_QWORD *)a3 + 9);
      v28 = *(_BYTE *)(v26 + 25) & 0x8F | (*((_BYTE *)a3 + 373) != 0 ? 0x30 : 0);
    }
  }
  *(_BYTE *)(v26 + 25) = v28;
  if ( !v27 || (v28 & 0x70) != 0 )
  {
    v31 = CConnection::AddToLoginRec((CConnection *)this, a4, (struct OFFLEN *)(v26 + 52), v27);
  }
  else
  {
    v29 = -1;
    v30 = -1;
    do
      ++v30;
    while ( v27[v30] );
    if ( v30 >= 0x80 )
    {
      LOWORD(v29) = 128;
    }
    else
    {
      _mm_lfence();
      do
        ++v29;
      while ( v27[v29] );
    }
    *(_WORD *)(v26 + 52) = *((_WORD *)a4 + 4);
    *(_WORD *)(v26 + 54) = v29;
    v31 = CExtByteBuffer::WriteIntoExtBuffer(a4, v27, 2LL * (unsigned __int16)v29);
  }
  v14 = v31;
  if ( v31 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v16 = (unsigned int)v31;
    v15 = 1818633;
    goto LABEL_7;
  }
  _mm_lfence();
  v32 = *((_QWORD *)a4 + 4);
  *(_WORD *)(v32 + 56) = *((_WORD *)a4 + 4);
  *(_WORD *)(v32 + 58) = 4;
  CExtByteBuffer::WriteIntoExtBuffer(a4, &Source, 4u);
  v12 = CConnection::AddToLoginRec(
          (CConnection *)this,
          a4,
          (struct OFFLEN *)(*((_QWORD *)a4 + 4) + 60LL),
          *((const unsigned __int16 **)a3 + 13));
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v15 = 1830921;
    goto LABEL_6;
  }
  _mm_lfence();
  v12 = CConnection::AddToLoginRec(
          (CConnection *)this,
          a4,
          (struct OFFLEN *)(*((_QWORD *)a4 + 4) + 64LL),
          *((const unsigned __int16 **)a3 + 3));
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v15 = 1835017;
    goto LABEL_6;
  }
  _mm_lfence();
  v12 = CConnection::AddToLoginRec(
          (CConnection *)this,
          a4,
          (struct OFFLEN *)(*((_QWORD *)a4 + 4) + 68LL),
          *((const unsigned __int16 **)a3 + 2));
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v15 = 1839113;
    goto LABEL_6;
  }
  _mm_lfence();
  v33 = *((_QWORD *)a4 + 4);
  memcpy_s((void *const)(v33 + 72), 6u, (char *)a3 + 200, 6u);
  v12 = CConnection::AddToLoginRec(
          (CConnection *)this,
          a4,
          (struct OFFLEN *)(v33 + 82),
          *((const unsigned __int16 **)a3 + 14));
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v14;
    v15 = 1847305;
    goto LABEL_6;
  }
  _mm_lfence();
  v34 = *((_QWORD *)a4 + 4);
  v35 = *((_BYTE *)a3 + 140);
  if ( (unsigned __int8)(v35 - 1) > 1u || *((_DWORD *)this + 114) && (v35 != 1 || *((_BYTE *)a3 + 141)) )
  {
    *(_BYTE *)(v34 + 25) &= ~0x80u;
    if ( *((_BYTE *)a3 + 140) )
    {
      v40 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 64);
      *(_QWORD *)v68 = v40;
      if ( !v40 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v44 = 1908745;
          return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
        }
        return (unsigned int)-2147024882;
      }
      v42 = (unsigned __int8)(*((_BYTE *)a3 + 140) - 1) <= 1u;
      v43 = *((_DWORD *)this + 114);
      *(_BYTE *)(v40 + 8) = 2;
      *(_DWORD *)(v40 + 12) = 0;
      *(_BYTE *)(v40 + 16) = 0;
      *(_QWORD *)v40 = &CFederatedAuthenticationFeatureExtension::`vftable';
      *(_BYTE *)(v40 + 24) = 2;
      *(_QWORD *)(v40 + 32) = 0;
      *(_DWORD *)(v40 + 40) = v42 + 1;
      *(_QWORD *)(v40 + 48) = 0;
      *(_DWORD *)(v40 + 56) = v43;
      CFeatureExtensionList::push_front((CFeatureExtensionList *)(this + 487), (struct CFeatureExtension *)v40);
    }
    else if ( *((_QWORD *)a3 + 6) )
    {
      *(_BYTE *)(v34 + 27) |= 1u;
      *((_DWORD *)this + 107) = 1;
      memcpy_s(Destination, 0x120u, *((const void *const *)a3 + 6), 0x120u);
      if ( g_pfnCryptUnprotectMemory && !g_pfnCryptUnprotectMemory(Destination, 0x120u, 0) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E6BA0[0] )
        {
          v45 = GetLastError();
          bidTraceW(0, 1936384, off_1005E6BA0[0], v45);
        }
        v14 = -2147467259;
        if ( (bidGblFlags & 2) == 0 || !off_1005E6BA8[0] )
          goto LABEL_25;
        v21 = off_1005E6BA8[0];
        v22 = 1938432;
        goto LABEL_24;
      }
      v14 = CConnection::AddToLoginRec((CConnection *)this, a4, (struct OFFLEN *)(v34 + 86), Destination);
      memset(Destination, 0, sizeof(Destination));
      if ( (v14 & 0x80000000) != 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v14;
        v16 = v14;
        v15 = 1950729;
        goto LABEL_7;
      }
      _mm_lfence();
      v34 = *((_QWORD *)a4 + 4);
      v46 = (_BYTE *)(v34 + *(unsigned __int16 *)(v34 + 86));
      for ( j = 2LL * *(unsigned __int16 *)(v34 + 88); j; --j )
      {
        *v46 = __ROL1__(*v46, 4) ^ 0xA5;
        ++v46;
      }
    }
  }
  else
  {
    v71 = 0;
    *(_BYTE *)(v34 + 25) |= 0x80u;
    v14 = CConnection::GenClientContext((CConnection *)this, 0, 0, &v71);
    _mm_lfence();
    if ( (v14 & 0x80000000) != 0 )
    {
      v37 = bidGblFlags;
      if ( (bidGblFlags & 2) != 0 )
      {
        bidTraceHR(0, 1866761, v14, v36);
        v37 = bidGblFlags;
      }
      if ( (v37 & 2) != 0 && off_1005E6B98[0] )
        bidTraceW(0, 1867776, off_1005E6B98[0], this);
      CTdsParser::PostSNIErrorEx(this[486], (struct CConnection *)this, *((void **)this[3] + 14), 0x9D25u);
      return v14;
    }
    v38 = *((_DWORD *)this + 24);
    v39 = this[11];
    *(_WORD *)(v34 + 78) = *((_WORD *)a4 + 4);
    *(_WORD *)(v34 + 80) = v38;
    v12 = CExtByteBuffer::WriteIntoExtBuffer(a4, v39, v38);
    v14 = v12;
    if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v14;
      v15 = 1884169;
      goto LABEL_6;
    }
    _mm_lfence();
    v34 = *((_QWORD *)a4 + 4);
    if ( *((_DWORD *)this + 24) > 0xFFFFu )
    {
      *(_WORD *)(v34 + 80) = -1;
      *(_DWORD *)(v34 + 90) = *((_DWORD *)this + 24);
    }
  }
  if ( *((_DWORD *)a3 + 62) )
  {
    v48 = (CSessionRecoveryFeatureExtension *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(
                                                g_pMO,
                                                40);
    *(_QWORD *)v68 = v48;
    if ( v48 )
      v49 = CSessionRecoveryFeatureExtension::CSessionRecoveryFeatureExtension(v48, a3, a2);
    else
      v49 = 0;
    if ( !v49 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v44 = 1967113;
        return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
      }
      return (unsigned int)-2147024882;
    }
    v50 = (CFeatureExtensionList *)(this + 487);
    CFeatureExtensionList::push_front((CFeatureExtensionList *)(this + 487), v49);
  }
  else
  {
    v50 = (CFeatureExtensionList *)(this + 487);
  }
  if ( *((_BYTE *)a3 + 256) )
  {
    v51 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 32);
    *(_QWORD *)v68 = v51;
    if ( !v51 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v44 = 1976329;
        return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
      }
      return (unsigned int)-2147024882;
    }
    v52 = *((_BYTE *)a3 + 256);
    *(_BYTE *)(v51 + 8) = 4;
    *(_DWORD *)(v51 + 12) = 0;
    *(_BYTE *)(v51 + 16) = 0;
    *(_QWORD *)v51 = &CColumnEncryptionFeatureExtension::`vftable';
    *(_BYTE *)(v51 + 24) = v52;
    CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v51);
  }
  if ( *((_QWORD *)a3 + 42) )
  {
    v53 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 64);
    *(_QWORD *)v68 = v53;
    if ( !v53 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v44 = 1986569;
        return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
      }
      return (unsigned int)-2147024882;
    }
    v54 = ((unsigned __int64)this + 460) & -(__int64)(*((_DWORD *)this + 123) != 0);
    v55 = *((_QWORD *)a3 + 42);
    v56 = *((_DWORD *)this + 114);
    *(_BYTE *)(v53 + 8) = 2;
    *(_DWORD *)(v53 + 12) = 0;
    *(_BYTE *)(v53 + 16) = 0;
    *(_QWORD *)v53 = &CFederatedAuthenticationFeatureExtension::`vftable';
    *(_BYTE *)(v53 + 24) = 1;
    *(_QWORD *)(v53 + 32) = v55;
    *(_DWORD *)(v53 + 40) = 0;
    *(_QWORD *)(v53 + 48) = v54;
    *(_DWORD *)(v53 + 56) = v56;
    CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v53);
  }
  v57 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 24);
  *(_QWORD *)v68 = v57;
  if ( !v57 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v44 = 1992713;
      return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
    }
    return (unsigned int)-2147024882;
  }
  *(_BYTE *)(v57 + 8) = 10;
  *(_DWORD *)(v57 + 12) = 0;
  *(_BYTE *)(v57 + 16) = 0;
  *(_QWORD *)v57 = &SupportUTF8FeatureExtension::`vftable';
  CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v57);
  v58 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 32);
  *(_QWORD *)v68 = v58;
  if ( !v58 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v44 = 1999881;
      return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
    }
    return (unsigned int)-2147024882;
  }
  v59 = *((_BYTE *)a3 + 372);
  *(_BYTE *)(v58 + 8) = 9;
  *(_DWORD *)(v58 + 12) = 0;
  *(_BYTE *)(v58 + 16) = 0;
  *(_QWORD *)v58 = &CColumnEncryptionFeatureExtension::`vftable';
  *(_BYTE *)(v58 + 24) = v59;
  CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v58);
  v60 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 24);
  *(_QWORD *)v68 = v60;
  if ( !v60 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v44 = 2007049;
      return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
    }
    return (unsigned int)-2147024882;
  }
  *(_BYTE *)(v60 + 8) = 11;
  *(_DWORD *)(v60 + 12) = 0;
  *(_BYTE *)(v60 + 16) = 0;
  *(_QWORD *)v60 = &DNSCacheExtension::`vftable';
  CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v60);
  if ( *((_BYTE *)a3 + 396) )
  {
    v61 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 32);
    *(_QWORD *)v68 = v61;
    if ( !v61 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v44 = 2015241;
        return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
      }
      return (unsigned int)-2147024882;
    }
    v62 = *((_BYTE *)a3 + 396);
    *(_BYTE *)(v61 + 8) = 14;
    *(_DWORD *)(v61 + 12) = 0;
    *(_BYTE *)(v61 + 16) = 0;
    *(_QWORD *)v61 = &VectorTypeFeatureExtension::`vftable';
    if ( v62 == 1 )
      *(_BYTE *)(v61 + 24) = 1;
    CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v61);
  }
  if ( (dword_1005D9398 & 1) == 0 )
  {
    dword_1005D9398 |= 1u;
    UserAgent::UserAgent((UserAgent *)qword_1005D9050);
  }
  v63 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 544);
  *(_QWORD *)v68 = v63;
  if ( !v63 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v44 = 2025481;
      return (unsigned int)bidTraceHR(0, v44, 2147942414LL, v41);
    }
    return (unsigned int)-2147024882;
  }
  v64 = qword_1005D9390;
  *(_BYTE *)(v63 + 8) = 16;
  *(_DWORD *)(v63 + 12) = 0;
  *(_BYTE *)(v63 + 16) = 0;
  *(_QWORD *)v63 = &UserAgentFeatureExtension::`vftable';
  *(_QWORD *)(v63 + 536) = 0;
  if ( v64 )
  {
    if ( v64 > 0x100 )
      v64 = 256;
    *(_QWORD *)(v63 + 536) = v64;
    v65 = 0;
    do
    {
      *(_WORD *)((char *)&qword_1005D9050[43] + 2 * v65 + v63 - (_QWORD)qword_1005D9190) = *((_WORD *)&qword_1005D9050[40]
                                                                                           + v65);
      ++v65;
    }
    while ( v65 < *(_QWORD *)(v63 + 536) );
  }
  CFeatureExtensionList::push_front(v50, (struct CFeatureExtension *)v63);
  *(_BYTE *)(v34 + 27) |= 0x10u;
  *(_DWORD *)(*(unsigned __int16 *)(v34 + 56) + *((_QWORD *)a4 + 4)) = *((_DWORD *)a4 + 2);
  v12 = SerializeFeatureExtensions(v50, a4);
  v14 = v12;
  if ( v12 >= 0 )
  {
    _mm_lfence();
    **((_DWORD **)a4 + 4) = *((_DWORD *)a4 + 2);
    return v14;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v15 = 2040841;
    goto LABEL_6;
  }
  return v14;
}

```

## disassembly

```asm
0x100462b10  push    rbp
0x100462b12  push    rbx
0x100462b13  push    rsi
0x100462b14  push    rdi
0x100462b15  push    r12
0x100462b17  push    r13
0x100462b19  push    r14
0x100462b1b  push    r15
0x100462b1d  lea     rbp, [rsp-98h]
0x100462b25  sub     rsp, 198h
0x100462b2c  mov     [rsp+1D0h+var_178], 0FFFFFFFFFFFFFFFEh
0x100462b35  mov     rax, cs:__security_cookie
0x100462b3c  xor     rax, rsp
0x100462b3f  mov     [rbp+0D0h+var_50], rax
0x100462b46  mov     r15, r9
0x100462b49  mov     r14, r8
0x100462b4c  mov     r12, rdx
0x100462b4f  mov     rsi, rcx
0x100462b52  xor     r13d, r13d
0x100462b55  mov     [rsp+1D0h+Source], r13d
0x100462b5a  mov     rdi, [r9+20h]
0x100462b5e  lea     r8d, [r13+5Eh]; Size
0x100462b62  mov     [r9+8], r8
0x100462b66  xor     edx, edx; Val
0x100462b68  mov     rcx, rdi; void *
0x100462b6b  call    memset_0
0x100462b70  movzx   ecx, word ptr [rsi+0F20h]
0x100462b77  shl     ecx, 10h
0x100462b7a  movzx   eax, word ptr [rsi+0F22h]
0x100462b81  or      ecx, eax
0x100462b83  mov     [rdi+4], ecx
0x100462b86  mov     eax, [r14+88h]
0x100462b8d  mov     [rdi+8], eax
0x100462b90  mov     dword ptr [rdi+0Ch], 7000000h
0x100462b97  call    cs:__imp_GetCurrentProcessId
0x100462b9d  mov     [rdi+10h], eax
0x100462ba0  mov     [rdi+14h], r13d
0x100462ba4  mov     dl, [rdi+18h]
0x100462ba7  and     dl, 0FCh
0x100462baa  mov     [rdi+18h], dl
0x100462bad  mov     eax, [r14+0B8h]
0x100462bb4  neg     eax
0x100462bb6  sbb     cl, cl
0x100462bb8  and     cl, 10h
0x100462bbb  and     dl, 3
0x100462bbe  or      cl, dl
0x100462bc0  or      cl, 0E0h
0x100462bc3  mov     [rdi+18h], cl
0x100462bc6  mov     cl, [rdi+1Ah]
0x100462bc9  and     cl, 0F0h
0x100462bcc  mov     [rdi+1Ah], cl
0x100462bcf  mov     dl, [rdi+19h]
0x100462bd2  and     dl, 0FBh
0x100462bd5  or      dl, 1
0x100462bd8  mov     [rdi+19h], dl
0x100462bdb  cmp     dword ptr [r14+0ECh], 1
0x100462be3  setnz   al
0x100462be6  dec     al
0x100462be8  and     al, 20h
0x100462bea  and     cl, 0DFh
0x100462bed  or      al, cl
0x100462bef  mov     [rdi+1Ah], al
0x100462bf2  or      dl, 2
0x100462bf5  mov     [rdi+19h], dl
0x100462bf8  xor     r8d, r8d; unsigned int *
0x100462bfb  lea     rdx, [rsp+1D0h+var_190]; int *
0x100462c00  lea     rcx, [rsp+1D0h+var_188]; this
0x100462c05  call    ?CurrentTimeZoneBias@SystemLocale@@QEBAKPEAJPEAK@Z; SystemLocale::CurrentTimeZoneBias(long *,ulong *)
0x100462c0a  test    eax, eax
0x100462c0c  jnz     short loc_100462C15
0x100462c0e  mov     eax, [rsp+1D0h+var_190]
0x100462c12  mov     [rdi+1Ch], eax
0x100462c15  mov     eax, [r14+0C4h]
0x100462c1c  mov     [rdi+20h], eax
0x100462c1f  lea     r8, [rdi+24h]; struct OFFLEN *
0x100462c23  mov     r9, [r14+38h]; unsigned __int16 *
0x100462c27  mov     rdx, r15; struct CExtByteBuffer *
0x100462c2a  mov     rcx, rsi; this
0x100462c2d  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x100462c32  mov     ebx, eax
0x100462c34  test    eax, eax
0x100462c36  jns     short loc_100462C5C
0x100462c38  test    byte ptr cs:_bidGblFlags, 2
0x100462c3f  jz      loc_1004637FC
0x100462c45  mov     edx, 1A5809h
0x100462c4a  mov     r8d, eax
0x100462c4d  lfence
0x100462c50  xor     ecx, ecx
0x100462c52  call    _bidTraceHR
0x100462c57  jmp     loc_1004637FC
0x100462c5c  lfence
0x100462c5f  mov     r8, [r15+20h]
0x100462c63  cmp     [r14+8Ch], r13b
0x100462c6a  jnz     short loc_100462C82
0x100462c6c  cmp     [r14+150h], r13
0x100462c73  jnz     short loc_100462C82
0x100462c75  mov     rax, [r14+108h]
0x100462c7c  cmp     [rax], r13w
0x100462c80  jz      short loc_100462C99
0x100462c82  mov     rax, [r14+50h]
0x100462c86  test    rax, rax
0x100462c89  jz      loc_100462E58
0x100462c8f  cmp     [rax], r13w
0x100462c93  jz      loc_100462E58
0x100462c99  add     r8, 28h ; '('; struct OFFLEN *
0x100462c9d  mov     r9, [r14+20h]; unsigned __int16 *
0x100462ca1  mov     rdx, r15; struct CExtByteBuffer *
0x100462ca4  mov     rcx, rsi; this
0x100462ca7  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x100462cac  mov     ebx, eax
0x100462cae  test    eax, eax
0x100462cb0  jns     short loc_100462CC6
0x100462cb2  test    byte ptr cs:_bidGblFlags, 2
0x100462cb9  jz      loc_1004637FC
0x100462cbf  mov     edx, 1A7409h
0x100462cc4  jmp     short loc_100462C4A
0x100462cc6  lfence
0x100462cc9  mov     rdi, [r15+20h]
0x100462ccd  cmp     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, r13; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x100462cd4  jz      loc_100462DFD
0x100462cda  mov     ebx, 120h
0x100462cdf  mov     r9d, ebx; SourceSize
0x100462ce2  mov     r8, [r14+28h]; Source
0x100462ce6  mov     edx, ebx; DestinationSize
0x100462ce8  lea     rcx, [rsp+1D0h+Destination]; Destination
0x100462ced  call    cs:__imp_memcpy_s
0x100462cf3  xor     r8d, r8d
0x100462cf6  mov     edx, ebx
0x100462cf8  lea     rcx, [rsp+1D0h+Destination]
0x100462cfd  mov     rax, cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x100462d04  call    cs:__guard_dispatch_icall_fptr
0x100462d0a  test    eax, eax
0x100462d0c  jnz     loc_100462DBB
0x100462d12  test    byte ptr cs:_bidGblFlags, 2
0x100462d19  jz      short loc_100462D43
0x100462d1b  mov     rax, cs:off_1005E6B88; "<CConnection::CreateLoginRecord|ERR|SNA"...
0x100462d22  test    rax, rax
0x100462d25  jz      short loc_100462D43
0x100462d27  call    cs:__imp_GetLastError
0x100462d2d  mov     r9d, eax
0x100462d30  mov     r8, cs:off_1005E6B88; "<CConnection::CreateLoginRecord|ERR|SNA"...
0x100462d37  mov     edx, 1AD000h
0x100462d3c  xor     ecx, ecx
0x100462d3e  call    _bidTraceW
0x100462d43  mov     ecx, 80004005h
0x100462d48  mov     ebx, ecx
0x100462d4a  mov     r14d, 9E28h
0x100462d50  test    byte ptr cs:_bidGblFlags, 2
0x100462d57  jz      short loc_100462D91
0x100462d59  mov     rax, cs:off_1005E6B90; "<CConnection::CreateLoginRecord|TDS|ERR"...
0x100462d60  test    rax, rax
0x100462d63  jz      short loc_100462D91
0x100462d65  mov     r8, cs:off_1005E6B90; "<CConnection::CreateLoginRecord|TDS|ERR"...
0x100462d6c  mov     edx, 1AD800h
0x100462d71  mov     [rsp+1D0h+var_198], ecx
0x100462d75  mov     [rsp+1D0h+var_1A0], r14d
0x100462d7a  mov     [rsp+1D0h+var_1A8], 3
0x100462d82  mov     r9, rsi
0x100462d85  mov     [rsp+1D0h+var_1B0], r12
0x100462d8a  xor     ecx, ecx
0x100462d8c  call    _bidTraceW
0x100462d91  mov     rdi, [rsi+0F30h]
0x100462d98  call    cs:__imp_GetLastError
0x100462d9e  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x100462da2  mov     r9d, 80004005h; unsigned int
0x100462da8  mov     r8d, r14d; unsigned __int16
0x100462dab  mov     rdx, r12; void *
0x100462dae  mov     rcx, rdi; this
0x100462db1  call    ?PostFormattedParserErrorEx@CTdsParser@@AEAAJPEAXGKZZ; CTdsParser::PostFormattedParserErrorEx(void *,ushort,ulong,...)
0x100462db6  jmp     loc_1004637FC
0x100462dbb  lea     r8, [rdi+2Ch]; struct OFFLEN *
0x100462dbf  lea     r9, [rsp+1D0h+Destination]; unsigned __int16 *
0x100462dc4  mov     rdx, r15; struct CExtByteBuffer *
0x100462dc7  mov     rcx, rsi; this
0x100462dca  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x100462dcf  mov     ebx, eax
0x100462dd1  lea     rdi, [rsp+1D0h+Destination]
0x100462dd6  xor     eax, eax
0x100462dd8  mov     ecx, 120h
0x100462ddd  rep stosb
0x100462ddf  test    ebx, ebx
0x100462de1  jns     short loc_100462E2D
0x100462de3  test    byte ptr cs:_bidGblFlags, 2
0x100462dea  jz      loc_1004637FC
0x100462df0  mov     r8d, ebx
0x100462df3  mov     edx, 1B0409h
0x100462df8  jmp     loc_100462C4D
0x100462dfd  lea     r8, [rdi+2Ch]; struct OFFLEN *
0x100462e01  mov     r9, [r14+28h]; unsigned __int16 *
0x100462e05  mov     rdx, r15; struct CExtByteBuffer *
0x100462e08  mov     rcx, rsi; this
0x100462e0b  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x100462e10  mov     ebx, eax
0x100462e12  test    eax, eax
0x100462e14  jns     short loc_100462E2D
0x100462e16  test    byte ptr cs:_bidGblFlags, 2
0x100462e1d  jz      loc_1004637FC
0x100462e23  mov     edx, 1B1809h
0x100462e28  jmp     loc_100462C4A
0x100462e2d  lfence
0x100462e30  mov     r8, [r15+20h]
0x100462e34  movzx   ecx, word ptr [r8+2Ch]
0x100462e39  add     rcx, r8
0x100462e3c  movzx   edx, word ptr [r8+2Eh]
0x100462e41  add     rdx, rdx
0x100462e44  jz      short loc_100462E58
0x100462e46  mov     al, [rcx]
0x100462e48  rol     al, 4
0x100462e4b  xor     al, 0A5h
0x100462e4d  mov     [rcx], al
0x100462e4f  inc     rcx
0x100462e52  sub     rdx, 1
0x100462e56  jnz     short loc_100462E46
0x100462e58  add     r8, 30h ; '0'; struct OFFLEN *
0x100462e5c  mov     r9, [r14+60h]; unsigned __int16 *
0x100462e60  mov     rdx, r15; struct CExtByteBuffer *
0x100462e63  mov     rcx, rsi; this
0x100462e66  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x100462e6b  mov     ebx, eax
0x100462e6d  test    eax, eax
0x100462e6f  jns     short loc_100462E88
0x100462e71  test    byte ptr cs:_bidGblFlags, 2
0x100462e78  jz      loc_1004637FC
0x100462e7e  mov     edx, 1B4009h
0x100462e83  jmp     loc_100462C4A
0x100462e88  lfence
0x100462e8b  mov     r8, [r15+20h]
0x100462e8f  mov     r9, [r14+50h]
0x100462e93  test    r9, r9
0x100462e96  jz      short loc_100462EAA
0x100462e98  cmp     [r9], r13w
0x100462e9c  jz      short loc_100462EAA
0x100462e9e  mov     cl, [r8+19h]
0x100462ea2  and     cl, 0AFh
0x100462ea5  or      cl, 20h
0x100462ea8  jmp     short loc_100462EDF
0x100462eaa  mov     r9, [r14+58h]
0x100462eae  test    r9, r9
0x100462eb1  jz      short loc_100462EC5
0x100462eb3  cmp     [r9], r13w
0x100462eb7  jz      short loc_100462EC5
0x100462eb9  mov     cl, [r8+19h]
0x100462ebd  and     cl, 0BFh
0x100462ec0  or      cl, 30h
0x100462ec3  jmp     short loc_100462EDF
0x100462ec5  mov     r9, [r14+48h]; unsigned __int16 *
0x100462ec9  mov     al, [r14+175h]
0x100462ed0  neg     al
0x100462ed2  sbb     cl, cl
0x100462ed4  and     cl, 30h
0x100462ed7  mov     al, [r8+19h]
0x100462edb  and     al, 8Fh
0x100462edd  or      cl, al
0x100462edf  mov     [r8+19h], cl
0x100462ee3  mov     edx, 80h
0x100462ee8  test    r9, r9
0x100462eeb  jz      short loc_100462F3D
0x100462eed  test    cl, 70h
0x100462ef0  jnz     short loc_100462F3D
0x100462ef2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x100462ef6  mov     rax, rcx
0x100462ef9  inc     rax
0x100462efc  cmp     [r9+rax*2], r13w
0x100462f01  jnz     short loc_100462EF9
0x100462f03  cmp     rax, rdx
0x100462f06  jnb     short loc_100462F17
0x100462f08  lfence
0x100462f0b  inc     rcx
0x100462f0e  cmp     [r9+rcx*2], r13w
0x100462f13  jnz     short loc_100462F0B
0x100462f15  jmp     short loc_100462F1A
0x100462f17  movzx   ecx, dx
0x100462f1a  movzx   eax, word ptr [r15+8]
0x100462f1f  mov     [r8+34h], ax
0x100462f24  mov     [r8+36h], cx
0x100462f29  movzx   r8d, cx
0x100462f2d  add     r8, r8; SourceSize
0x100462f30  mov     rdx, r9; Source
0x100462f33  mov     rcx, r15; this
0x100462f36  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x100462f3b  jmp     short loc_100462F4C
0x100462f3d  add     r8, 34h ; '4'; struct OFFLEN *
0x100462f41  mov     rdx, r15; struct CExtByteBuffer *
0x100462f44  mov     rcx, rsi; this
0x100462f47  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x100462f4c  mov     ebx, eax
0x100462f4e  test    eax, eax
0x100462f50  jns     short loc_100462F6C
0x100462f52  test    byte ptr cs:_bidGblFlags, 2
0x100462f59  jz      loc_1004637FC
0x100462f5f  mov     r8d, eax
0x100462f62  mov     edx, 1BC009h
0x100462f67  jmp     loc_100462C4D
0x100462f6c  lfence
0x100462f6f  mov     rcx, [r15+20h]
0x100462f73  movzx   eax, word ptr [r15+8]
0x100462f78  mov     [rcx+38h], ax
0x100462f7c  mov     eax, 4
0x100462f81  mov     [rcx+3Ah], ax
0x100462f85  mov     r8d, eax; SourceSize
  ... truncated ...
```
