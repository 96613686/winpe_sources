# CPkgDefProcessor::Process(void)

- ea: `0x14001eda0`
- end: `0x14001f6b3`
- name: `?Process@CPkgDefProcessor@@QEAAJXZ`
- size: `2323`
- prototype: `__int64 __fastcall(CPkgDefProcessor *__hidden this)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140018048`
- `0x14004772c`
- `0x1400480b0`

## callees

- `0x140001020`
- `0x140002190`
- `0x140002196`
- `0x140002c10`
- `0x140003ec0`
- `0x140004950`
- `0x14000b710`
- `0x14000fea0`
- `0x140014910`
- `0x140016d4c`
- `0x14001eda0`
- `0x14001f6b4`
- `0x140033090`
- `0x140033ab0`
- `0x14004a140`
- `0x14004c80c`
- `0x14004c93c`
- `0x14004c950`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14001f554`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14001f5eb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14001f5f2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14001f554`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14001f5eb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x14001f5f2`
- `ole32!CLSIDFromString` at `0x14001f0c7`
- `ole32!CLSIDFromString` at `0x14001f0c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CPkgDefProcessor::Process(CPkgDefProcessor *this)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v3; // rax
  struct ATL::IAtlStringMgr *v4; // rax
  wchar_t *v5; // rsi
  struct ATL::IAtlStringMgr *v6; // rax
  __int64 v7; // rbx
  struct ATL::IAtlStringMgr *v8; // rax
  __int64 v9; // rdi
  int v10; // eax
  unsigned __int16 *v11; // rax
  int v12; // edx
  int v13; // ecx
  unsigned __int16 *v14; // rax
  int v15; // ecx
  __int64 v16; // r8
  __int64 v17; // r8
  unsigned __int64 v18; // r13
  char *v19; // r14
  void **v20; // r8
  char *v21; // r9
  char *v22; // rax
  char *i; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // r10
  void **v26; // rdx
  __int64 v27; // rcx
  unsigned __int64 first_of; // r15
  __int64 v29; // r8
  __int64 v30; // r9
  unsigned __int64 v31; // rdx
  __int128 *v32; // rax
  const OLECHAR *v33; // rcx
  __int64 v34; // rcx
  CLSID *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  OLECHAR *v37; // rcx
  int v38; // r15d
  const struct std::nothrow_t *v39; // rdx
  char *v40; // rax
  const struct std::nothrow_t *v41; // rdx
  void *v42; // rcx
  int v43; // eax
  _WORD *v44; // r8
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r8
  _QWORD *v48; // r14
  _QWORD *v49; // rdx
  unsigned __int64 v50; // r15
  wchar_t *v51; // r14
  wchar_t *v52; // rax
  char *v53; // r13
  const wchar_t *v54; // r8
  int v55; // eax
  int v56; // edx
  __int64 v57; // rdx
  _QWORD *v58; // rcx
  _QWORD *v59; // r14
  const struct std::nothrow_t *v60; // rdx
  const struct std::nothrow_t *v62; // rdx
  char *v63; // rax
  const struct std::nothrow_t *v64; // rdx
  void *v65; // rcx
  __int64 v66; // rdx
  _QWORD *v67; // rcx
  _QWORD *v68; // r14
  int v69; // [rsp+28h] [rbp-E0h]
  __int64 v70; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v71; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *v72; // [rsp+40h] [rbp-C8h]
  char *v73; // [rsp+48h] [rbp-C0h]
  __int64 v74; // [rsp+58h] [rbp-B0h] BYREF
  _WORD *v75; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+68h] [rbp-A0h]
  __int64 v77; // [rsp+70h] [rbp-98h] BYREF
  wchar_t *Destination; // [rsp+78h] [rbp-90h]
  int v79; // [rsp+80h] [rbp-88h]
  int v80; // [rsp+84h] [rbp-84h]
  __int128 v81; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v82; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v83; // [rsp+B0h] [rbp-58h]
  __int128 v84; // [rsp+B8h] [rbp-50h] BYREF
  __int64 Block; // [rsp+C8h] [rbp-40h]
  void *Block_8[2]; // [rsp+D0h] [rbp-38h]
  __int64 v87; // [rsp+E0h] [rbp-28h]
  LPCOLESTR lpsz[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v89; // [rsp+F8h] [rbp-10h]
  unsigned __int64 v90; // [rsp+100h] [rbp-8h]
  wchar_t *v91; // [rsp+108h] [rbp+0h]
  void *v92[2]; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int64 v93; // [rsp+120h] [rbp+18h]
  unsigned __int64 v94; // [rsp+128h] [rbp+20h]
  CLSID pclsid; // [rsp+130h] [rbp+28h] BYREF

  v69 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance
    || (v74 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24,
        (v3 = ATL::CAtlStringMgr::GetInstance()) == 0)
    || (v75 = (_WORD *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v3 + 24LL))(v3) + 24),
        (v4 = ATL::CAtlStringMgr::GetInstance()) == 0) )
  {
    ATL::AtlThrowImpl(-2147467259);
  }
  v77 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v4 + 24LL))(v4) + 24;
  v80 = 0x10000;
  v5 = (wchar_t *)operator new[](0x10000u);
  v91 = v5;
  Destination = v5;
  v6 = ATL::CAtlStringMgr::GetInstance();
  if ( !v6 )
    ATL::AtlThrowImpl(-2147467259);
  v7 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v6 + 24LL))(v6) + 24;
  v70 = v7;
  v8 = ATL::CAtlStringMgr::GetInstance();
  if ( !v8 )
    ATL::AtlThrowImpl(-2147467259);
  v9 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v8 + 24LL))(v8) + 24;
  v71 = v9;
  v10 = (*(__int64 (__fastcall **)(CPkgDefProcessor *, __int64 *))(*(_QWORD *)this + 16LL))(this, &v74);
  if ( v10 < 0 )
  {
LABEL_102:
    v38 = 0;
    if ( v10 != -2147024858 )
      v38 = v10;
    if ( v38 >= 0 && *(_DWORD *)(v7 - 16) )
    {
      _mm_lfence();
      v38 = (*(__int64 (__fastcall **)(CPkgDefProcessor *))(*(_QWORD *)this + 32LL))(this);
    }
    goto LABEL_107;
  }
  _mm_lfence();
  while ( 1 )
  {
    if ( !v9 )
LABEL_135:
      ATL::AtlThrowImpl(-2147467259);
    v11 = (unsigned __int16 *)v74;
    do
    {
      v12 = *(unsigned __int16 *)((char *)v11 + v9 - v74);
      v13 = *v11 - v12;
      if ( v13 )
        break;
      ++v11;
    }
    while ( v12 );
    if ( !v13 )
      goto LABEL_101;
    if ( !v7 )
      goto LABEL_135;
    v14 = (unsigned __int16 *)v74;
    do
    {
      v15 = *(unsigned __int16 *)((char *)v14 + v7 - v74);
      v16 = (unsigned int)*v14 - v15;
      LODWORD(v72) = v16;
      if ( (_DWORD)v16 )
        break;
      ++v14;
    }
    while ( v15 );
    if ( (_DWORD)v16 )
      break;
LABEL_67:
    CMultiReplacer::ReplaceAll((char *)this + 88, &v74, v16);
    if ( !(_DWORD)v72 )
      goto LABEL_73;
    if ( !(*(unsigned int (__fastcall **)(CPkgDefProcessor *, __int64 *))(*(_QWORD *)this + 56LL))(this, &v74) )
      goto LABEL_72;
    v38 = (*(__int64 (__fastcall **)(CPkgDefProcessor *, __int64 *))(*(_QWORD *)this + 48LL))(this, &v74);
    if ( v38 < 0 )
      goto LABEL_107;
    _mm_lfence();
    v43 = (*(__int64 (__fastcall **)(CPkgDefProcessor *, __int64 *))(*(_QWORD *)this + 24LL))(this, &v74);
    v38 = v43;
    if ( v43 < 0 )
      goto LABEL_107;
    if ( v43 == 1 )
    {
LABEL_72:
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v71, &v70);
      v9 = v71;
    }
    else
    {
LABEL_73:
      v44 = v75;
      if ( *((_DWORD *)v75 - 4) )
      {
        v45 = *((_QWORD *)this + 24);
        if ( !v45 || (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 24LL))(v45, v74) )
        {
          CMultiReplacer::ReplaceAll((char *)this + 88, &v75, v44);
          if ( *v75 == 64 && !v75[1] )
            ATL::CSimpleStringT<unsigned short,0>::Empty(&v75);
          if ( (unsigned int)v76 < 2 )
          {
            CMultiReplacer::ReplaceAll((char *)this + 88, &v77, v46);
          }
          else if ( (_DWORD)v76 == 2 )
          {
            v84 = 0;
            Block = 0;
            *(_OWORD *)Block_8 = 0;
            v87 = 10;
            v38 = ConvertNullTerminatedStringArrayToAtlList(Destination, &v84);
            if ( v38 < 0 )
              goto LABEL_131;
            v48 = (_QWORD *)v84;
            if ( (_QWORD)v84 )
            {
              do
              {
                v49 = v48;
                v48 = (_QWORD *)*v48;
                CMultiReplacer::ReplaceAll((char *)this + 88, v49 + 2, v47);
              }
              while ( v48 );
              v5 = v91;
            }
            v50 = (unsigned __int64)v80 >> 1;
            v51 = Destination;
            if ( !Destination )
            {
LABEL_127:
              v38 = -2147024809;
LABEL_131:
              while ( Block )
              {
                v66 = v84;
                if ( !(_QWORD)v84 )
LABEL_140:
                  ATL::AtlThrowImpl(-2147467259);
                *(_QWORD *)&v84 = *(_QWORD *)v84;
                ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::FreeNode(
                  &v84,
                  v66);
              }
              v84 = 0;
              Block_8[1] = 0;
              v67 = Block_8[0];
              if ( Block_8[0] )
              {
                do
                {
                  v68 = (_QWORD *)*v67;
                  free_0(v67);
                  v67 = v68;
                }
                while ( v68 );
              }
              goto LABEL_107;
            }
            v52 = Destination;
            v72 = Destination;
            v53 = (char *)v84;
            if ( (_QWORD)v84 )
            {
              while ( 1 )
              {
                v73 = v53;
                v53 = *(char **)v53;
                v54 = (const wchar_t *)*((_QWORD *)v73 + 2);
                v55 = *((_DWORD *)v54 - 4);
                if ( !v55 )
                  goto LABEL_127;
                if ( v55 + 2 > (int)v50 )
                  break;
                if ( wcscpy_s_0(v51, (int)v50, v54) )
                {
                  v38 = -2147467259;
                  goto LABEL_131;
                }
                v56 = *(_DWORD *)(*((_QWORD *)v73 + 2) - 16LL);
                v51 += v56 + 1;
                LODWORD(v50) = -1 - v56 + v50;
                if ( !v53 )
                {
                  v52 = v72;
                  goto LABEL_92;
                }
              }
              v38 = -2147024774;
              goto LABEL_131;
            }
LABEL_92:
            *v51 = 0;
            v79 = 2 * (v51 + 1 - v52);
            while ( Block )
            {
              v57 = v84;
              if ( !(_QWORD)v84 )
                goto LABEL_140;
              *(_QWORD *)&v84 = *(_QWORD *)v84;
              ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::FreeNode(
                &v84,
                v57);
            }
            v84 = 0;
            Block_8[1] = 0;
            v58 = Block_8[0];
            if ( Block_8[0] )
            {
              do
              {
                v59 = (_QWORD *)*v58;
                free_0(v58);
                v58 = v59;
              }
              while ( v59 );
            }
          }
          v38 = (*(__int64 (__fastcall **)(CPkgDefProcessor *, __int64 *))(*(_QWORD *)this + 40LL))(this, &v74);
          if ( v38 < 0 )
            goto LABEL_107;
        }
      }
    }
