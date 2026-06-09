# CMultiReplacer::ReplaceWithRegKeyLookup(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x140022e40`
- end: `0x140023824`
- name: `?ReplaceWithRegKeyLookup@CMultiReplacer@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `2532`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x140016d4c`

## callees

- `0x140002140`
- `0x140002c10`
- `0x140002dd0`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x140007740`
- `0x140007a58`
- `0x14000fe10`
- `0x14000fea8`
- `0x1400102a0`
- `0x140011b10`
- `0x140022e40`
- `0x140023824`
- `0x140027c20`
- `0x14002891c`
- `0x140033ab0`
- `0x1400464b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140023637`
- `ADVAPI32!RegCloseKey` at `0x140023637`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140023236`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140023236`
- `ADVAPI32!RevertToSelf` at `0x140023663`
- `ADVAPI32!RevertToSelf` at `0x140023663`
- `VCRUNTIME140!wcsstr` at `0x140022e7c`
- `VCRUNTIME140!wcsstr` at `0x140022ec4`
- `VCRUNTIME140!wcsstr` at `0x140022fc3`
- `VCRUNTIME140!wcsstr` at `0x140023032`
- `VCRUNTIME140!wcsstr` at `0x1400230a1`
- `VCRUNTIME140!wcsstr` at `0x140022e7c`
- `VCRUNTIME140!wcsstr` at `0x140022ec4`
- `VCRUNTIME140!wcsstr` at `0x140022fc3`
- `VCRUNTIME140!wcsstr` at `0x140023032`
- `VCRUNTIME140!wcsstr` at `0x1400230a1`
- `VCRUNTIME140!wcsrchr` at `0x14002317f`
- `VCRUNTIME140!wcsrchr` at `0x14002317f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140023306`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400233d8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140023306`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400233d8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400237c3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400237e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400237c3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400237e0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400237b7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400237d4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400237b7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400237d4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400233fe`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400233fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CMultiReplacer::ReplaceWithRegKeyLookup(__int64 a1, const wchar_t **a2)
{
  wchar_t *v4; // rax
  __int64 v5; // rdi
  int v6; // ecx
  wchar_t *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  wchar_t *v10; // rcx
  wchar_t *v11; // rax
  unsigned __int64 v12; // r15
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  _QWORD *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  wchar_t *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  _QWORD *v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // rdx
  bool v24; // r14
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned __int16 *v26; // rdi
  wchar_t *v27; // r12
  __int64 v28; // rbx
  unsigned int v29; // ebx
  void *v30; // r12
  __int64 v31; // rbx
  unsigned int v32; // ebx
  unsigned __int16 *v33; // rbx
  int StringValue; // ebx
  int v35; // eax
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned __int16 *v39; // rdx
  _QWORD *v40; // rdx
  __int64 v41; // rcx
  __int64 *v42; // rdx
  struct ATL::IAtlStringMgr *v43; // rax
  __int64 v44; // rsi
  struct ATL::IAtlStringMgr *v45; // rax
  wchar_t **p_SubStr; // rdx
  struct ATL::IAtlStringMgr *v47; // rax
  unsigned __int16 *v48; // rbx
  _QWORD *v49; // rdx
  _QWORD *v50; // rdx
  wchar_t *v51; // rdx
  wchar_t *v52; // rdx
  wchar_t *v53; // rdx
  wchar_t *v54; // rdx
  _QWORD *v55; // rdx
  _QWORD *v56; // rdx
  wchar_t *Str; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v58; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v59; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *SubStr; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v64; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h]
  void *Block; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v70[264]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v71; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v72[312]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v73; // [rsp+310h] [rbp+210h] BYREF
  __int64 v74; // [rsp+318h] [rbp+218h] BYREF

  if ( *((int *)*a2 - 4) < 0 )
    return;
  v4 = wcsstr(*a2, L"$=");
  if ( !v4 )
    return;
  v5 = v4 - *a2;
  if ( (_DWORD)v5 == -1 )
    return;
  v6 = v5 + 1;
  if ( (int)v5 + 1 >= 0 && v6 <= *((_DWORD *)*a2 - 4) && (_mm_lfence(), (v7 = wcsstr(&(*a2)[v6], L"$")) != 0) )
    v8 = v7 - *a2;
  else
    LODWORD(v8) = -1;
  if ( (_DWORD)v8 == -1 )
    return;
  v63 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
    a2,
    &v63,
    0,
    (unsigned int)v5);
  v62 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
    a2,
    &v62,
    (unsigned int)(v8 + 1),
    (unsigned int)(*((_DWORD *)*a2 - 4) - v8 - 1));
  Str = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
    a2,
    &Str,
    (unsigned int)(v5 + 2),
    (unsigned int)(v8 - v5 - 2));
  v9 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&Str);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, v9);
  SubStr = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &SubStr,
    L"HKEY_LOCAL_MACHINE\\");
  v59 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v59,
    L"HKEY_CURRENT_USER\\");
  v58 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v58,
    L"HKEY_CLASSES_ROOT\\");
  if ( !SubStr )
    goto LABEL_15;
  v10 = Str;
  if ( *((int *)Str - 4) < 0 )
    goto LABEL_16;
  v11 = wcsstr(Str, SubStr);
  if ( !v11 )
  {
LABEL_15:
    v10 = Str;
    goto LABEL_16;
  }
  v10 = Str;
  if ( !(unsigned int)(v11 - Str) )
  {
    v12 = -2147483646;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      &Str,
      &v73,
      *((unsigned int *)SubStr - 4),
      (unsigned int)(*((_DWORD *)Str - 4) - *((_DWORD *)SubStr - 4)));
    ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, &v73);
    goto LABEL_26;
  }
LABEL_16:
  if ( v59 )
  {
    if ( *((int *)v10 - 4) >= 0 )
    {
      v13 = wcsstr(v10, v59);
      v10 = Str;
      if ( v13 )
      {
        if ( !(unsigned int)(v13 - Str) )
        {
          v12 = -2147483647;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
            &Str,
            &v73,
            *((unsigned int *)v59 - 4),
            (unsigned int)(*((_DWORD *)Str - 4) - *((_DWORD *)v59 - 4)));
          ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, &v73);
          goto LABEL_26;
        }
      }
    }
  }
  if ( v58 )
  {
    if ( *((int *)v10 - 4) >= 0 )
    {
      v14 = wcsstr(v10, v58);
      if ( v14 )
      {
        if ( !(unsigned int)(v14 - Str) )
        {
          v12 = 0xFFFFFFFF80000000uLL;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
            &Str,
            &v73,
            *((unsigned int *)v58 - 4),
            (unsigned int)(*((_DWORD *)Str - 4) - *((_DWORD *)v58 - 4)));
          ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, &v73);
LABEL_26:
          v15 = (_QWORD *)(v73 - 24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v73 - 24 + 16), 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
          }
          Src = 0;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &Src,
            &WindowName);
          v16 = *((int *)Str - 4);
          if ( (int)v16 < 0 )
            ATL::AtlThrowImpl(-2147024809);
          if ( Str[v16] == 92 )
          {
            v17 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                    &Str,
                    &v73,
                    (unsigned int)(v16 - 1));
            ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, v17);
          }
          else
          {
            v18 = wcsrchr(Str, 0x5Cu);
            if ( v18 )
              v19 = v18 - Str;
            else
              LODWORD(v19) = -1;
            v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                    &Str,
                    &v73,
                    (unsigned int)(*((_DWORD *)Str - 4) - v19 - 1));
            ATL::CSimpleStringT<unsigned short,0>::operator=(&Src, v20);
            v21 = (_QWORD *)(v73 - 24);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v73 - 24 + 16), 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
            }
            v22 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                    &Str,
                    &v73,
                    (unsigned int)v19);
            ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, v22);
          }
          v23 = (_QWORD *)(v73 - 24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v73 - 24 + 16), 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
          }
          v24 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 80));
          LOBYTE(v73) = v24;
          LODWORD(v74) = 260;
          Instance = ATL::CAtlStringMgr::GetInstance();
          if ( !Instance )
            ATL::AtlThrowImpl(-2147467259);
          v26 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                                   + 24);
          v65 = v26;
          hKey[0] = 0;
          hKey[1] = 0;
          v68 = 0;
          v27 = Str;
          Block = v70;
          if ( Str )
          {
            v28 = -1;
            do
              ++v28;
            while ( Str[v28] );
            v29 = v28 + 1;
            ATL::AtlConvAllocMemory<unsigned short>(&Block, v29, v70);
            if ( 2LL * (int)v29 )
            {
              if ( !Block )
              {
                *_errno() = 22;
                _invalid_parameter_noinfo();
                ATL::AtlThrowImpl(-2147024809);
              }
              _mm_lfence();
              memcpy_0(Block, v27, 2LL * (int)v29);
            }
          }
          else
          {
            Block = 0;
          }
          ATL::CRegKey::Open((ATL::CRegKey *)hKey, (HKEY)v12, (const unsigned __int16 *)Block, 0x20019u);
          if ( Block != v70 )
            free(Block);
          v30 = Src;
          v71 = (unsigned __int16 *)v72;
          if ( Src )
          {
            v31 = -1;
            do
              ++v31;
            while ( *((_WORD *)Src + v31) );
            v32 = v31 + 1;
            ATL::AtlConvAllocMemory<unsigned short>(&v71, v32, v72);
            if ( 2LL * (int)v32 )
            {
              if ( !v71 )
              {
                *_errno() = 22;
                _invalid_parameter_noinfo();
                ATL::AtlThrowImpl(-2147024809);
              }
              _mm_lfence();
              memcpy_0(v71, v30, 2LL * (int)v32);
            }
          }
          else
          {
            v71 = 0;
          }
          v33 = v71;
          if ( ((1 - *((_DWORD *)v26 - 2)) | (*((_DWORD *)v26 - 3) - 260)) < 0 )
          {
            _mm_lfence();
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v65, 260);
            v26 = v65;
          }
          StringValue = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, v33, v26, (unsigned int *)&v74);
          if ( v71 != (unsigned __int16 *)v72 )
            free(v71);
          if ( StringValue )
          {
            v43 = ATL::CAtlStringMgr::GetInstance();
            if ( !v43 )
              ATL::AtlThrowImpl(-2147467259);
            v44 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v43 + 24LL))(v43) + 24;
            v66 = v44;
            v45 = ATL::CAtlStringMgr::GetInstance();
            if ( !v45 )
              ATL::AtlThrowImpl(-2147467259);
            v74 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v45 + 24LL))(v45) + 24;
            if ( v12 == -2147483646 )
            {
              p_SubStr = &SubStr;
            }
            else if ( v12 == -2147483647 )
            {
              p_SubStr = &v59;
            }
            else
            {
              p_SubStr = &v58;
            }
            ATL::CSimpleStringT<unsigned short,0>::operator=(&v74, p_SubStr);
            if ( CLogger::ms_bLoggingOn )
            {
              v47 = ATL::CAtlStringMgr::GetInstance();
              if ( !v47 )
                ATL::AtlThrowImpl(-2147467259);
              v64 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v47 + 24LL))(v47)
                                       + 24);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v64,
                L"%s at key %s\\%s",
                Src,
                v74,
                Str);
              v48 = v64;
              CLogger::LogWarn(L"Cannot query the value", 0, v64);
              if ( _InterlockedDecrement((volatile signed __int32 *)v48 - 2) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v48 - 3) + 8LL))(*((_QWORD *)v48 - 3));
              }
            }
            v49 = (_QWORD *)(v74 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v74 - 24 + 16)) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v49 + 8LL))(*v49);
            }
            v42 = (__int64 *)(v44 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v44 - 24 + 16)) > 0 )
              goto LABEL_87;
            _mm_lfence();
            v41 = *v42;
          }
          else
          {
            v35 = v74 - 1;
            if ( !(_DWORD)v74 )
              v35 = wcsnlen(v26, *((int *)v26 - 3));
            if ( v35 < 0 || v35 > *((_DWORD *)v26 - 3) )
              ATL::AtlThrowImpl(-2147024809);
            *((_DWORD *)v26 - 4) = v35;
            v26[v35] = 0;
            v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v26 - 12);
            v74 = v36 + 24;
            v37 = ATL::operator+(&v66, &v63, &v74);
            v38 = ATL::operator+(&v64, v37, &v62);
            ATL::CSimpleStringT<unsigned short,0>::operator=(a2, v38);
            v39 = v64 - 12;
            if ( _InterlockedDecrement((volatile signed __int32 *)v64 - 2) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 8LL))(*(_QWORD *)v39);
            }
            v40 = (_QWORD *)(v66 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
            }
            if ( _InterlockedDecrement((volatile signed __int32 *)(v36 + 16)) > 0 )
              goto LABEL_87;
            _mm_lfence();
            v41 = *(_QWORD *)v36;
            v42 = (__int64 *)v36;
          }
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 8LL))(v41, v42);
LABEL_87:
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
          if ( _InterlockedDecrement((volatile signed __int32 *)v26 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 - 3) + 8LL))(*((_QWORD *)v26 - 3));
          }
          if ( v24 )
            RevertToSelf();
          v50 = (char *)Src - 24;
          if ( _InterlockedDecrement((volatile signed __int32 *)Src - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v50 + 8LL))(*v50);
          }
          goto LABEL_96;
        }
      }
    }
  }
  CLogger::LogWarn(L"PkgDef: Unknown root key", 0, *a2);
LABEL_96:
  v51 = v58 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 8LL))(*(_QWORD *)v51);
  }
  v52 = v59 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v59 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v52 + 8LL))(*(_QWORD *)v52);
  }
  v53 = SubStr - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)SubStr - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 8LL))(*(_QWORD *)v53);
  }
  v54 = Str - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)Str - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v54 + 8LL))(*(_QWORD *)v54);
  }
  v55 = (_QWORD *)(v62 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v62 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v55 + 8LL))(*v55);
  }
  v56 = (_QWORD *)(v63 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v63 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v56 + 8LL))(*v56);
  }
}

```

