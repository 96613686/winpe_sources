# CScopeManager::URLToScope(wchar_t const *,ulong *,wchar_t *,ulong,ulong *)

- ea: `0x18001d980`
- end: `0x18001e7a6`
- name: `?URLToScope@CScopeManager@@UEAAJPEB_WPEAKPEA_WK1@Z`
- size: `3622`
- prototype: `int(CScopeManager *__hidden this, const wchar_t *, unsigned int *, wchar_t *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18001b470`
- `0x18001d5b0`
- `0x18001d730`
- `0x18001d854`
- `0x18001d880`
- `0x18001d8a0`
- `0x18001d980`
- `0x18001f7c0`
- `0x180029348`
- `0x180033158`
- `0x1800341dc`
- `0x1800cf9a4`
- `0x18010a2e4`
- `0x18010a7dc`
- `0x18010bff4`
- `0x1801244c0`
- `0x1801249b0`
- `0x18013dd98`
- `0x1801ef6a4`
- `0x180241010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001e4f2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001e4f2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e0dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e481`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e0dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e481`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001dac4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001db9c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001dbe6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001dc68`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e01c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001dac4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001db9c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001dbe6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001dc68`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e01c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e448`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d9ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d9ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e0af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e10b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e1f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e21a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e0af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e10b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e1f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e21a`

## string_xrefs

- `0x18001e52a`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x18001e54e`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CScopeManager::URLToScope(
        CScopeManager *this,
        const wchar_t *a2,
        unsigned int *a3,
        wchar_t *a4,
        unsigned int a5,
        unsigned int *a6)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // r14
  const wchar_t *v10; // r15
  unsigned __int64 v11; // rax
  int v12; // r14d
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  __int64 i; // rdx
  wchar_t *v16; // rax
  char v17; // al
  __int64 v18; // rdi
  int v19; // r8d
  unsigned __int64 v20; // r13
  wchar_t *v21; // rax
  wchar_t v22; // r9
  __int64 v23; // rdx
  bool v24; // zf
  __int64 v25; // r15
  __int64 v26; // r14
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // r8
  __int64 v29; // r12
  __int64 size_of; // rax
  __int64 v31; // r13
  __int64 v32; // r14
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // rcx
  unsigned int v38; // edx
  unsigned __int64 v39; // r12
  unsigned __int64 v40; // r13
  unsigned __int64 v41; // r15
  __int64 v42; // r14
  unsigned __int64 v43; // rdi
  unsigned int j; // eax
  unsigned __int64 v45; // r12
  unsigned __int64 v46; // r13
  unsigned __int64 v47; // r15
  __int64 v48; // r14
  __int64 v49; // r13
  __int64 v50; // rdi
  __int64 v51; // r12
  const wchar_t *v52; // r15
  __int64 v53; // r9
  unsigned __int64 v54; // rcx
  wchar_t *v55; // r12
  __int64 v56; // r15
  const wchar_t *v57; // r14
  unsigned __int64 v58; // rax
  __int64 v59; // r9
  const wchar_t *v60; // r14
  __int64 v61; // rcx
  const wchar_t *v62; // rax
  unsigned __int64 v63; // r8
  bool v64; // al
  __int64 v65; // rax
  unsigned __int64 k; // rdi
  __int64 v67; // rax
  int v68; // edi
  wchar_t *v69; // rdx
  unsigned int v70; // r8d
  int v71; // r10d
  unsigned int *v72; // rcx
  char IsEnabled; // al
  wchar_t *v75; // r8
  unsigned __int64 v76; // r14
  unsigned __int64 v77; // rdi
  __int64 v78; // rax
  __int64 v79; // r12
  __int64 v80; // rax
  __int64 v81; // r14
  unsigned __int64 v82; // r14
  unsigned __int64 v83; // rdi
  __int64 v84; // rax
  __int64 v85; // r12
  __int64 v86; // rax
  __int64 v87; // r14
  BOOL bIgnoreCase; // [rsp+20h] [rbp-408h]
  char v89; // [rsp+30h] [rbp-3F8h]
  int v90; // [rsp+34h] [rbp-3F4h]
  unsigned int v91; // [rsp+34h] [rbp-3F4h]
  wchar_t v92; // [rsp+38h] [rbp-3F0h]
  int v93; // [rsp+38h] [rbp-3F0h]
  int v94; // [rsp+3Ch] [rbp-3ECh]
  unsigned int v95; // [rsp+3Ch] [rbp-3ECh]
  __int128 v96; // [rsp+40h] [rbp-3E8h] BYREF
  __int64 v97; // [rsp+50h] [rbp-3D8h]
  int v98; // [rsp+58h] [rbp-3D0h]
  unsigned __int64 v99; // [rsp+60h] [rbp-3C8h]
  unsigned __int64 v100; // [rsp+68h] [rbp-3C0h]
  wchar_t *v101; // [rsp+70h] [rbp-3B8h]
  unsigned int *v102; // [rsp+78h] [rbp-3B0h]
  unsigned int *v103; // [rsp+80h] [rbp-3A8h]
  unsigned int *v104; // [rsp+88h] [rbp-3A0h]
  wchar_t *v105; // [rsp+90h] [rbp-398h]
  char *v106; // [rsp+98h] [rbp-390h]
  void **v107; // [rsp+A0h] [rbp-388h] BYREF
  wchar_t *Str; // [rsp+A8h] [rbp-380h]
  __int64 v109; // [rsp+B0h] [rbp-378h]
  _WORD v110[196]; // [rsp+B8h] [rbp-370h] BYREF
  void **v111; // [rsp+240h] [rbp-1E8h] BYREF
  void *Block; // [rsp+248h] [rbp-1E0h]
  int v113; // [rsp+250h] [rbp-1D8h]
  unsigned int v114; // [rsp+254h] [rbp-1D4h]
  __int64 v115; // [rsp+258h] [rbp-1D0h] BYREF
  wchar_t v116; // [rsp+260h] [rbp-1C8h]
  __int16 v117; // [rsp+262h] [rbp-1C6h]
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+0h]

  v101 = a4;
  v102 = a3;
  v105 = a4;
  v103 = a6;
  v104 = a6;
  *a3 = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  v106 = (char *)this + 40;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  Str = v110;
  v109 = 193;
  v110[0] = 0;
  v107 = &TLMString<192,64,32767>::`vftable';
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  try
  {
    if ( (unsigned int)v9 >= 8 && CompareStringOrdinal(L"file:///", 8, a2, 8, 1) == 2 )
    {
      v10 = a2 + 8;
    }
    else
    {
      v10 = a2;
      if ( (unsigned int)v9 >= 5 && CompareStringOrdinal(L"file:", 5, a2, 5, 1) == 2 )
        v10 = a2 + 5;
    }
    v11 = -1;
    v12 = 0;
    do
      ++v11;
    while ( v10[v11] );
    if ( v11 < 3 || (unsigned __int16)(*v10 - 97) > 0x19u && (unsigned __int16)(*v10 - 65) > 0x19u )
      goto LABEL_9;
    if ( v10[1] != 58 || v10[2] != 92 && v10[2] != 47 )
    {
      v12 = 0;
      goto LABEL_9;
    }
    v56 = -1;
    do
      ++v56;
    while ( a2[v56] );
    if ( (unsigned int)v56 >= 8 && CompareStringOrdinal(L"file:///", 8, a2, 8, 1) == 2 )
    {
      v57 = a2 + 8;
    }
    else
    {
      v57 = a2;
      if ( (unsigned int)v56 >= 5 && CompareStringOrdinal(L"file:", 5, a2, 5, 1) == 2 )
        v57 = a2 + 5;
    }
    v58 = -1;
    v59 = 0;
    do
      ++v58;
    while ( v57[v58] );
    if ( v58 < 3 || (unsigned __int16)(*v57 - 97) > 0x19u && (unsigned __int16)(*v57 - 65) > 0x19u )
      goto LABEL_104;
    if ( v57[1] != 58 || v57[2] != 47 && v57[2] != 92 )
      goto LABEL_104;
    v60 = v57 + 3;
    if ( !v60 )
      goto LABEL_104;
    v61 = 0x7FFF;
    v62 = v60;
    do
    {
      if ( !*v62 )
        break;
      ++v62;
      --v61;
    }
    while ( v61 );
    v63 = (0x7FFF - v61) & -(__int64)(v61 != 0);
    if ( v61 && v63 >= 0x26 )
    {
      v64 = _MatchesFormat(v60, (const wchar_t *)(0x7FFF - v61), v63);
      v12 = 0;
      if ( v64 )
        goto LABEL_9;
    }
    else
    {
LABEL_104:
      v12 = 0;
    }
    if ( (int)IndexedVolumeIdUrlFromCurrentUrlWrap(*((_QWORD *)this + 90), a2, &v107, v59) >= 0 )
    {
LABEL_10:
      std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v96);
      if ( HIDWORD(v109) )
      {
        v13 = wcschr(Str, 0x3Au);
        if ( v13 )
        {
          if ( (unsigned int)(v13 - Str) == 1 )
          {
            Block = &v115;
            v113 = 193;
            v115 = *(_QWORD *)L"file:";
            v116 = aFile_5[4];
            v114 = 5;
            v117 = 0;
            v111 = &TLMString<192,64,32767>::`vftable';
            CLMString::Assign((CLMString *)&v111, Str, 5u, 0xFFFFFFFF);
            ((void (__fastcall *)(void ***, void *, _QWORD, __int64))v107[4])(&v107, Block, 0, 0xFFFFFFFFLL);
            if ( HIDWORD(v109) )
            {
              v14 = wcschr(Str, 0x5Cu);
              if ( v14 )
              {
                for ( i = v14 - Str; (_DWORD)i != -1; LODWORD(i) = v16 - Str )
                {
                  Str[(unsigned int)i] = 47;
                  if ( (unsigned int)(i + 1) >= HIDWORD(v109) )
                    break;
                  v16 = wcschr(&Str[(unsigned int)(i + 1)], 0x5Cu);
                  if ( !v16 )
                    break;
                }
              }
            }
            v111 = &TLMString<192,64,32767>::`vftable';
            if ( Block && Block != &v115 )
            {
              free(Block);
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
            }
          }
        }
      }
      v17 = 1;
      v89 = 1;
      LODWORD(v18) = 0;
      while ( 1 )
      {
        v98 = v18;
        v19 = v18;
        v90 = v18;
        v20 = (unsigned int)v18;
        v100 = (unsigned int)v18;
        if ( v17 )
          break;
        if ( (unsigned int)v18 < HIDWORD(v109) )
        {
          v21 = wcschr(&Str[(unsigned int)v18], 0x2Fu);
          if ( v21 )
            v18 = v21 - Str;
          else
            LODWORD(v18) = -1;
LABEL_25:
          v19 = v90;
          goto LABEL_26;
        }
        LODWORD(v18) = -1;
LABEL_26:
        if ( (_DWORD)v18 != -1 )
        {
          v22 = Str[(unsigned int)v18];
          v92 = v22;
          while ( 1 )
          {
            v23 = (unsigned int)v18;
            v18 = (unsigned int)(v18 + 1);
            v24 = (_DWORD)v18 == HIDWORD(v109);
            if ( (unsigned int)v18 >= HIDWORD(v109) )
              break;
            if ( Str[v18] != v22 )
            {
              v24 = (_DWORD)v18 == HIDWORD(v109);
              break;
            }
          }
          if ( !v24 || v19 <= 0 || Str[v23] != 58 )
          {
            v94 = v18 - v19;
            v25 = *((_QWORD *)&v96 + 1);
            if ( *((_QWORD *)&v96 + 1) == v97 )
            {
              v26 = (__int64)(*((_QWORD *)&v96 + 1) - v96) >> 4;
              if ( v26 == 0xFFFFFFFFFFFFFFFLL )
                std::_Xlength_error("vector too long");
              v99 = v26 + 1;
              v27 = (v97 - (__int64)v96) >> 4;
              v28 = v27 >> 1;
              if ( v27 > 0xFFFFFFFFFFFFFFFLL - (v27 >> 1) )
              {
                v29 = 0xFFFFFFFFFFFFFFFLL;
              }
              else
              {
                v29 = v28 + v27;
                if ( v28 + v27 < v26 + 1 )
                  v29 = v26 + 1;
              }
              size_of = std::_Get_size_of_n<16>(v29);
              v31 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
              v32 = 16 * v26;
              *(_DWORD *)(v32 + v31) = v90;
              *(_DWORD *)(v32 + v31 + 4) = v94;
              *(_QWORD *)(v32 + v31 + 8) = &v107;
              v33 = *((_QWORD *)&v96 + 1);
              v34 = v96;
              if ( v25 == *((_QWORD *)&v96 + 1) )
              {
                v35 = v31;
                while ( v34 != v33 )
                {
                  *(_DWORD *)v35 = *(_DWORD *)v34;
                  *(_DWORD *)(v35 + 4) = *(_DWORD *)(v34 + 4);
                  *(_QWORD *)(v35 + 8) = *(_QWORD *)(v34 + 8);
                  v35 += 16;
                  v34 += 16;
                }
              }
              else
              {
                std::_Uninitialized_move<CLMSubStr *>(v96, v25, v31);
                std::_Uninitialized_move<CLMSubStr *>(v25, *((_QWORD *)&v96 + 1), v31 + v32 + 16);
              }
              v12 = 0;
              if ( (_QWORD)v96 )
                std::_Deallocate<16>(v96, (v97 - v96) & 0xFFFFFFFFFFFFFFF0uLL);
              *(_QWORD *)&v96 = v31;
              *((_QWORD *)&v96 + 1) = v31 + 16 * v99;
              v97 = v31 + 16 * v29;
              v19 = v90;
              v22 = v92;
              v20 = v100;
            }
            else
            {
              **((_DWORD **)&v96 + 1) = v19;
              *(_DWORD *)(v25 + 4) = v18 - v19;
              *(_QWORD *)(v25 + 8) = &v107;
              *((_QWORD *)&v96 + 1) += 16LL;
            }
            if ( !v89 || v22 != 58 || (v17 = 1, (unsigned __int64)((__int64)(*((_QWORD *)&v96 + 1) - v96) >> 4) >= 2) )
              v17 = 0;
            v89 = v17;
            if ( (_DWORD)v18 != -1 )
              continue;
          }
        }
        v95 = HIDWORD(v109) - v19;
        if ( (unsigned int)(HIDWORD(v109) - v19) > HIDWORD(v109) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x428,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            bIgnoreCase);
        v36 = v20 + (unsigned int)(HIDWORD(v109) - v19);
        if ( v36 < v20 )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(HIDWORD(v109));
        if ( v36 > HIDWORD(v109) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x40C,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            bIgnoreCase);
        v37 = 0;
        v99 = 0;
        v38 = 1;
        v93 = 1;
LABEL_54:
        if ( v37 < (__int64)(*((_QWORD *)&v96 + 1) - v96) >> 4 )
        {
          v39 = v38;
          v100 = v38;
          v40 = (unsigned __int64)v38 >> *((_BYTE *)this + 384);
          v41 = *((_QWORD *)this + 45);
          if ( v40 >= v41 )
          {
            v76 = v40 + (unsigned int)((*((_DWORD *)this + 67) >> *((_BYTE *)this + 384)) + 1);
            v77 = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56491615>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56491615>::GetImpl'::`2'::impl) )
            {
              v78 = std::_Get_size_of_n<8>(v76);
              v79 = std::_Allocate<16,std::_Default_allocate_traits>(v78);
              if ( v41 )
              {
                do
                {
                  *(_QWORD *)(v79 + 8 * v77) = *(_QWORD *)(*((_QWORD *)this + 46) + 8 * v77);
                  ++v77;
                }
                while ( v77 < v41 );
              }
              std::_Deallocate<16>(*((_QWORD *)this + 46), 8LL * *((_QWORD *)this + 45));
              for ( *((_QWORD *)this + 45) = v76; v77 < *((_QWORD *)this + 45); ++v77 )
                *(_QWORD *)(v79 + 8 * v77) = 0;
              *((_QWORD *)this + 46) = v79;
              v39 = v100;
            }
            else
            {
              *((_QWORD *)this + 45) = v76;
              v80 = std::_Get_size_of_n<8>(v76);
              v81 = std::_Allocate<16,std::_Default_allocate_traits>(v80);
              if ( v41 )
              {
                do
                {
                  *(_QWORD *)(v81 + 8LL * (unsigned int)v77) = *(_QWORD *)(*((_QWORD *)this + 46)
                                                                         + 8LL * (unsigned int)v77);
                  LODWORD(v77) = v77 + 1;
                }
                while ( (unsigned int)v77 < v41 );
              }
              operator delete(*((void **)this + 46));
              while ( (unsigned __int64)(unsigned int)v77 < *((_QWORD *)this + 45) )
              {
                *(_QWORD *)(v81 + 8LL * (unsigned int)v77) = 0;
                LODWORD(v77) = v77 + 1;
              }
              *((_QWORD *)this + 46) = v81;
            }
          }
          v42 = *(_QWORD *)(*((_QWORD *)this + 46) + 8 * v40);
          v43 = 0;
          if ( !v42 )
          {
            v67 = std::_Get_size_of_n<88>(*((_QWORD *)this + 49));
            v42 = std::_Allocate<16,std::_Default_allocate_traits>(v67);
            while ( v43 < *((_QWORD *)this + 49) )
              CScopeManager::_CFolder::_CFolder(
                (CScopeManager::_CFolder *)(v42 + 88 * v43++),
                (CScopeManager *)((char *)this + 272));
            *(_QWORD *)(*((_QWORD *)this + 46) + 8 * v40) = v42;
          }
          if ( v39 >= *((_QWORD *)this + 50) )
            *((_QWORD *)this + 50) = v39 + 1;
          for ( j = *(_DWORD *)(88 * (*((_QWORD *)this + 47) & v39) + v42 + 68); ; j = *(_DWORD *)(v48 + v49 + 72) )
          {
            v91 = j;
            if ( !j )
              break;
            v45 = j;
            v100 = j;
            v46 = (unsigned __int64)j >> *((_BYTE *)this + 384);
            v47 = *((_QWORD *)this + 45);
            if ( v46 >= v47 )
            {
              v82 = v46 + (unsigned int)((*((_DWORD *)this + 67) >> *((_BYTE *)this + 384)) + 1);
              v83 = 0;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56491615>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56491615>::GetImpl'::`2'::impl) )
              {
                v84 = std::_Get_size_of_n<8>(v82);
                v85 = std::_Allocate<16,std::_Default_allocate_traits>(v84);
                if ( v47 )
                {
                  do
                  {
                    *(_QWORD *)(v85 + 8 * v83) = *(_QWORD *)(*((_QWORD *)this + 46) + 8 * v83);
                    ++v83;
                  }
                  while ( v83 < v47 );
                }
                std::_Deallocate<16>(*((_QWORD *)this + 46), 8LL * *((_QWORD *)this + 45));
                for ( *((_QWORD *)this + 45) = v82; v83 < *((_QWORD *)this + 45); ++v83 )
                  *(_QWORD *)(v85 + 8 * v83) = 0;
                *((_QWORD *)this + 46) = v85;
                v45 = v100;
              }
              else
              {
                *((_QWORD *)this + 45) = v82;
                v86 = std::_Get_size_of_n<8>(v82);
                v87 = std::_Allocate<16,std::_Default_allocate_traits>(v86);
                if ( v47 )
                {
                  do
                  {
                    *(_QWORD *)(v87 + 8LL * (unsigned int)v83) = *(_QWORD *)(*((_QWORD *)this + 46)
                                                                           + 8LL * (unsigned int)v83);
                    LODWORD(v83) = v83 + 1;
                  }
                  while ( (unsigned int)v83 < v47 );
                }
                operator delete(*((void **)this + 46));
                while ( (unsigned __int64)(unsigned int)v83 < *((_QWORD *)this + 45) )
                {
                  *(_QWORD *)(v87 + 8LL * (unsigned int)v83) = 0;
                  LODWORD(v83) = v83 + 1;
                }
                *((_QWORD *)this + 46) = v87;
              }
            }
            v48 = *(_QWORD *)(*((_QWORD *)this + 46) + 8 * v46);
            if ( !v48 )
            {
              v65 = std::_Get_size_of_n<88>(*((_QWORD *)this + 49));
              v48 = std::_Allocate<16,std::_Default_allocate_traits>(v65);
              for ( k = 0; k < *((_QWORD *)this + 49); ++k )
                CScopeManager::_CFolder::_CFolder(
                  (CScopeManager::_CFolder *)(v48 + 88 * k),
                  (CScopeManager *)((char *)this + 272));
              *(_QWORD *)(*((_QWORD *)this + 46) + 8 * v46) = v48;
            }
            if ( v45 >= *((_QWORD *)this + 50) )
              *((_QWORD *)this + 50) = v45 + 1;
            v49 = 88 * (*((_QWORD *)this + 47) & v45);
            v50 = 2 * v99;
            v51 = v96;
            v52 = *(const wchar_t **)(v48 + v49 + 8);
            v53 = -1;
            do
              ++v53;
            while ( v52[v53] );
            if ( !(unsigned int)NCompareStrings(
                                  1u,
                                  (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v96 + 16 * v99 + 8) + 8LL)
                                                  + 2LL * *(unsigned int *)(v96 + 16 * v99)),
                                  *(_DWORD *)(v96 + 16 * v99 + 4),
                                  v52,
                                  v53,
                                  *(_DWORD *)(v96 + 16 * v99 + 4)) )
            {
              v54 = -1;
              do
                ++v54;
              while ( v52[v54] );
              if ( *(int *)(v51 + 8 * v50 + 4) >= v54 )
              {
                v38 = v91;
                v93 = v91;
                v37 = ++v99;
                goto LABEL_54;
              }
            }
          }
          v37 = v99;
          v38 = v93;
        }
        if ( v37 != (__int64)(*((_QWORD *)&v96 + 1) - v96) >> 4 )
        {
          v68 = -2147467259;
          goto LABEL_140;
        }
        *v102 = v38;
        v68 = v95 != 0;
        v69 = v101;
        if ( v101 )
        {
          if ( a5 <= v95 )
          {
            v68 = -2147215348;
          }
          else
          {
            v70 = 0;
            if ( v95 )
            {
              v71 = v98;
              do
              {
                *v69++ = Str[v70 + v71];
                ++v70;
              }
              while ( v70 < v95 );
            }
            *v69 = 0;
LABEL_140:
            v69 = v101;
          }
        }
        v72 = v103;
        if ( v103 )
          *v103 = v95 + 1;
        if ( v68 < 0 )
        {
          if ( v72 )
            *v72 = 0;
          if ( v69 )
            *v69 = 0;
        }
        if ( (_QWORD)v96 )
        {
          std::_Deallocate<16>(v96, (v97 - v96) & 0xFFFFFFFFFFFFFFF0uLL);
          v96 = 0;
          v97 = 0;
        }
        v107 = &TLMString<192,64,32767>::`vftable';
        if ( Str && Str != v110 )
        {
          free(Str);
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
          v75 = Str;
          if ( IsEnabled )
            v75 = 0;
          Str = v75;
        }
        v107 = &CLMString::`vftable';
        LeaveCriticalSection(v8);
        return (unsigned int)v68;
      }
      v55 = &Str[(unsigned int)v18];
      while ( 1 )
      {
        if ( (unsigned int)(v12 + v18) >= HIDWORD(v109) )
        {
          LODWORD(v18) = -1;
          goto LABEL_78;
        }
        if ( wcschr(L":/", v55[v12]) )
          break;
        ++v12;
      }
      LODWORD(v18) = v12 + v18;