LABEL_101:
    v10 = (*(__int64 (__fastcall **)(CPkgDefProcessor *, __int64 *))(*(_QWORD *)this + 16LL))(this, &v74);
    if ( v10 < 0 )
      goto LABEL_102;
  }
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(v74 + 2 * v17) );
  std::wstring::_Construct<1,unsigned short const *>(&v81, v74, v17);
  *(_OWORD *)v92 = 0;
  v93 = 0;
  v94 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v92, L"$RootKey$\\Packages\\{", 20);
  v18 = v94;
  v19 = (char *)v92[0];
  if ( *((_QWORD *)this + 25) )
  {
    v20 = v92;
    if ( v94 > 7 )
      v20 = (void **)v92[0];
    v21 = (char *)&v81;
    if ( v83 > 7 )
      v21 = (char *)v81;
    if ( v93 > v82 )
    {
      v27 = -1;
LABEL_39:
      if ( v27 )
        goto LABEL_55;
    }
    else if ( v93 )
    {
      v22 = &v21[2 * (v82 - v93) + 2];
      v73 = v22;
      for ( i = v21; ; i += 2 )
      {
        v24 = (v22 - i) >> 1;
        if ( !v24 )
          break;
        while ( *(_WORD *)i != *(_WORD *)v20 )
        {
          i += 2;
          if ( !--v24 )
            goto LABEL_55;
        }
        if ( !i )
          break;
        v25 = v93;
        v26 = v20;
        while ( *(_WORD *)((char *)v26 + i - (char *)v20) == *(_WORD *)v26 )
        {
          v26 = (void **)((char *)v26 + 2);
          if ( !--v25 )
          {
            v27 = (i - v21) >> 1;
            goto LABEL_39;
          }
        }
        v22 = v73;
      }
      goto LABEL_55;
    }
    first_of = std::wstring::find_first_of(&v81, L"}", v20, v21);
    v31 = std::wstring::find_first_of(&v81, L"{", v29, v30);
    *(_OWORD *)lpsz = 0;
    v89 = 0;
    v90 = 0;
    if ( v82 < v31 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    _mm_lfence();
    if ( v82 - v31 < first_of )
      first_of = v82 - v31;
    v32 = &v81;
    if ( v83 > 7 )
      v32 = (__int128 *)v81;
    std::wstring::_Construct<1,unsigned short const *>(lpsz, (char *)v32 + 2 * v31, first_of);
    v69 |= 1u;
    v33 = (const OLECHAR *)lpsz;
    if ( v90 > 7 )
      v33 = lpsz[0];
    CLSIDFromString(v33, &pclsid);
    v34 = *((_QWORD *)this + 25);
    v35 = *(CLSID **)(v34 + 8);
    if ( v35 == *(CLSID **)(v34 + 16) )
    {
      std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v34, v35, &pclsid);
    }
    else
    {
      *v35 = pclsid;
      *(_QWORD *)(v34 + 8) += 16LL;
    }
    if ( v90 > 7 )
    {
      v36 = (const struct std::nothrow_t *)(2 * v90 + 2);
      v37 = (OLECHAR *)lpsz[0];
      if ( (unsigned __int64)v36 >= 0x1000 )
      {
        v36 = (const struct std::nothrow_t *)(2 * v90 + 41);
        v37 = (OLECHAR *)*((_QWORD *)lpsz[0] - 1);
        if ( (unsigned __int64)((char *)lpsz[0] - (char *)v37 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v37, v36);
    }
    v89 = 0;
    v90 = 7;
    LOWORD(lpsz[0]) = 0;
  }
LABEL_55:
  if ( !*(_DWORD *)(v7 - 16) )
    goto LABEL_58;
  v38 = (*(__int64 (__fastcall **)(CPkgDefProcessor *))(*(_QWORD *)this + 32LL))(this);
  if ( v38 < 0 )
    goto LABEL_114;
  if ( v38 != 1 )
  {
LABEL_58:
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v70, &v74);
    if ( v18 > 7 )
    {
      v39 = (const struct std::nothrow_t *)(2 * v18 + 2);
      v40 = v19;
      if ( (unsigned __int64)v39 >= 0x1000 )
      {
        v39 = (const struct std::nothrow_t *)(2 * v18 + 41);
        v19 = (char *)*((_QWORD *)v19 - 1);
        if ( (unsigned __int64)(v40 - v19 - 8) > 0x1F )
          goto LABEL_123;
      }
      operator delete(v19, v39);
    }
    if ( v83 > 7 )
    {
      v41 = (const struct std::nothrow_t *)(2 * v83 + 2);
      v42 = (void *)v81;
      if ( (unsigned __int64)v41 >= 0x1000 )
      {
        v41 = (const struct std::nothrow_t *)(2 * v83 + 41);
        v42 = *(void **)(v81 - 8);
        if ( (unsigned __int64)(v81 - (_QWORD)v42 - 8) > 0x1F )
          goto LABEL_124;
      }
      operator delete(v42, v41);
    }
    v82 = 0;
    v83 = 7;
    LOWORD(v81) = 0;
    v7 = v70;
    goto LABEL_67;
  }
  v38 = 0;
LABEL_114:
  if ( v18 > 7 )
  {
    v62 = (const struct std::nothrow_t *)(2 * v18 + 2);
    v63 = v19;
    if ( (unsigned __int64)v62 >= 0x1000 )
    {
      v62 = (const struct std::nothrow_t *)(2 * v18 + 41);
      v19 = (char *)*((_QWORD *)v19 - 1);
      if ( (unsigned __int64)(v63 - v19 - 8) > 0x1F )
LABEL_123:
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v19, v62);
  }
  if ( v83 > 7 )
  {
    v64 = (const struct std::nothrow_t *)(2 * v83 + 2);
    v65 = (void *)v81;
    if ( (unsigned __int64)v64 >= 0x1000 )
    {
      v64 = (const struct std::nothrow_t *)(2 * v83 + 41);
      v65 = *(void **)(v81 - 8);
      if ( (unsigned __int64)(v81 - (_QWORD)v65 - 8) > 0x1F )
LABEL_124:
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v65, v64);
  }
  v82 = 0;
  v83 = 7;
  LOWORD(v81) = 0;
LABEL_107:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
  }
  v60 = (const struct std::nothrow_t *)(v7 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v60 + 8LL))(*(_QWORD *)v60);
  }
  operator delete(v5, v60);
  PkgDefIO::PkgDefItem::~PkgDefItem((PkgDefIO::PkgDefItem *)&v74);
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x14001eda0  mov     rax, rsp
0x14001eda3  mov     [rax+10h], rbx
0x14001eda7  mov     [rax+18h], rsi
0x14001edab  mov     [rax+20h], rdi
0x14001edaf  push    rbp
0x14001edb0  push    r12
0x14001edb2  push    r13
0x14001edb4  push    r14
0x14001edb6  push    r15
0x14001edb8  lea     rbp, [rax-68h]
0x14001edbc  sub     rsp, 140h
0x14001edc3  mov     rax, cs:__security_cookie
0x14001edca  xor     rax, rsp
0x14001edcd  mov     [rbp+60h+var_28], rax
0x14001edd1  mov     r12, rcx
0x14001edd4  xor     r14d, r14d
0x14001edd7  mov     dword ptr [rsp+160h+var_140], r14d
0x14001eddc  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001ede1  mov     rcx, rax
0x14001ede4  test    rax, rax
0x14001ede7  jz      loc_14001F675
0x14001eded  mov     rax, [rax]
0x14001edf0  call    qword ptr [rax+18h]
0x14001edf3  add     rax, 18h
0x14001edf7  mov     [rsp+160h+var_110], rax
0x14001edfc  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001ee01  mov     rcx, rax
0x14001ee04  test    rax, rax
0x14001ee07  jz      loc_14001F675
0x14001ee0d  mov     rax, [rax]
0x14001ee10  call    qword ptr [rax+18h]
0x14001ee13  add     rax, 18h
0x14001ee17  mov     [rsp+160h+var_108], rax
0x14001ee1c  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001ee21  mov     rcx, rax
0x14001ee24  test    rax, rax
0x14001ee27  jz      loc_14001F675
0x14001ee2d  mov     rax, [rax]
0x14001ee30  call    qword ptr [rax+18h]
0x14001ee33  add     rax, 18h
0x14001ee37  mov     [rsp+160h+var_F8], rax
0x14001ee3c  mov     ecx, 10000h; unsigned __int64
0x14001ee41  mov     [rsp+160h+var_E4], ecx
0x14001ee45  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001ee4a  mov     rsi, rax
0x14001ee4d  mov     [rbp+60h+var_60], rax
0x14001ee51  mov     [rsp+160h+Destination], rax
0x14001ee56  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001ee5b  mov     rcx, rax
0x14001ee5e  test    rax, rax
0x14001ee61  jz      loc_14001F683
0x14001ee67  mov     rax, [rax]
0x14001ee6a  call    qword ptr [rax+18h]
0x14001ee6d  lea     rbx, [rax+18h]
0x14001ee71  mov     [rsp+160h+var_138], rbx
0x14001ee76  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001ee7b  mov     rcx, rax
0x14001ee7e  test    rax, rax
0x14001ee81  jz      loc_14001F691
0x14001ee87  mov     rax, [rax]
0x14001ee8a  call    qword ptr [rax+18h]
0x14001ee8d  lea     rdi, [rax+18h]
0x14001ee91  mov     [rsp+160h+var_130], rdi
0x14001ee96  mov     rax, [r12]
0x14001ee9a  lea     rdx, [rsp+160h+var_110]
0x14001ee9f  mov     rcx, r12
0x14001eea2  call    qword ptr [rax+10h]
0x14001eea5  test    eax, eax
0x14001eea7  js      loc_14001F4AE
0x14001eead  lfence
0x14001eeb0  test    rdi, rdi
0x14001eeb3  jz      loc_14001F665
0x14001eeb9  mov     r9, [rsp+160h+var_110]
0x14001eebe  mov     rax, r9
0x14001eec1  mov     r8, rdi
0x14001eec4  sub     r8, r9
0x14001eec7  movzx   ecx, word ptr [rax]
0x14001eeca  movzx   edx, word ptr [rax+r8]
0x14001eecf  sub     ecx, edx
0x14001eed1  jnz     short loc_14001EEDB
0x14001eed3  add     rax, 2
0x14001eed7  test    edx, edx
0x14001eed9  jnz     short loc_14001EEC7
0x14001eedb  test    ecx, ecx
0x14001eedd  jz      loc_14001F497
0x14001eee3  test    rbx, rbx
0x14001eee6  jz      loc_14001F665
0x14001eeec  mov     rax, r9
0x14001eeef  mov     rdx, rbx
0x14001eef2  sub     rdx, r9
0x14001eef5  movzx   r8d, word ptr [rax]
0x14001eef9  movzx   ecx, word ptr [rax+rdx]
0x14001eefd  sub     r8d, ecx
0x14001ef00  mov     dword ptr [rsp+160h+var_128], r8d
0x14001ef05  jnz     short loc_14001EF0F
0x14001ef07  add     rax, 2
0x14001ef0b  test    ecx, ecx
0x14001ef0d  jnz     short loc_14001EEF5
0x14001ef0f  test    r8d, r8d
0x14001ef12  jz      loc_14001F225
0x14001ef18  xorps   xmm0, xmm0
0x14001ef1b  movups  [rbp+60h+var_D0], xmm0
0x14001ef1f  mov     [rbp+60h+var_C0], r14
0x14001ef23  mov     [rbp+60h+var_B8], r14
0x14001ef27  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001ef2b  inc     r8
0x14001ef2e  cmp     [r9+r8*2], r14w
0x14001ef33  jnz     short loc_14001EF2B
0x14001ef35  mov     rdx, r9
0x14001ef38  lea     rcx, [rbp+60h+var_D0]
0x14001ef3c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001ef41  nop
0x14001ef42  xorps   xmm0, xmm0
0x14001ef45  movups  xmmword ptr [rbp+60h+var_58], xmm0
0x14001ef49  mov     [rbp+60h+var_48], r14
0x14001ef4d  mov     [rbp+60h+var_40], r14
0x14001ef51  mov     r8d, 14h
0x14001ef57  lea     rdx, aRootkeyPackage; "$RootKey$\\Packages\\{"
0x14001ef5e  lea     rcx, [rbp+60h+var_58]
0x14001ef62  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001ef67  nop
0x14001ef68  mov     r13, [rbp+60h+var_40]
0x14001ef6c  mov     r14, [rbp+60h+var_58]
0x14001ef70  xor     r11d, r11d
0x14001ef73  cmp     [r12+0C8h], r11
0x14001ef7b  jz      loc_14001F14C
0x14001ef81  lea     r8, [rbp+60h+var_58]
0x14001ef85  cmp     r13, 7
0x14001ef89  cmova   r8, r14
0x14001ef8d  lea     r9, [rbp+60h+var_D0]
0x14001ef91  cmp     [rbp+60h+var_B8], 7
0x14001ef96  cmova   r9, qword ptr [rbp+60h+var_D0]
0x14001ef9b  mov     r15, [rbp+60h+var_48]
0x14001ef9f  cmp     r15, [rbp+60h+var_C0]
0x14001efa3  ja      loc_14001F033
0x14001efa9  mov     rax, [rbp+60h+var_C0]
0x14001efad  sub     rax, r15
0x14001efb0  test    r15, r15
0x14001efb3  jz      loc_14001F040
0x14001efb9  inc     rax
0x14001efbc  lea     rax, [r9+rax*2]
0x14001efc0  mov     [rsp+160h+var_120], rax
0x14001efc5  mov     rcx, r9
0x14001efc8  sub     rax, rcx
0x14001efcb  sar     rax, 1
0x14001efce  jz      loc_14001F14C
0x14001efd4  movzx   edx, word ptr [r8]
0x14001efd8  cmp     [rcx], dx
0x14001efdb  jz      short loc_14001EFEC
0x14001efdd  add     rcx, 2
0x14001efe1  sub     rax, 1
0x14001efe5  jnz     short loc_14001EFD8
0x14001efe7  jmp     loc_14001F14C
0x14001efec  test    rcx, rcx
0x14001efef  jz      loc_14001F14C
0x14001eff5  mov     r10, r15
0x14001eff8  mov     rdx, r8
0x14001effb  test    r15, r15
0x14001effe  jz      short loc_14001F01D
0x14001f000  mov     r11, rcx
0x14001f003  sub     r11, r8
0x14001f006  movzx   eax, word ptr [rdx]
0x14001f009  cmp     [r11+rdx], ax
0x14001f00e  jnz     short loc_14001F025
0x14001f010  add     rdx, 2
0x14001f014  sub     r10, 1
0x14001f018  jnz     short loc_14001F006
0x14001f01a  xor     r11d, r11d
0x14001f01d  sub     rcx, r9
0x14001f020  sar     rcx, 1
0x14001f023  jmp     short loc_14001F037
0x14001f025  add     rcx, 2
0x14001f029  mov     rax, [rsp+160h+var_120]
0x14001f02e  xor     r11d, r11d
0x14001f031  jmp     short loc_14001EFC8
0x14001f033  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001f037  test    rcx, rcx
0x14001f03a  jnz     loc_14001F14C
0x14001f040  lea     rdx, asc_140084E54; "}"
0x14001f047  lea     rcx, [rbp+60h+var_D0]
0x14001f04b  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x14001f050  mov     r15, rax
0x14001f053  lea     rdx, asc_140084E58; "{"
0x14001f05a  lea     rcx, [rbp+60h+var_D0]
0x14001f05e  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x14001f063  mov     rdx, rax
0x14001f066  xorps   xmm0, xmm0
0x14001f069  movups  xmmword ptr [rbp+60h+lpsz], xmm0
0x14001f06d  xor     eax, eax
0x14001f06f  mov     [rbp+60h+var_70], rax
0x14001f073  mov     [rbp+60h+var_68], rax
0x14001f077  cmp     [rbp+60h+var_C0], rdx
0x14001f07b  jb      loc_14001F69F
0x14001f081  lfence
0x14001f084  mov     rcx, [rbp+60h+var_C0]
0x14001f088  sub     rcx, rdx
0x14001f08b  cmp     rcx, r15
0x14001f08e  cmovb   r15, rcx
0x14001f092  lea     rax, [rbp+60h+var_D0]
0x14001f096  cmp     [rbp+60h+var_B8], 7
0x14001f09b  cmova   rax, qword ptr [rbp+60h+var_D0]
0x14001f0a0  lea     rdx, [rax+rdx*2]
0x14001f0a4  mov     r8, r15
0x14001f0a7  lea     rcx, [rbp+60h+lpsz]
0x14001f0ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001f0b0  or      dword ptr [rsp+160h+var_140], 1
0x14001f0b5  lea     rcx, [rbp+60h+lpsz]
0x14001f0b9  cmp     [rbp+60h+var_68], 7
0x14001f0be  cmova   rcx, [rbp+60h+lpsz]; lpsz
0x14001f0c3  lea     rdx, [rbp+60h+pclsid]; pclsid
0x14001f0c7  call    cs:__imp_CLSIDFromString
0x14001f0cd  mov     rcx, [r12+0C8h]
0x14001f0d5  mov     rdx, [rcx+8]
0x14001f0d9  cmp     rdx, [rcx+10h]
0x14001f0dd  jz      short loc_14001F0EE
0x14001f0df  movups  xmm0, xmmword ptr [rbp+60h+pclsid.Data1]
0x14001f0e3  movdqu  xmmword ptr [rdx], xmm0
0x14001f0e7  add     qword ptr [rcx+8], 10h
0x14001f0ec  jmp     short loc_14001F0F8
0x14001f0ee  lea     r8, [rbp+60h+pclsid]
0x14001f0f2  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x14001f0f7  nop
0x14001f0f8  mov     rdx, [rbp+60h+var_68]
0x14001f0fc  cmp     rdx, 7
0x14001f100  jbe     short loc_14001F138
0x14001f102  lea     rdx, ds:2[rdx*2]
0x14001f10a  mov     rcx, [rbp+60h+lpsz]
0x14001f10e  mov     rax, rcx
0x14001f111  cmp     rdx, 1000h
0x14001f118  jb      short loc_14001F133
0x14001f11a  add     rdx, 27h ; '''; struct std::nothrow_t *
0x14001f11e  mov     rcx, [rcx-8]; void *
0x14001f122  sub     rax, rcx
0x14001f125  add     rax, 0FFFFFFFFFFFFFFF8h
0x14001f129  cmp     rax, 1Fh
0x14001f12d  ja      loc_14001F554
0x14001f133  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f138  xor     r11d, r11d
0x14001f13b  mov     [rbp+60h+var_70], r11
0x14001f13f  mov     [rbp+60h+var_68], 7
0x14001f147  mov     word ptr [rbp+60h+lpsz], r11w
0x14001f14c  cmp     [rbx-10h], r11d
0x14001f150  jz      short loc_14001F174
0x14001f152  mov     rax, [r12]
0x14001f156  mov     rcx, r12
0x14001f159  call    qword ptr [rax+20h]
0x14001f15c  mov     r15d, eax
0x14001f15f  xor     eax, eax
0x14001f161  test    r15d, r15d
0x14001f164  js      loc_14001F55E
0x14001f16a  cmp     r15d, 1
0x14001f16e  jz      loc_14001F55B
0x14001f174  lea     rdx, [rsp+160h+var_110]
0x14001f179  lea     rcx, [rsp+160h+var_138]
0x14001f17e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001f183  nop
0x14001f184  nop     dword ptr [rax+00h]
0x14001f188  nop     dword ptr [rax+rax+00000000h]
0x14001f190  cmp     r13, 7
0x14001f194  jbe     short loc_14001F1CC
0x14001f196  lea     rdx, ds:2[r13*2]
0x14001f19e  mov     rax, r14
0x14001f1a1  cmp     rdx, 1000h
0x14001f1a8  jb      short loc_14001F1C3
0x14001f1aa  add     rdx, 27h ; '''; struct std::nothrow_t *
0x14001f1ae  mov     r14, [r14-8]
0x14001f1b2  sub     rax, r14
0x14001f1b5  add     rax, 0FFFFFFFFFFFFFFF8h
0x14001f1b9  cmp     rax, 1Fh
0x14001f1bd  ja      loc_14001F5EB
0x14001f1c3  mov     rcx, r14; void *
0x14001f1c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f1cb  nop
0x14001f1cc  mov     rdx, [rbp+60h+var_B8]
0x14001f1d0  cmp     rdx, 7
0x14001f1d4  jbe     short loc_14001F20C
0x14001f1d6  lea     rdx, ds:2[rdx*2]
0x14001f1de  mov     rcx, qword ptr [rbp+60h+var_D0]
0x14001f1e2  mov     rax, rcx
0x14001f1e5  cmp     rdx, 1000h
0x14001f1ec  jb      short loc_14001F207
0x14001f1ee  add     rdx, 27h ; '''; struct std::nothrow_t *
0x14001f1f2  mov     rcx, [rcx-8]; void *
0x14001f1f6  sub     rax, rcx
0x14001f1f9  add     rax, 0FFFFFFFFFFFFFFF8h
0x14001f1fd  cmp     rax, 1Fh
0x14001f201  ja      loc_14001F5F2
0x14001f207  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f20c  xor     r14d, r14d
0x14001f20f  mov     [rbp+60h+var_C0], r14
0x14001f213  mov     [rbp+60h+var_B8], 7
0x14001f21b  mov     word ptr [rbp+60h+var_D0], r14w
0x14001f220  mov     rbx, [rsp+160h+var_138]
0x14001f225  lea     r13, [r12+58h]
0x14001f22a  lea     rdx, [rsp+160h+var_110]
0x14001f22f  mov     rcx, r13
0x14001f232  call    ?ReplaceAll@CMultiReplacer@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CMultiReplacer::ReplaceAll(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001f237  cmp     dword ptr [rsp+160h+var_128], r14d
0x14001f23c  jz      short loc_14001F2A6
0x14001f23e  mov     rax, [r12]
  ... truncated ...
```
