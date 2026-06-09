# CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(ushort const *,ushort const *,ulong,ulong,uint *,ulong *)

- ea: `0x181099880`
- end: `0x18109a0a5`
- name: `?AddUrlAndNotifyCPWithBrowserHandle@CUrlHistoryBase@@UEAAJPEBG0KKPEAIPEAK@Z`
- size: `2085`
- prototype: `__int64 __fastcall(CUrlHistoryBase *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, DWORD, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x181099810`

## callees

- `0x180214b84`
- `0x180275414`
- `0x18040ac58`
- `0x180695734`
- `0x1807318dc`
- `0x18106980c`
- `0x181099880`
- `0x18109ae74`
- `0x18109af4c`
- `0x18109b060`
- `0x18109b2e8`
- `0x18109b518`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x181099dc1`
- `KERNEL32!SystemTimeToFileTime` at `0x181099dc1`
- `KERNEL32!GetLocalTime` at `0x181099dad`
- `KERNEL32!GetLocalTime` at `0x181099dad`
- `KERNEL32!GetCurrentThreadId` at `0x18109990e`
- `KERNEL32!GetCurrentThreadId` at `0x18109990e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x1810999ae`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x1810999ae`
- `iertutil!__imp_IEGlobalCounterIncrement` at `0x18109a03b`
- `iertutil!__imp_IEGlobalCounterIncrement` at `0x18109a03b`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099a8d`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099ac6`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099aff`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099b3a`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099b73`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099bd8`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099c77`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099cb0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099cf0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099d2d`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18109a02a`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099a8d`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099ac6`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099aff`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099b3a`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099b73`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099bd8`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099c77`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099cb0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099cf0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181099d2d`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18109a02a`
- `SHLWAPI!UrlIsNoHistoryW` at `0x181099ea6`
- `SHLWAPI!UrlIsNoHistoryW` at `0x181099ea6`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x181099928`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x181099928`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x181099942`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x18109995c`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x181099942`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x18109995c`
- `urlmon!CoInternetQueryInfo` at `0x181099f1e`
- `urlmon!CoInternetQueryInfo` at `0x181099f1e`

## pseudocode