LABEL_78:
      v12 = 0;
      goto LABEL_25;
    }
LABEL_9:
    ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v107[4])(&v107, a2, 0, 0xFFFFFFFFLL);
    goto LABEL_10;
  }
  catch ( ... )
  {
    if ( v104 )
      *v104 = 0;
    if ( v105 )
      *v105 = 0;
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      1467,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\scopemanager.cxx");
  }
  return (unsigned int)v68;
}

```

## disassembly

```asm
0x18001d980  push    rbx
0x18001d982  push    rsi
0x18001d983  push    rdi
0x18001d984  push    r12
0x18001d986  push    r13
0x18001d988  push    r14
0x18001d98a  push    r15
0x18001d98c  sub     rsp, 3F0h
0x18001d993  mov     rax, cs:__security_cookie
0x18001d99a  xor     rax, rsp
0x18001d99d  mov     [rsp+428h+var_48], rax
0x18001d9a5  mov     [rsp+428h+var_3B8], r9
0x18001d9aa  mov     [rsp+428h+var_3B0], r8
0x18001d9af  mov     rdi, rdx
0x18001d9b2  mov     rsi, rcx
0x18001d9b5  mov     [rsp+428h+var_398], r9
0x18001d9bd  mov     rax, [rsp+428h+arg_28]
0x18001d9c5  mov     [rsp+428h+var_3A8], rax
0x18001d9cd  mov     [rsp+428h+var_3A0], rax
0x18001d9d5  xor     r15d, r15d
0x18001d9d8  mov     [r8], r15d
0x18001d9db  lea     rbx, [rcx+28h]
0x18001d9df  mov     [rsp+428h+var_390], rbx
0x18001d9e7  mov     rcx, rbx; lpCriticalSection
0x18001d9ea  call    cs:__imp_EnterCriticalSection
0x18001d9f0  nop
0x18001d9f1  lea     rax, [rsp+428h+var_370]
0x18001d9f9  mov     [rsp+428h+Str], rax
0x18001da01  mov     [rsp+428h+var_378], 0C1h
0x18001da0d  mov     [rsp+428h+var_370], r15w
0x18001da16  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18001da1d  mov     [rsp+428h+var_388], rax
0x18001da25  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001da29  mov     r14, r12
0x18001da2c  inc     r14
0x18001da2f  cmp     [rdi+r14*2], r15w
0x18001da34  jnz     short loc_18001DA2C
0x18001da36  mov     eax, 8
0x18001da3b  cmp     r14d, eax
0x18001da3e  jnb     loc_18001E098
0x18001da44  mov     r15, rdi
0x18001da47  mov     r13d, 5
0x18001da4d  cmp     r14d, r13d
0x18001da50  jnb     loc_18001E0F3
0x18001da56  mov     rax, r12
0x18001da59  xor     r14d, r14d
0x18001da5c  inc     rax
0x18001da5f  cmp     [r15+rax*2], r14w
0x18001da64  jnz     short loc_18001DA5C
0x18001da66  cmp     rax, 3
0x18001da6a  jnb     loc_18001E123
0x18001da70  mov     r12d, 5Ch ; '\'
0x18001da76  lea     r15d, [r12-2Dh]
0x18001da7b  mov     rax, [rsp+428h+var_388]
0x18001da83  or      r9d, 0FFFFFFFFh
0x18001da87  xor     r8d, r8d
0x18001da8a  mov     rdx, rdi
0x18001da8d  lea     rcx, [rsp+428h+var_388]
0x18001da95  mov     rax, [rax+20h]
0x18001da99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da9e  lea     rcx, [rsp+428h+var_3E8]; void *
0x18001daa3  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x18001daa8  nop
0x18001daa9  cmp     dword ptr [rsp+428h+var_378+4], r14d
0x18001dab1  jbe     loc_18001DC1C
0x18001dab7  mov     edx, 3Ah ; ':'; Ch
0x18001dabc  mov     rcx, [rsp+428h+Str]; Str
0x18001dac4  call    cs:__imp_wcschr
0x18001daca  test    rax, rax
0x18001dacd  jz      loc_18001DC1C
0x18001dad3  sub     rax, [rsp+428h+Str]
0x18001dadb  sar     rax, 1
0x18001dade  cmp     eax, 1
0x18001dae1  jnz     loc_18001DC1C
0x18001dae7  lea     rcx, [rsp+428h+var_1D0]
0x18001daef  mov     [rsp+428h+Block], rcx
0x18001daf7  mov     [rsp+428h+var_1D8], 0C1h
0x18001db02  movsd   xmm0, qword ptr cs:aFile_5; "file:"
0x18001db0a  movsd   [rsp+428h+var_1D0], xmm0
0x18001db13  movzx   eax, word ptr cs:aFile_5+8; ":"
0x18001db1a  mov     [rsp+428h+var_1C8], ax
0x18001db22  mov     [rsp+428h+var_1D4], r13d
0x18001db2a  mov     [rcx+0Ah], r14w
0x18001db2f  lea     r13, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18001db36  mov     [rsp+428h+var_1E8], r13
0x18001db3e  or      r9d, 0FFFFFFFFh; unsigned int
0x18001db42  mov     r8d, [rsp+428h+var_1D4]; unsigned int
0x18001db4a  mov     rdx, [rsp+428h+Str]; wchar_t *
0x18001db52  lea     rcx, [rsp+428h+var_1E8]; this
0x18001db5a  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x18001db5f  mov     rax, [rsp+428h+var_388]
0x18001db67  or      r9d, 0FFFFFFFFh
0x18001db6b  xor     r8d, r8d
0x18001db6e  mov     rdx, [rsp+428h+Block]
0x18001db76  lea     rcx, [rsp+428h+var_388]
0x18001db7e  mov     rax, [rax+20h]
0x18001db82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db87  cmp     dword ptr [rsp+428h+var_378+4], r14d
0x18001db8f  jbe     short loc_18001DC03
0x18001db91  mov     edx, r12d; Ch
0x18001db94  mov     rcx, [rsp+428h+Str]; Str
0x18001db9c  call    cs:__imp_wcschr
0x18001dba2  mov     rdx, rax
0x18001dba5  test    rax, rax
0x18001dba8  jz      short loc_18001DC03
0x18001dbaa  sub     rdx, [rsp+428h+Str]
0x18001dbb2  sar     rdx, 1
0x18001dbb5  cmp     edx, 0FFFFFFFFh
0x18001dbb8  jz      short loc_18001DC03
0x18001dbba  mov     ecx, edx
0x18001dbbc  mov     rax, [rsp+428h+Str]
0x18001dbc4  mov     [rax+rcx*2], r15w
0x18001dbc9  lea     eax, [rdx+1]
0x18001dbcc  cmp     eax, dword ptr [rsp+428h+var_378+4]
0x18001dbd3  jnb     short loc_18001DC03
0x18001dbd5  mov     edx, r12d; Ch
0x18001dbd8  mov     ecx, eax
0x18001dbda  mov     rax, [rsp+428h+Str]
0x18001dbe2  lea     rcx, [rax+rcx*2]; Str
0x18001dbe6  call    cs:__imp_wcschr
0x18001dbec  test    rax, rax
0x18001dbef  jz      short loc_18001DC03
0x18001dbf1  sub     rax, [rsp+428h+Str]
0x18001dbf9  sar     rax, 1
0x18001dbfc  mov     edx, eax
0x18001dbfe  cmp     eax, 0FFFFFFFFh
0x18001dc01  jnz     short loc_18001DBBA
0x18001dc03  mov     [rsp+428h+var_1E8], r13
0x18001dc0b  mov     rcx, [rsp+428h+Block]; Block
0x18001dc13  test    rcx, rcx
0x18001dc16  jnz     loc_18001E0CB
0x18001dc1c  mov     al, 1
0x18001dc1e  mov     [rsp+428h+var_3F8], al
0x18001dc22  mov     edi, r14d
0x18001dc25  mov     r10, 0FFFFFFFFFFFFFFFh
0x18001dc2f  mov     [rsp+428h+var_3D0], edi
0x18001dc33  mov     r8d, edi
0x18001dc36  mov     [rsp+428h+var_3F4], edi
0x18001dc3a  mov     r13d, edi
0x18001dc3d  mov     [rsp+428h+var_3C0], r13
0x18001dc42  test    al, al
0x18001dc44  jnz     loc_18001DFF3
0x18001dc4a  cmp     edi, dword ptr [rsp+428h+var_378+4]
0x18001dc51  jnb     loc_18001E1D4
0x18001dc57  mov     edx, 2Fh ; '/'; Ch
0x18001dc5c  mov     rax, [rsp+428h+Str]
0x18001dc64  lea     rcx, [rax+r13*2]; Str
0x18001dc68  call    cs:__imp_wcschr
0x18001dc6e  mov     rdi, rax
0x18001dc71  test    rax, rax
0x18001dc74  jz      loc_18001E083
0x18001dc7a  sub     rdi, [rsp+428h+Str]
0x18001dc82  sar     rdi, 1
0x18001dc85  mov     r8d, [rsp+428h+var_3F4]
0x18001dc8a  mov     r10, 0FFFFFFFFFFFFFFFh
0x18001dc94  cmp     edi, 0FFFFFFFFh
0x18001dc97  jz      loc_18001DE44
0x18001dc9d  mov     ecx, edi
0x18001dc9f  mov     rax, [rsp+428h+Str]
0x18001dca7  movzx   r9d, word ptr [rax+rcx*2]
0x18001dcac  mov     word ptr [rsp+428h+var_3F0], r9w
0x18001dcb2  mov     edx, edi
0x18001dcb4  inc     edi
0x18001dcb6  cmp     edi, dword ptr [rsp+428h+var_378+4]
0x18001dcbd  jnb     short loc_18001DCD5
0x18001dcbf  mov     rax, [rsp+428h+Str]
0x18001dcc7  cmp     [rax+rdi*2], r9w
0x18001dccc  jz      short loc_18001DCB2
0x18001dcce  cmp     edi, dword ptr [rsp+428h+var_378+4]
0x18001dcd5  jz      loc_18001DE21
0x18001dcdb  mov     eax, edi
0x18001dcdd  sub     eax, r8d
0x18001dce0  mov     [rsp+428h+var_3EC], eax
0x18001dce4  mov     rcx, [rsp+428h+var_3D8]
0x18001dce9  mov     r15, qword ptr [rsp+428h+var_3E8+8]
0x18001dcee  cmp     r15, rcx
0x18001dcf1  jnz     loc_18001E037
0x18001dcf7  mov     r14, r15
0x18001dcfa  sub     r14, qword ptr [rsp+428h+var_3E8]
0x18001dcff  sar     r14, 4
0x18001dd03  cmp     r14, r10
0x18001dd06  jz      loc_18001E4EB
0x18001dd0c  lea     rdx, [r14+1]
0x18001dd10  mov     [rsp+428h+var_3C8], rdx
0x18001dd15  sub     rcx, qword ptr [rsp+428h+var_3E8]
0x18001dd1a  sar     rcx, 4
0x18001dd1e  mov     r8, rcx
0x18001dd21  shr     r8, 1
0x18001dd24  mov     rax, r10
0x18001dd27  sub     rax, r8
0x18001dd2a  cmp     rcx, rax
0x18001dd2d  ja      loc_18001E090
0x18001dd33  lea     r12, [r8+rcx]
0x18001dd37  cmp     r12, rdx
0x18001dd3a  cmovb   r12, rdx
0x18001dd3e  mov     rcx, r12
0x18001dd41  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18001dd46  mov     rcx, rax
0x18001dd49  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001dd4e  mov     r13, rax
0x18001dd51  shl     r14, 4
0x18001dd55  mov     eax, [rsp+428h+var_3F4]
0x18001dd59  mov     [r14+r13], eax
0x18001dd5d  mov     eax, [rsp+428h+var_3EC]
0x18001dd61  mov     [r14+r13+4], eax
0x18001dd66  lea     rax, [rsp+428h+var_388]
0x18001dd6e  mov     [r14+r13+8], rax
0x18001dd73  mov     r8, qword ptr [rsp+428h+var_3E8+8]
0x18001dd78  mov     rcx, qword ptr [rsp+428h+var_3E8]
0x18001dd7d  cmp     r15, r8
0x18001dd80  jnz     loc_18001E4F8
0x18001dd86  mov     rdx, r13
0x18001dd89  jmp     short loc_18001DDA5
0x18001dd8b  mov     eax, [rcx]
0x18001dd8d  mov     [rdx], eax
0x18001dd8f  mov     eax, [rcx+4]
0x18001dd92  mov     [rdx+4], eax
0x18001dd95  mov     rax, [rcx+8]
0x18001dd99  mov     [rdx+8], rax
0x18001dd9d  lea     rdx, [rdx+10h]
0x18001dda1  add     rcx, 10h
0x18001dda5  cmp     rcx, r8
0x18001dda8  jnz     short loc_18001DD8B
0x18001ddaa  mov     rcx, qword ptr [rsp+428h+var_3E8]
0x18001ddaf  xor     r14d, r14d
0x18001ddb2  test    rcx, rcx
0x18001ddb5  jz      short loc_18001DDC8
0x18001ddb7  mov     rdx, [rsp+428h+var_3D8]
0x18001ddbc  sub     rdx, rcx
0x18001ddbf  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001ddc3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ddc8  mov     qword ptr [rsp+428h+var_3E8], r13
0x18001ddcd  mov     rax, [rsp+428h+var_3C8]
0x18001ddd2  shl     rax, 4
0x18001ddd6  add     rax, r13
0x18001ddd9  mov     qword ptr [rsp+428h+var_3E8+8], rax
0x18001ddde  shl     r12, 4
0x18001dde2  add     r12, r13
0x18001dde5  mov     [rsp+428h+var_3D8], r12
0x18001ddea  mov     r8d, [rsp+428h+var_3F4]
0x18001ddef  movzx   r9d, word ptr [rsp+428h+var_3F0]
0x18001ddf5  mov     r13, [rsp+428h+var_3C0]
0x18001ddfa  cmp     [rsp+428h+var_3F8], r14b
0x18001ddff  jnz     loc_18001E055
0x18001de05  mov     al, r14b
0x18001de08  mov     [rsp+428h+var_3F8], al
0x18001de0c  cmp     edi, 0FFFFFFFFh
0x18001de0f  mov     r10, 0FFFFFFFFFFFFFFFh
0x18001de19  jnz     loc_18001DC2F
0x18001de1f  jmp     short loc_18001DE44
0x18001de21  test    r8d, r8d
0x18001de24  jle     loc_18001DCDB
0x18001de2a  mov     rcx, rdx
0x18001de2d  mov     rax, [rsp+428h+Str]
0x18001de35  mov     edx, 3Ah ; ':'
0x18001de3a  cmp     [rax+rcx*2], dx
0x18001de3e  jnz     loc_18001DCDB
0x18001de44  mov     ecx, dword ptr [rsp+428h+var_378+4]
0x18001de4b  mov     r9d, ecx
0x18001de4e  sub     r9d, r8d
0x18001de51  mov     [rsp+428h+var_3EC], r9d
0x18001de56  cmp     r9d, ecx
0x18001de59  ja      loc_18001E51C
0x18001de5f  mov     edx, r9d
0x18001de62  add     rdx, r13
0x18001de65  cmp     rdx, r13
0x18001de68  jb      loc_18001E53B
0x18001de6e  cmp     rdx, rcx
0x18001de71  ja      loc_18001E540
0x18001de77  mov     rcx, r14
0x18001de7a  mov     [rsp+428h+var_3C8], rcx
0x18001de7f  mov     edx, 1
0x18001de84  mov     [rsp+428h+var_3F0], edx
0x18001de88  mov     rax, qword ptr [rsp+428h+var_3E8+8]
0x18001de8d  sub     rax, qword ptr [rsp+428h+var_3E8]
0x18001de92  sar     rax, 4
0x18001de96  cmp     rcx, rax
0x18001de99  jnb     loc_18001E4C5
0x18001de9f  mov     r12d, edx
0x18001dea2  mov     [rsp+428h+var_3C0], r12
0x18001dea7  movzx   r14d, byte ptr [rsi+180h]
0x18001deaf  mov     ecx, r14d
0x18001deb2  mov     r13d, edx
0x18001deb5  shr     r13, cl
0x18001deb8  mov     r15, [rsi+168h]
0x18001debf  cmp     r13, r15
0x18001dec2  jnb     loc_18001E55F
0x18001dec8  mov     rax, [rsi+170h]
0x18001decf  mov     r14, [rax+r13*8]
0x18001ded3  xor     edi, edi
0x18001ded5  test    r14, r14
0x18001ded8  jz      loc_18001E330
0x18001dede  cmp     r12, [rsi+190h]
0x18001dee5  jnb     loc_18001E661
0x18001deeb  and     r12, [rsi+178h]
0x18001def2  imul    rax, r12, 58h ; 'X'
0x18001def6  mov     eax, [rax+r14+44h]
0x18001defb  mov     [rsp+428h+var_3F4], eax
0x18001deff  xor     r14d, r14d
0x18001df02  test    eax, eax
  ... truncated ...
```