## disassembly

```asm
0x140022e40  mov     [rsp-8+arg_0], rbx
0x140022e45  push    rbp
0x140022e46  push    rsi
0x140022e47  push    rdi
0x140022e48  push    r12
0x140022e4a  push    r13
0x140022e4c  push    r14
0x140022e4e  push    r15
0x140022e50  lea     rbp, [rsp-1C0h]
0x140022e58  sub     rsp, 2C0h
0x140022e5f  mov     rsi, rdx
0x140022e62  mov     r14, rcx
0x140022e65  xor     r12d, r12d
0x140022e68  mov     rcx, [rdx]; Str
0x140022e6b  cmp     [rcx-10h], r12d
0x140022e6f  jl      loc_14002377F
0x140022e75  lea     rdx, asc_1400775AC; "$="
0x140022e7c  call    cs:__imp_wcsstr
0x140022e82  mov     rdi, rax
0x140022e85  test    rax, rax
0x140022e88  jz      loc_14002377F
0x140022e8e  sub     rdi, [rsi]
0x140022e91  sar     rdi, 1
0x140022e94  or      r15, 0FFFFFFFFFFFFFFFFh
0x140022e98  cmp     edi, r15d
0x140022e9b  jz      loc_14002377F
0x140022ea1  lea     ecx, [rdi+1]
0x140022ea4  mov     rax, [rsi]
0x140022ea7  test    ecx, ecx
0x140022ea9  js      short loc_140022EDA
0x140022eab  cmp     ecx, [rax-10h]
0x140022eae  jg      short loc_140022EDA
0x140022eb0  lfence
0x140022eb3  movsxd  rcx, ecx
0x140022eb6  mov     rax, [rsi]
0x140022eb9  lea     rcx, [rax+rcx*2]; Str
0x140022ebd  lea     rdx, asc_140083FEC; "$"
0x140022ec4  call    cs:__imp_wcsstr
0x140022eca  mov     rbx, rax
0x140022ecd  test    rax, rax
0x140022ed0  jz      short loc_140022EDA
0x140022ed2  sub     rbx, [rsi]
0x140022ed5  sar     rbx, 1
0x140022ed8  jmp     short loc_140022EDD
0x140022eda  mov     ebx, r15d
0x140022edd  cmp     ebx, r15d
0x140022ee0  jz      loc_14002377F
0x140022ee6  mov     [rsp+2F0h+var_290], r12
0x140022eeb  mov     r9d, edi
0x140022eee  xor     r8d, r8d
0x140022ef1  lea     rdx, [rsp+2F0h+var_290]
0x140022ef6  mov     rcx, rsi
0x140022ef9  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140022efe  mov     [rsp+2F0h+var_298], r12
0x140022f03  mov     rax, [rsi]
0x140022f06  mov     r9d, [rax-10h]
0x140022f0a  sub     r9d, ebx
0x140022f0d  mov     r13d, 1
0x140022f13  sub     r9d, r13d
0x140022f16  lea     r8d, [rbx+1]
0x140022f1a  lea     rdx, [rsp+2F0h+var_298]
0x140022f1f  mov     rcx, rsi
0x140022f22  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140022f27  mov     [rsp+2F0h+Str], r12
0x140022f2c  sub     ebx, edi
0x140022f2e  lea     r9d, [rbx-2]
0x140022f32  lea     r8d, [rdi+2]
0x140022f36  lea     rdx, [rsp+2F0h+Str]
0x140022f3b  mov     rcx, rsi
0x140022f3e  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140022f43  lea     rcx, [rsp+2F0h+Str]
0x140022f48  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x140022f4d  mov     rdx, rax
0x140022f50  lea     rcx, [rsp+2F0h+Str]
0x140022f55  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140022f5a  mov     [rsp+2F0h+SubStr], r12
0x140022f5f  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\"
0x140022f66  lea     rcx, [rsp+2F0h+SubStr]
0x140022f6b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140022f70  nop
0x140022f71  nop     dword ptr [rax+00h]
0x140022f75  nop     word ptr [rax+rax+00000000h]
0x140022f80  mov     [rsp+2F0h+var_2B0], r12
0x140022f85  lea     rdx, aHkeyCurrentUse_1; "HKEY_CURRENT_USER\\"
0x140022f8c  lea     rcx, [rsp+2F0h+var_2B0]
0x140022f91  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140022f96  nop
0x140022f97  mov     [rsp+2F0h+var_2B8], r12
0x140022f9c  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT\\"
0x140022fa3  lea     rcx, [rsp+2F0h+var_2B8]
0x140022fa8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140022fad  nop
0x140022fae  mov     rdx, [rsp+2F0h+SubStr]; SubStr
0x140022fb3  test    rdx, rdx
0x140022fb6  jz      short loc_14002301D
0x140022fb8  mov     rcx, [rsp+2F0h+Str]; Str
0x140022fbd  cmp     [rcx-10h], r12d
0x140022fc1  jl      short loc_140023022
0x140022fc3  call    cs:__imp_wcsstr
0x140022fc9  test    rax, rax
0x140022fcc  jz      short loc_14002301D
0x140022fce  mov     rcx, [rsp+2F0h+Str]
0x140022fd3  sub     rax, rcx
0x140022fd6  sar     rax, 1
0x140022fd9  test    eax, eax
0x140022fdb  jnz     short loc_140023022
0x140022fdd  mov     r15, 0FFFFFFFF80000002h
0x140022fe4  mov     rax, [rsp+2F0h+SubStr]
0x140022fe9  mov     r8d, [rax-10h]
0x140022fed  mov     r9d, [rcx-10h]
0x140022ff1  sub     r9d, r8d
0x140022ff4  lea     rdx, [rbp+1F0h+arg_10]
0x140022ffb  lea     rcx, [rsp+2F0h+Str]
0x140023000  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140023005  nop
0x140023006  lea     rdx, [rbp+1F0h+arg_10]
0x14002300d  lea     rcx, [rsp+2F0h+Str]
0x140023012  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140023017  nop
0x140023018  jmp     loc_1400230FE
0x14002301d  mov     rcx, [rsp+2F0h+Str]; Str
0x140023022  mov     rdx, [rsp+2F0h+var_2B0]; SubStr
0x140023027  test    rdx, rdx
0x14002302a  jz      short loc_140023089
0x14002302c  cmp     [rcx-10h], r12d
0x140023030  jl      short loc_140023089
0x140023032  call    cs:__imp_wcsstr
0x140023038  mov     rcx, [rsp+2F0h+Str]
0x14002303d  test    rax, rax
0x140023040  jz      short loc_140023089
0x140023042  sub     rax, rcx
0x140023045  sar     rax, 1
0x140023048  test    eax, eax
0x14002304a  jnz     short loc_140023089
0x14002304c  mov     r15, 0FFFFFFFF80000001h
0x140023053  mov     rax, [rsp+2F0h+var_2B0]
0x140023058  mov     r8d, [rax-10h]
0x14002305c  mov     r9d, [rcx-10h]
0x140023060  sub     r9d, r8d
0x140023063  lea     rdx, [rbp+1F0h+arg_10]
0x14002306a  lea     rcx, [rsp+2F0h+Str]
0x14002306f  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140023074  nop
0x140023075  lea     rdx, [rbp+1F0h+arg_10]
0x14002307c  lea     rcx, [rsp+2F0h+Str]
0x140023081  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140023086  nop
0x140023087  jmp     short loc_1400230FE
0x140023089  mov     rdx, [rsp+2F0h+var_2B8]; SubStr
0x14002308e  test    rdx, rdx
0x140023091  jz      loc_140023690
0x140023097  cmp     [rcx-10h], r12d
0x14002309b  jl      loc_140023690
0x1400230a1  call    cs:__imp_wcsstr
0x1400230a7  test    rax, rax
0x1400230aa  jz      loc_140023690
0x1400230b0  mov     rcx, [rsp+2F0h+Str]
0x1400230b5  sub     rax, rcx
0x1400230b8  sar     rax, 1
0x1400230bb  test    eax, eax
0x1400230bd  jnz     loc_140023690
0x1400230c3  mov     r15, 0FFFFFFFF80000000h
0x1400230ca  mov     rax, [rsp+2F0h+var_2B8]
0x1400230cf  mov     r8d, [rax-10h]
0x1400230d3  mov     r9d, [rcx-10h]
0x1400230d7  sub     r9d, r8d
0x1400230da  lea     rdx, [rbp+1F0h+arg_10]
0x1400230e1  lea     rcx, [rsp+2F0h+Str]
0x1400230e6  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1400230eb  nop
0x1400230ec  lea     rdx, [rbp+1F0h+arg_10]
0x1400230f3  lea     rcx, [rsp+2F0h+Str]
0x1400230f8  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400230fd  nop
0x1400230fe  mov     rdx, [rbp+1F0h+arg_10]
0x140023105  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140023109  or      eax, 0FFFFFFFFh
0x14002310c  lock xadd [rdx+10h], eax
0x140023111  sub     eax, 1
0x140023114  jg      short loc_140023122
0x140023116  lfence
0x140023119  mov     rcx, [rdx]
0x14002311c  mov     rax, [rcx]
0x14002311f  call    qword ptr [rax+8]
0x140023122  mov     [rsp+2F0h+Src], r12
0x140023127  lea     rdx, WindowName
0x14002312e  lea     rcx, [rsp+2F0h+Src]
0x140023133  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140023138  nop
0x140023139  mov     rcx, [rsp+2F0h+Str]; Str
0x14002313e  movsxd  r8, dword ptr [rcx-10h]
0x140023142  test    r8d, r8d
0x140023145  js      loc_14002379A
0x14002314b  mov     edx, 5Ch ; '\'; Ch
0x140023150  cmp     [rcx+r8*2], dx
0x140023155  jnz     short loc_14002317F
0x140023157  dec     r8d
0x14002315a  lea     rdx, [rbp+1F0h+arg_10]
0x140023161  lea     rcx, [rsp+2F0h+Str]
0x140023166  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x14002316b  nop
0x14002316c  mov     rdx, rax
0x14002316f  lea     rcx, [rsp+2F0h+Str]
0x140023174  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140023179  nop
0x14002317a  jmp     loc_14002320E
0x14002317f  call    cs:__imp_wcsrchr
0x140023185  mov     rbx, rax
0x140023188  mov     rcx, [rsp+2F0h+Str]
0x14002318d  test    rax, rax
0x140023190  jnz     short loc_140023197
0x140023192  or      ebx, 0FFFFFFFFh
0x140023195  jmp     short loc_14002319D
0x140023197  sub     rbx, rcx
0x14002319a  sar     rbx, 1
0x14002319d  mov     r8d, [rcx-10h]
0x1400231a1  sub     r8d, ebx
0x1400231a4  sub     r8d, r13d
0x1400231a7  lea     rdx, [rbp+1F0h+arg_10]
0x1400231ae  lea     rcx, [rsp+2F0h+Str]
0x1400231b3  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x1400231b8  nop
0x1400231b9  mov     rdx, rax
0x1400231bc  lea     rcx, [rsp+2F0h+Src]
0x1400231c1  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400231c6  nop
0x1400231c7  mov     rdx, [rbp+1F0h+arg_10]
0x1400231ce  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400231d2  or      eax, 0FFFFFFFFh
0x1400231d5  lock xadd [rdx+10h], eax
0x1400231da  sub     eax, 1
0x1400231dd  jg      short loc_1400231EB
0x1400231df  lfence
0x1400231e2  mov     rcx, [rdx]
0x1400231e5  mov     rax, [rcx]
0x1400231e8  call    qword ptr [rax+8]
0x1400231eb  mov     r8d, ebx
0x1400231ee  lea     rdx, [rbp+1F0h+arg_10]
0x1400231f5  lea     rcx, [rsp+2F0h+Str]
0x1400231fa  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x1400231ff  nop
0x140023200  mov     rdx, rax
0x140023203  lea     rcx, [rsp+2F0h+Str]
0x140023208  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002320d  nop
0x14002320e  mov     rdx, [rbp+1F0h+arg_10]
0x140023215  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140023219  or      eax, 0FFFFFFFFh
0x14002321c  lock xadd [rdx+10h], eax
0x140023221  sub     eax, 1
0x140023224  jg      short loc_140023232
0x140023226  lfence
0x140023229  mov     rcx, [rdx]
0x14002322c  mov     rax, [rcx]
0x14002322f  call    qword ptr [rax+8]
0x140023232  mov     rcx, [r14+50h]; hToken
0x140023236  call    cs:__imp_ImpersonateLoggedOnUser
0x14002323c  test    eax, eax
0x14002323e  setnz   r14b
0x140023242  mov     byte ptr [rbp+1F0h+arg_10], r14b
0x140023249  mov     dword ptr [rbp+1F0h+arg_18], 104h
0x140023253  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140023258  mov     rcx, rax
0x14002325b  test    rax, rax
0x14002325e  jz      loc_1400237A9
0x140023264  mov     rax, [rax]
0x140023267  call    qword ptr [rax+18h]
0x14002326a  lea     rdi, [rax+18h]
0x14002326e  mov     [rsp+2F0h+var_280], rdi
0x140023273  xorps   xmm0, xmm0
0x140023276  movups  xmmword ptr [rbp+1F0h+hKey], xmm0
0x14002327a  mov     [rbp+1F0h+hKey], r12
0x14002327e  mov     dword ptr [rbp+1F0h+hKey+8], r12d
0x140023282  mov     [rbp+1F0h+var_260], r12
0x140023286  mov     r12, [rsp+2F0h+Str]
0x14002328b  lea     rax, [rbp+1F0h+var_248]
0x14002328f  mov     [rbp+1F0h+Block], rax
0x140023293  xor     eax, eax
0x140023295  test    r12, r12
0x140023298  jnz     short loc_1400232A0
0x14002329a  mov     [rbp+1F0h+Block], rax
0x14002329e  jmp     short loc_1400232E3
0x1400232a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400232a4  inc     rbx
0x1400232a7  cmp     [r12+rbx*2], ax
0x1400232ac  jnz     short loc_1400232A4
0x1400232ae  add     ebx, r13d
0x1400232b1  lea     r8, [rbp+1F0h+var_248]
0x1400232b5  mov     edx, ebx
0x1400232b7  lea     rcx, [rbp+1F0h+Block]
0x1400232bb  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x1400232c0  movsxd  r8, ebx
0x1400232c3  add     r8, r8; Size
0x1400232c6  jz      short loc_1400232E3
0x1400232c8  xor     eax, eax
0x1400232ca  cmp     [rbp+1F0h+Block], rax
0x1400232ce  jz      loc_1400237B7
0x1400232d4  lfence
0x1400232d7  mov     rdx, r12; Src
0x1400232da  mov     rcx, [rbp+1F0h+Block]; void *
  ... truncated ...
```