```c
__int64 __fastcall CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(
        CUrlHistoryBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        DWORD a5,
        unsigned int *a6,
        unsigned int *a7)
{
  DWORD CurrentThreadId; // eax
  int v12; // r14d
  const unsigned __int16 *v13; // r13
  struct IStream *v14; // rbx
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  int v17; // ebx
  unsigned int v18; // ebx
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // esi
  unsigned int v25; // edi
  CUrlHistoryBase *v26; // rbx
  CUrlHistoryBase *v27; // rcx
  int cbBuffer; // [rsp+28h] [rbp-E0h]
  struct IHistoryData *v30; // [rsp+88h] [rbp-80h] BYREF
  int pvBuffer; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v32; // [rsp+94h] [rbp-74h] BYREF
  unsigned int v33; // [rsp+98h] [rbp-70h]
  DWORD pcbBuffer; // [rsp+9Ch] [rbp-6Ch] BYREF
  unsigned int v35; // [rsp+A0h] [rbp-68h] BYREF
  int v36; // [rsp+A4h] [rbp-64h]
  unsigned int v37; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v38; // [rsp+ACh] [rbp-5Ch]
  unsigned __int16 *v39; // [rsp+B0h] [rbp-58h] BYREF
  struct _FILETIME v40; // [rsp+B8h] [rbp-50h] BYREF
  struct _FILETIME FileTime; // [rsp+C0h] [rbp-48h] BYREF
  CUrlHistoryBase *v42; // [rsp+C8h] [rbp-40h]
  struct IStream *v43; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int *v44; // [rsp+D8h] [rbp-30h]
  __int64 v45; // [rsp+E0h] [rbp-28h] BYREF
  PROPVARIANT v46[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-10h]
  __int128 v48; // [rsp+100h] [rbp-8h] BYREF
  __int64 v49; // [rsp+110h] [rbp+8h]
  __int128 v50; // [rsp+118h] [rbp+10h] BYREF
  __int64 v51; // [rsp+128h] [rbp+20h]
  PROPVARIANT pvar[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v53; // [rsp+140h] [rbp+38h]
  unsigned __int16 v54[264]; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int16 v55[264]; // [rsp+358h] [rbp+250h] BYREF
  unsigned __int16 v56[264]; // [rsp+568h] [rbp+460h] BYREF
  unsigned __int16 v57[2088]; // [rsp+778h] [rbp+670h] BYREF

  v42 = this;
  v44 = a7;
  if ( a6 )
    *a6 = 0;
  CurrentThreadId = a5;
  v35 = 0;
  if ( !a5 )
    CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v35, 0) >= 0
    && !LCIEIsComponentSharedFlagValueSet(v35, 0x1000000u)
    && !LCIEIsComponentSharedFlagValueSet(v35, 0x400000u) )
  {
    if ( a7 )
      *a7 = 0;
    return (unsigned int)CUrlHistoryBase::_CacheUrlForPrerender(this, a2, a3, a4);
  }
  if ( a2 && *a2 )
  {
    v13 = a3;
    if ( a3 && !StrCmpIW(a3, a2) )
      v13 = 0;
    v30 = 0;
    v54[0] = 0;
    v32 = 0;
    v14 = 0;
    v40 = 0;
    FileTime = 0;
    v56[0] = 0;
    v57[0] = 0;
    v38 = 0;
    LOBYTE(v36) = 0;
    v55[0] = 0;
    pvBuffer = 0;
    pcbBuffer = 0;
    v37 = 0;
    v43 = 0;
    v45 = 0;
    v33 = 0;
    v39 = 0;
    if ( (int)CUrlHistoryBase::_GetHistoryDataFromWinINetCache(this, a2, &v39, &v30) < 0 )
    {
      v39 = 0;
      v30 = 0;
      pvar[0] = 0;
      v12 = CUrlHistoryBase::_EnsureHistoryDataFactory(this, (struct IHistoryDataFactory **)pvar);
      if ( v12 >= 0 )
        v12 = (*(__int64 (__fastcall **)(PROPVARIANT, const unsigned __int16 *, unsigned __int16 **, struct IHistoryData **))(*(_QWORD *)pvar[0] + 24LL))(
                pvar[0],
                a2,
                &v39,
                &v30);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(pvar);
      if ( v12 < 0 )
        goto LABEL_92;
    }
    else
    {
      v12 = 0;
      if ( !a3 )
        (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v30 + 56LL))(
          v30,
          16,
          v54,
          260);
      v53 = 0;
      *(_OWORD *)pvar = 0;
      if ( a6
        && (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 18, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        *a6 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 6, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v33 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 23, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v32 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 24, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v40 = (struct _FILETIME)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 39, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v38 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 34, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(
               v30,
               40,
               pvar) >= 0 )
        {
          v15 = (unsigned __int8)v36;
          if ( !LOWORD(pvar[0]) )
            v15 = 1;
          v36 = v15;
        }
        PropVariantClear(pvar);
      }
      (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v30 + 56LL))(
        v30,
        25,
        v56,
        260);
      (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v30 + 56LL))(
        v30,
        26,
        v57,
        2084);
      (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v30 + 56LL))(
        v30,
        27,
        v55,
        260);
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 28, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        pcbBuffer = (DWORD)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 32, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        pvBuffer = (int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 29, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        ATL::CComPtr<IStream>::operator=(&v43, pvar[1]);
        PropVariantClear(pvar);
        v14 = v43;
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 33, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v37 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
    }
    if ( v13 )
      StringCchCopyW(v54, 0x104u, v13);
    *(_OWORD *)pvar = 0;
    GetLocalTime((LPSYSTEMTIME)pvar);
    if ( SystemTimeToFileTime((const SYSTEMTIME *)pvar, &FileTime) && !v32 )
      v40 = FileTime;
    if ( (int)CUrlHistoryBase::_UpdateHistoryData(
                (CUrlHistoryBase *)&v32,
                v16,
                v54,
                v30,
                v39,
                &v32,
                &v40,
                v56,
                v57,
                v55,
                &pvBuffer,
                &pcbBuffer,
                &v37,
                v14) < 0 )
    {
LABEL_91:
      IEGlobalCounterIncrement(11);
LABEL_92:
      if ( v44 )
        *v44 = a4;
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      return (unsigned int)v12;
    }
    v47 = 0;
    *(_OWORD *)v46 = 0;
    v17 = 0;
    if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v30 + 24LL))(v30, 9, v46) >= 0
      && LOWORD(v46[0]) )
    {
      v17 = (int)v46[1];
    }
    if ( (a4 & 4) != 0 || (a4 & 1) != 0 && !UrlIsNoHistoryW(a2) )
      v18 = v17 | 0x10000000;
    else
      v18 = v17 & 0xEFFFFFFF;
    v19 = a4 | 4;
    if ( (v18 & 0x10000000) == 0 )
      v19 = a4;
    a4 = v19;
    if ( (unsigned int)IsSpartanApp() )
    {
      v20 = GetUrlSchemeW(a2) - 4;
      if ( !v20 )
        goto LABEL_82;
      v21 = v20 - 11;
      if ( !v21 )
        goto LABEL_82;
      v22 = v21 - 1;
      if ( !v22 )
        goto LABEL_82;
      v23 = v22 - 1;
      if ( !v23 )
      {
LABEL_81:
        v18 &= ~0x10000000u;
        goto LABEL_82;
      }
      if ( v23 == 1 )
      {
LABEL_82:
        v24 = v33;
        v25 = v18 & 0xFFFFFFFE;
        if ( (v18 & 1) == 0 )
          v25 = v18;
        if ( (a4 & 8) != 0 || (v25 & 0x10000000) == 0 )
        {
          v26 = v42;
        }
        else
        {
          v49 = 0;
          v48 = 0;
          LOWORD(v48) = 19;
          DWORD2(v48) = v33 + 1;
          (*(void (__fastcall **)(struct IHistoryData *, __int64, __int128 *))(*(_QWORD *)v30 + 32LL))(v30, 6, &v48);
          v26 = v42;
          LOBYTE(cbBuffer) = v36;
          (*(void (__fastcall **)(CUrlHistoryBase *, _QWORD, _QWORD, _QWORD, int, struct IHistoryData *, struct _FILETIME *, struct _FILETIME *))(*(_QWORD *)v42 + 216LL))(
            v42,
            a4,
            v32,
            v38,
            cbBuffer,
            v30,
            &v40,
            &FileTime);
        }
        v50 = 0;
        v51 = 0;
        LOWORD(v50) = 19;
        DWORD2(v50) = v25;
        (*(void (__fastcall **)(struct IHistoryData *, __int64, __int128 *))(*(_QWORD *)v30 + 32LL))(v30, 9, &v50);
        v12 = CUrlHistoryBase::_CommitUrlCacheEntry(v27, v30);
        if ( v12 >= 0 )
          (*(void (__fastcall **)(CUrlHistoryBase *, struct IHistoryData *, _QWORD))(*(_QWORD *)v26 + 224LL))(
            v26,
            v30,
            v24);
        PropVariantClear(v46);
        goto LABEL_91;
      }
    }
    pvBuffer = 0;
    pcbBuffer = 0;
    if ( CoInternetQueryInfo(a2, QUERY_USES_HISTORYFOLDER, 0, &pvBuffer, 4u, &pcbBuffer, 0) < 0 || pvBuffer )
      goto LABEL_82;
    goto LABEL_81;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x181099880  mov     rax, rsp
0x181099883  mov     [rax+20h], r9d
0x181099887  mov     [rax+18h], r8
0x18109988b  mov     [rax+10h], rdx
0x18109988f  mov     [rax+8], rcx
0x181099893  push    rbp
0x181099894  push    rbx
0x181099895  push    rsi
0x181099896  push    rdi
0x181099897  push    r12
0x181099899  push    r13
0x18109989b  push    r14
0x18109989d  push    r15
0x18109989f  lea     rbp, [rax-1718h]
0x1810998a6  mov     eax, 17D8h
0x1810998ab  call    _alloca_probe
0x1810998b0  sub     rsp, rax
0x1810998b3  mov     rax, cs:__security_cookie
0x1810998ba  xor     rax, rsp
0x1810998bd  mov     [rbp+1710h+var_50], rax
0x1810998c4  mov     r12, [rbp+1710h+arg_28]
0x1810998cb  xor     ecx, ecx
0x1810998cd  mov     r14, [rbp+1710h+arg_0]
0x1810998d4  mov     rbx, [rbp+1710h+arg_30]
0x1810998db  mov     r15d, [rbp+1710h+arg_18]
0x1810998e2  mov     rsi, [rbp+1710h+psz2]
0x1810998e9  mov     rdi, [rbp+1710h+psz1]
0x1810998f0  mov     [rbp+1710h+var_1750], r14
0x1810998f4  mov     [rbp+1710h+var_1740], rbx
0x1810998f8  test    r12, r12
0x1810998fb  jz      short loc_181099901
0x1810998fd  mov     [r12], ecx
0x181099901  mov     eax, [rbp+1710h+arg_20]
0x181099907  mov     [rbp+1710h+var_1778], ecx
0x18109990a  test    eax, eax
0x18109990c  jnz     short loc_18109991A
0x18109990e  call    cs:__imp_GetCurrentThreadId
0x181099915  nop     dword ptr [rax+rax+00h]
0x18109991a  xor     r9d, r9d
0x18109991d  lea     r8, [rbp+1710h+var_1778]
0x181099921  mov     edx, eax
0x181099923  mov     ecx, 203h
0x181099928  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18109992f  nop     dword ptr [rax+rax+00h]
0x181099934  xor     edx, edx
0x181099936  test    eax, eax
0x181099938  js      short loc_18109998E
0x18109993a  mov     ecx, [rbp+1710h+var_1778]
0x18109993d  mov     edx, 1000000h
0x181099942  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z; LCIEIsComponentSharedFlagValueSet(ulong,ulong)
0x181099949  nop     dword ptr [rax+rax+00h]
0x18109994e  xor     edx, edx
0x181099950  test    eax, eax
0x181099952  jnz     short loc_18109998E
0x181099954  mov     ecx, [rbp+1710h+var_1778]
0x181099957  mov     edx, 400000h
0x18109995c  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z; LCIEIsComponentSharedFlagValueSet(ulong,ulong)
0x181099963  nop     dword ptr [rax+rax+00h]
0x181099968  xor     edx, edx
0x18109996a  test    eax, eax
0x18109996c  jnz     short loc_18109998E
0x18109996e  test    rbx, rbx
0x181099971  jz      short loc_181099975
0x181099973  mov     [rbx], edx
0x181099975  mov     r9d, r15d; unsigned int
0x181099978  mov     r8, rdi; unsigned __int16 *
0x18109997b  mov     rdx, rsi; unsigned __int16 *
0x18109997e  mov     rcx, r14; this
0x181099981  call    ?_CacheUrlForPrerender@CUrlHistoryBase@@IEAAJPEBG0K@Z; CUrlHistoryBase::_CacheUrlForPrerender(ushort const *,ushort const *,ulong)
0x181099986  mov     r14d, eax
0x181099989  jmp     loc_18109A077
0x18109998e  test    rsi, rsi
0x181099991  jz      loc_18109A07C
0x181099997  cmp     [rsi], dx
0x18109999a  jz      loc_18109A07C
0x1810999a0  mov     r13, rdi
0x1810999a3  test    rdi, rdi
0x1810999a6  jz      short loc_1810999C2
0x1810999a8  mov     rdx, rsi; psz2
0x1810999ab  mov     rcx, rdi; psz1
0x1810999ae  call    cs:__imp_StrCmpIW
0x1810999b5  nop     dword ptr [rax+rax+00h]
0x1810999ba  xor     edx, edx
0x1810999bc  test    eax, eax
0x1810999be  cmovz   r13, rdx
0x1810999c2  mov     [rbp+1710h+var_1790], rdx
0x1810999c6  lea     r9, [rbp+1710h+var_1790]; struct IHistoryData **
0x1810999ca  mov     [rbp+1710h+var_16D0], dx
0x1810999ce  lea     r8, [rbp+1710h+var_1768]; unsigned __int16 **
0x1810999d2  mov     [rbp+1710h+var_1784], edx
0x1810999d5  mov     rbx, rdx
0x1810999d8  mov     qword ptr [rbp+1710h+var_1760.dwLowDateTime], rdx
0x1810999dc  mov     rcx, r14; this
0x1810999df  mov     qword ptr [rbp+1710h+FileTime.dwLowDateTime], rdx
0x1810999e3  mov     [rbp+1710h+var_12B0], dx
0x1810999ea  mov     [rbp+1710h+var_10A0], dx
0x1810999f1  mov     [rbp+1710h+var_176C], edx
0x1810999f4  mov     byte ptr [rbp+1710h+var_1774], dl
0x1810999f7  mov     [rbp+1710h+var_14C0], dx
0x1810999fe  mov     [rbp+1710h+pvBuffer], edx
0x181099a01  mov     [rbp+1710h+var_177C], edx
0x181099a04  mov     [rbp+1710h+var_1770], edx
0x181099a07  mov     [rbp+1710h+var_1748], rdx
0x181099a0b  mov     [rbp+1710h+var_1738], rdx
0x181099a0f  mov     [rbp+1710h+var_1780], edx
0x181099a12  mov     [rbp+1710h+var_1768], rdx
0x181099a16  mov     rdx, rsi; unsigned __int16 *
0x181099a19  call    ?_GetHistoryDataFromWinINetCache@CUrlHistoryBase@@IEAAJPEBGPEAPEAGPEAPEAUIHistoryData@@@Z; CUrlHistoryBase::_GetHistoryDataFromWinINetCache(ushort const *,ushort * *,IHistoryData * *)
0x181099a1e  xor     ecx, ecx
0x181099a20  test    eax, eax
0x181099a22  js      loc_181099D3B
0x181099a28  mov     r14d, ecx
0x181099a2b  test    rdi, rdi
0x181099a2e  jnz     short loc_181099A4D
0x181099a30  mov     rcx, [rbp+1710h+var_1790]
0x181099a34  lea     r8, [rbp+1710h+var_16D0]
0x181099a38  mov     r9d, 104h
0x181099a3e  lea     edx, [rdi+10h]
0x181099a41  mov     rax, [rcx]
0x181099a44  mov     rax, [rax+38h]
0x181099a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099a4d  xor     eax, eax
0x181099a4f  xor     edi, edi
0x181099a51  mov     [rbp+1710h+var_16D8], rax
0x181099a55  xorps   xmm0, xmm0
0x181099a58  movups  xmmword ptr [rbp+1710h+pvar], xmm0
0x181099a5c  test    r12, r12
0x181099a5f  jz      short loc_181099A99
0x181099a61  mov     rcx, [rbp+1710h+var_1790]
0x181099a65  lea     r8, [rbp+1710h+pvar]
0x181099a69  lea     edx, [rdi+12h]
0x181099a6c  mov     rax, [rcx]
0x181099a6f  mov     rax, [rax+18h]
0x181099a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099a78  test    eax, eax
0x181099a7a  js      short loc_181099A99
0x181099a7c  cmp     word ptr [rbp+1710h+pvar], di
0x181099a80  jz      short loc_181099A99
0x181099a82  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181099a85  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099a89  mov     [r12], eax
0x181099a8d  call    cs:__imp_PropVariantClear
0x181099a94  nop     dword ptr [rax+rax+00h]
0x181099a99  mov     rcx, [rbp+1710h+var_1790]
0x181099a9d  lea     r8, [rbp+1710h+pvar]
0x181099aa1  mov     edx, 6
0x181099aa6  mov     rax, [rcx]
0x181099aa9  mov     rax, [rax+18h]
0x181099aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099ab2  test    eax, eax
0x181099ab4  js      short loc_181099AD2
0x181099ab6  cmp     word ptr [rbp+1710h+pvar], di
0x181099aba  jz      short loc_181099AD2
0x181099abc  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181099abf  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099ac3  mov     [rbp+1710h+var_1780], eax
0x181099ac6  call    cs:__imp_PropVariantClear
0x181099acd  nop     dword ptr [rax+rax+00h]
0x181099ad2  mov     rcx, [rbp+1710h+var_1790]
0x181099ad6  lea     r8, [rbp+1710h+pvar]
0x181099ada  mov     edx, 17h
0x181099adf  mov     rax, [rcx]
0x181099ae2  mov     rax, [rax+18h]
0x181099ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099aeb  test    eax, eax
0x181099aed  js      short loc_181099B0B
0x181099aef  cmp     word ptr [rbp+1710h+pvar], di
0x181099af3  jz      short loc_181099B0B
0x181099af5  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181099af8  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099afc  mov     [rbp+1710h+var_1784], eax
0x181099aff  call    cs:__imp_PropVariantClear
0x181099b06  nop     dword ptr [rax+rax+00h]
0x181099b0b  mov     rcx, [rbp+1710h+var_1790]
0x181099b0f  lea     r8, [rbp+1710h+pvar]
0x181099b13  mov     edx, 18h
0x181099b18  mov     rax, [rcx]
0x181099b1b  mov     rax, [rax+18h]
0x181099b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099b24  test    eax, eax
0x181099b26  js      short loc_181099B46
0x181099b28  cmp     word ptr [rbp+1710h+pvar], di
0x181099b2c  jz      short loc_181099B46
0x181099b2e  mov     rax, [rbp+1710h+pvar+8]
0x181099b32  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099b36  mov     qword ptr [rbp+1710h+var_1760.dwLowDateTime], rax
0x181099b3a  call    cs:__imp_PropVariantClear
0x181099b41  nop     dword ptr [rax+rax+00h]
0x181099b46  mov     rcx, [rbp+1710h+var_1790]
0x181099b4a  lea     r8, [rbp+1710h+pvar]
0x181099b4e  mov     edx, 27h ; '''
0x181099b53  mov     rax, [rcx]
0x181099b56  mov     rax, [rax+18h]
0x181099b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099b5f  test    eax, eax
0x181099b61  js      short loc_181099B7F
0x181099b63  cmp     word ptr [rbp+1710h+pvar], di
0x181099b67  jz      short loc_181099B7F
0x181099b69  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181099b6c  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099b70  mov     [rbp+1710h+var_176C], eax
0x181099b73  call    cs:__imp_PropVariantClear
0x181099b7a  nop     dword ptr [rax+rax+00h]
0x181099b7f  mov     rcx, [rbp+1710h+var_1790]
0x181099b83  lea     r8, [rbp+1710h+pvar]
0x181099b87  mov     edx, 22h ; '"'
0x181099b8c  mov     rax, [rcx]
0x181099b8f  mov     rax, [rax+18h]
0x181099b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099b98  test    eax, eax
0x181099b9a  js      short loc_181099BE4
0x181099b9c  cmp     word ptr [rbp+1710h+pvar], di
0x181099ba0  jz      short loc_181099BE4
0x181099ba2  mov     rcx, [rbp+1710h+var_1790]
0x181099ba6  lea     r8, [rbp+1710h+pvar]
0x181099baa  mov     edx, 28h ; '('
0x181099baf  mov     rax, [rcx]
0x181099bb2  mov     rax, [rax+18h]
0x181099bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099bbb  test    eax, eax
0x181099bbd  js      short loc_181099BD4
0x181099bbf  mov     eax, [rbp+1710h+var_1774]
0x181099bc2  mov     ecx, 1
0x181099bc7  cmp     word ptr [rbp+1710h+pvar], di
0x181099bcb  movzx   eax, al
0x181099bce  cmovz   eax, ecx
0x181099bd1  mov     [rbp+1710h+var_1774], eax
0x181099bd4  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099bd8  call    cs:__imp_PropVariantClear
0x181099bdf  nop     dword ptr [rax+rax+00h]
0x181099be4  mov     rcx, [rbp+1710h+var_1790]
0x181099be8  lea     r8, [rbp+1710h+var_12B0]
0x181099bef  mov     r9d, 104h
0x181099bf5  mov     edx, 19h
0x181099bfa  mov     rax, [rcx]
0x181099bfd  mov     rax, [rax+38h]
0x181099c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099c06  mov     rcx, [rbp+1710h+var_1790]
0x181099c0a  lea     r8, [rbp+1710h+var_10A0]
0x181099c11  mov     r9d, 824h
0x181099c17  mov     edx, 1Ah
0x181099c1c  mov     rax, [rcx]
0x181099c1f  mov     rax, [rax+38h]
0x181099c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099c28  mov     rcx, [rbp+1710h+var_1790]
0x181099c2c  lea     r8, [rbp+1710h+var_14C0]
0x181099c33  mov     r9d, 104h
0x181099c39  mov     edx, 1Bh
0x181099c3e  mov     rax, [rcx]
0x181099c41  mov     rax, [rax+38h]
0x181099c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099c4a  mov     rcx, [rbp+1710h+var_1790]
0x181099c4e  lea     r8, [rbp+1710h+pvar]
0x181099c52  mov     edx, 1Ch
0x181099c57  mov     rax, [rcx]
0x181099c5a  mov     rax, [rax+18h]
0x181099c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099c63  test    eax, eax
0x181099c65  js      short loc_181099C83
0x181099c67  cmp     word ptr [rbp+1710h+pvar], di
0x181099c6b  jz      short loc_181099C83
0x181099c6d  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181099c70  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099c74  mov     [rbp+1710h+var_177C], eax
0x181099c77  call    cs:__imp_PropVariantClear
0x181099c7e  nop     dword ptr [rax+rax+00h]
0x181099c83  mov     rcx, [rbp+1710h+var_1790]
0x181099c87  lea     r8, [rbp+1710h+pvar]
0x181099c8b  mov     edx, 20h ; ' '
0x181099c90  mov     rax, [rcx]
0x181099c93  mov     rax, [rax+18h]
0x181099c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099c9c  test    eax, eax
0x181099c9e  js      short loc_181099CBC
0x181099ca0  cmp     word ptr [rbp+1710h+pvar], di
0x181099ca4  jz      short loc_181099CBC
0x181099ca6  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181099ca9  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099cad  mov     [rbp+1710h+pvBuffer], eax
0x181099cb0  call    cs:__imp_PropVariantClear
0x181099cb7  nop     dword ptr [rax+rax+00h]
0x181099cbc  mov     rcx, [rbp+1710h+var_1790]
0x181099cc0  lea     r8, [rbp+1710h+pvar]
0x181099cc4  mov     edx, 1Dh
0x181099cc9  mov     rax, [rcx]
0x181099ccc  mov     rax, [rax+18h]
0x181099cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181099cd5  test    eax, eax
0x181099cd7  js      short loc_181099D00
0x181099cd9  cmp     word ptr [rbp+1710h+pvar], di
0x181099cdd  jz      short loc_181099D00
0x181099cdf  mov     rdx, [rbp+1710h+pvar+8]
0x181099ce3  lea     rcx, [rbp+1710h+var_1748]
0x181099ce7  call    ??4?$CComPtr@UIStream@@@ATL@@QEAAPEAUIStream@@PEAU2@@Z; ATL::CComPtr<IStream>::operator=(IStream *)
0x181099cec  lea     rcx, [rbp+1710h+pvar]; pvar
0x181099cf0  call    cs:__imp_PropVariantClear
0x181099cf7  nop     dword ptr [rax+rax+00h]
0x181099cfc  mov     rbx, [rbp+1710h+var_1748]
0x181099d00  mov     rcx, [rbp+1710h+var_1790]
0x181099d04  lea     r8, [rbp+1710h+pvar]
  ... truncated ...
```
