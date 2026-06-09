# Container::Manager::Image::ApplyAdjustments(Csl::Path const &,Container::Manager::Image::ImageAdjustments,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &,bool)

- ea: `0x140016da0`
- end: `0x14001785f`
- name: `?ApplyAdjustments@Image@Manager@Container@@YAJAEBVPath@Csl@@UImageAdjustments@123@AEBV?$optional@VPath@Csl@@@utl@@2_N@Z`
- size: `2751`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14001694c`

## callees

- `0x140002344`
- `0x140002b8c`
- `0x140006fe4`
- `0x14000c7a8`
- `0x14000c914`
- `0x14000cd84`
- `0x14000d7bc`
- `0x1400140a0`
- `0x1400150dc`
- `0x140015718`
- `0x140015f98`
- `0x140016da0`
- `0x140017868`
- `0x140017c88`
- `0x140018184`
- `0x140018d5c`
- `0x14001b938`
- `0x14001c440`
- `0x14001f660`
- `0x140021324`
- `0x140021390`
- `0x140021444`

## import_xrefs

- `DismApi!DismOpenSession` at `0x140016f25`
- `DismApi!DismOpenSession` at `0x140016f25`
- `DismApi!DismInitialize` at `0x140016f00`
- `DismApi!DismInitialize` at `0x140016f00`
- `DismApi!DismShutdown` at `0x140016f37`
- `DismApi!DismShutdown` at `0x140016f37`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::ApplyAdjustments(
        _QWORD *a1,
        Container::Manager::Image::ImageAdjustments *a2,
        __int64 a3,
        __int64 a4)
{
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rdx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rdi
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rdi
  int v19; // esi
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rdi
  _DWORD *v23; // rbx
  _DWORD *v24; // rdi
  __int64 v25; // rdx
  int *v26; // rdi
  int *v27; // rsi
  __m128i si128; // xmm6
  void **v29; // rax
  void **v30; // rcx
  int v31; // r8d
  __int64 v32; // rdx
  void **v33; // rax
  const char *v34; // r9
  void **v35; // rbx
  __int128 v36; // xmm0
  __int64 v37; // xmm1_8
  char v38; // al
  void **v39; // rcx
  int v40; // r8d
  void **v41; // r12
  unsigned __int8 v42; // dl
  void **v43; // r9
  _BYTE *v44; // r9
  __int64 v45; // rcx
  wil::details::in1diag3 *v46; // rcx
  void *v47; // rbx
  __int64 v48; // rdx
  void *v49; // rbx
  void *v50; // rcx
  _QWORD *i; // rbx
  int v52; // eax
  int v53; // edi
  unsigned __int64 v54; // rcx
  _QWORD *v55; // rax
  unsigned __int64 v56; // rax
  int ContainerUserProfile; // eax
  int v58; // eax
  int v60; // eax
  void *v61[2]; // [rsp+28h] [rbp-E0h] BYREF
  unsigned int v62[4]; // [rsp+38h] [rbp-D0h] BYREF
  void **v63; // [rsp+48h] [rbp-C0h] BYREF
  void ***v64; // [rsp+50h] [rbp-B8h]
  void ***v65; // [rsp+58h] [rbp-B0h]
  __int64 v66; // [rsp+60h] [rbp-A8h]
  void *v67[2]; // [rsp+68h] [rbp-A0h] BYREF
  _WORD v68[8]; // [rsp+78h] [rbp-90h] BYREF
  void *v69[2]; // [rsp+88h] [rbp-80h] BYREF
  _WORD v70[8]; // [rsp+98h] [rbp-70h] BYREF
  void **v71; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int8 v72; // [rsp+B0h] [rbp-58h]
  void *v73[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v74; // [rsp+C8h] [rbp-40h]
  void *v75[2]; // [rsp+D0h] [rbp-38h] BYREF
  _WORD v76[8]; // [rsp+E0h] [rbp-28h] BYREF
  void *v77[2]; // [rsp+F0h] [rbp-18h] BYREF
  _WORD v78[20]; // [rsp+100h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  int v80; // [rsp+168h] [rbp+60h] BYREF
  char v81; // [rsp+16Ch] [rbp+64h]
  __int64 v82; // [rsp+180h] [rbp+78h]

  v82 = a4;
  v8 = Container::Manager::Image::_anonymous_namespace_::DeployBootFilesToImage();
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v8,
      (int)v61[0]);
    goto LABEL_144;
  }
  v61[0] = v62;
  v61[1] = v62;
  LOWORD(v62[0]) = 0;
  if ( *(_BYTE *)(a4 + 32) )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v61,
                             *(_QWORD *)a4,
                             (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1) )
    {
      v10 = 1330;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL,
        (int)v61[0]);
      v11 = v61[0];
      if ( v61[0] != v62 )
LABEL_131:
        operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
LABEL_132:
      v9 = -2147024882;
      goto LABEL_144;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                v61,
                                *a1,
                                (__int64)(a1[1] - *a1) >> 1) )
  {
    v10 = 1334;
    goto LABEL_6;
  }
  if ( *(_QWORD *)a2 != *((_QWORD *)a2 + 1) || *((_QWORD *)a2 + 9) != *((_QWORD *)a2 + 10) )
  {
    if ( *(_BYTE *)(a4 + 32) )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x540,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32,
             (unsigned int)v61[0]);
      goto LABEL_14;
    }
    v13 = v61[0];
    v80 = 0;
    v81 = 0;
    v9 = DismInitialize(2, 0, 0);
    if ( v9 < 0 )
    {
      v14 = 78;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
        (const char *)(unsigned int)v9,
        (int)v61[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
        (const char *)(unsigned int)v9,
        (int)v61[0]);
      v16 = 1349;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v9,
        (int)v61[0]);
      Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v80);
LABEL_14:
      v12 = v61[0];
      if ( v61[0] != v62 )
        goto LABEL_143;
      goto LABEL_144;
    }
    v9 = DismOpenSession(v13, 0, 0, &v80);
    if ( v9 < 0 )
    {
      v15 = DismShutdown();
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
          (const char *)(unsigned int)v15,
          (int)v61[0]);
      v14 = 88;
      goto LABEL_22;
    }
    v17 = *(_QWORD *)a2;
    v18 = *((_QWORD *)a2 + 1);
    v81 = 1;
    if ( v17 != v18 )
    {
      while ( v17 != v18 )
      {
        if ( *(_DWORD *)(v17 + 32) == 1 )
        {
          v19 = Csl::DismHelper::EnableFeature(&v80, v17);
          if ( v19 < 0 )
          {
            v20 = 1359;
            goto LABEL_29;
          }
        }
        else
        {
          v19 = Csl::DismHelper::DisableFeature(&v80, v17);
          if ( v19 < 0 )
          {
            v20 = 1366;
            goto LABEL_29;
          }
        }
        v17 += 40;
      }
    }
    v21 = *((_QWORD *)a2 + 9);
    v22 = *((_QWORD *)a2 + 10);
    if ( v21 != v22 )
    {
      if ( *(_BYTE *)(a3 + 32) )
      {
        while ( 1 )
        {
          if ( v21 == v22 )
            goto LABEL_45;
          if ( !*(_BYTE *)(a3 + 32) )
            __int2c();
          v19 = Container::Manager::Image::_anonymous_namespace_::ApplyPackageAdjustment(&v80, v21, a3);
          if ( v19 < 0 )
            break;
          v21 += 40;
        }
        v20 = 1382;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v19,
          (int)v61[0]);
        Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v80);
        goto LABEL_30;
      }
      v9 = -2147024809;
      v16 = 1377;
      goto LABEL_23;
    }
LABEL_45:
    Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v80);
  }
  v23 = (_DWORD *)*((_QWORD *)a2 + 6);
  v24 = (_DWORD *)*((_QWORD *)a2 + 7);
  while ( v23 != v24 )
  {
    if ( *v23 == 1 )
    {
      v19 = Container::Manager::Image::_anonymous_namespace_::ApplyCommandAdjustment(a1, v23);
      if ( v19 < 0 )
      {
        v25 = 1429;
        goto LABEL_51;
      }
    }
    else
    {
      v19 = Container::Manager::Image::_anonymous_namespace_::ApplyCommandAdjustment(v61, v23);
      if ( v19 < 0 )
      {
        v25 = 1433;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v19,
          (int)v61[0]);
LABEL_30:
        if ( v61[0] != v62 )
          operator delete(v61[0], (const struct std::nothrow_t *)&std::nothrow);
        v9 = v19;
        goto LABEL_144;
      }
    }
    v23 += 10;
  }
  v26 = (int *)*((_QWORD *)a2 + 3);
  v27 = (int *)*((_QWORD *)a2 + 4);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v63 = (void **)&v63;
  v66 = 0;
  v64 = &v63;
  v65 = &v63;
  while ( v26 != v27 )
  {
    if ( (unsigned int)v26[27] > 1 )
      goto LABEL_89;
    if ( v65 == &v63 )
      goto LABEL_68;
    v29 = v63;
    v30 = (void **)&v63;
    v31 = *v26;
    do
    {
      if ( *((_DWORD *)v29 + 6) < v31 )
      {
        v32 = 2;
      }
      else
      {
        v30 = v29;
        v32 = 1;
      }
      v29 = (void **)v29[v32];
    }
    while ( v29 != &utl::_TreeSentinel );
    if ( v30 == (void **)&v63 || v31 < *((_DWORD *)v30 + 6) )
    {
LABEL_68:
      v74 = -1;
      *(__m128i *)v73 = si128;
      if ( !(unsigned __int8)utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(
                               v73,
                               v26) )
      {
        v46 = retaddr;
        v48 = 1466;
LABEL_92:
        wil::details::in1diag3::Return_Hr(
          v46,
          (void *)v48,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)0x8007000ELL,
          (int)v61[0]);
        v49 = v73[0];
        if ( v73[0] != (void *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
            (char *)v73[1] - (char *)v73[0],
            v73[0],
            ((char *)v73[1] - (char *)v73[0]) / 120 + (char *)v73[1] - (char *)v73[0]);
          v50 = v49;
          goto LABEL_129;
        }
        goto LABEL_130;
      }
      v33 = (void **)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v35 = v33;
      if ( v33 )
      {
        v36 = *(_OWORD *)v73;
        *((_DWORD *)v33 + 6) = *v26;
        v37 = v74;
        *((_OWORD *)v33 + 2) = v36;
        v33[6] = (void *)v37;
        *(__m128i *)v73 = si128;
        if ( v65 == &v63 )
        {
          *v33 = (char *)&v63 + 1;
          v38 = 1;
          v35[1] = &utl::_TreeSentinel;
          v35[2] = &utl::_TreeSentinel;
          ++v66;
          v63 = v35;
          v64 = (void ***)v35;
          v65 = (void ***)v35;
LABEL_85:
          v46 = retaddr;
          if ( !v35 )
          {
            v48 = 1472;
            goto LABEL_92;
          }
          if ( !v38 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x5C1,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
              v34);
          v47 = v73[0];
          if ( v73[0] != (void *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
              (char *)v73[1] - (char *)v73[0],
              v73[0],
              ((char *)v73[1] - (char *)v73[0]) / 120 + (char *)v73[1] - (char *)v73[0]);
            operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
          }
          goto LABEL_89;
        }
        v39 = v63;
        v40 = *((_DWORD *)v33 + 6);
        v41 = 0;
        do
        {
          if ( v40 < *((_DWORD *)v39 + 6) )
          {
            v42 = 0;
          }
          else
          {
            v41 = v39;
            v42 = 1;
          }
          v43 = v39;
          v39 = (void **)v39[v42 + 1];
        }
        while ( v39 != &utl::_TreeSentinel );
        if ( v41 && *((_DWORD *)v41 + 6) < v40 )
          v41 = 0;
        v71 = v43;
        v72 = v42;
        if ( !v41 )
        {
          utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::_InsertAt(
            &v63,
            &v71,
            v33);
          v38 = 1;
          goto LABEL_85;
        }
        v44 = v33[4];
        if ( v44 != (void *)-1LL )
        {
          v45 = (_BYTE *)v33[5] - (_BYTE *)v44;
          v33[5] = v44;
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
            v45,
            v44,
            v45 / 120 + v45);
          operator delete(v35[4], (const struct std::nothrow_t *)&std::nothrow);
        }
        operator delete(v35, (const struct std::nothrow_t *)&std::nothrow);
        v35 = v41;
      }
      v38 = 0;
      goto LABEL_85;
    }
    if ( !(unsigned __int8)utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(
                             v30 + 4,
                             v26) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL,
        (int)v61[0]);
      goto LABEL_130;
    }
LABEL_89:
    v26 += 30;
  }
  for ( i = v65; i != &v63; i = (_QWORD *)v54 )
  {
    v52 = Container::Manager::Image::_anonymous_namespace_::ProcessHive(v61, *((unsigned int *)i + 6), i + 4);
    v53 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C7,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v52,
        (int)v61[0]);
      utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v63);
      if ( v61[0] != v62 )
        operator delete(v61[0], (const struct std::nothrow_t *)&std::nothrow);
      v9 = v53;
      goto LABEL_144;
    }
    v54 = i[2];
    if ( (void **)v54 == &utl::_TreeSentinel )
    {
      v55 = (_QWORD *)(*i & 0xFFFFFFFFFFFFFFFEuLL);
      v54 = (unsigned __int64)v55;
      if ( (_QWORD *)v55[2] == i && (_QWORD *)*v55 != i )
      {
        v54 = *v55 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( *(_QWORD **)(v54 + 16) == v55 && *(_QWORD **)v54 != v55 )
        {
          do
          {
            v56 = v54;
            v54 = *(_QWORD *)v54 & 0xFFFFFFFFFFFFFFFEuLL;
          }
          while ( *(_QWORD *)(v54 + 16) == v56 );
        }
      }
    }
    else
    {
      if ( i == (_QWORD *)v54 )
        __int2c();
      while ( *(void ***)(v54 + 8) != &utl::_TreeSentinel )
        v54 = *(_QWORD *)(v54 + 8);
    }
  }
  v67[0] = v68;
  v67[1] = v68;
  v68[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v67,
                           L"ContainerUser",
                           13) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v61[0]);
LABEL_128:
    v50 = v67[0];
    if ( v67[0] == v68 )
      goto LABEL_130;
LABEL_129:
    operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
LABEL_130:
    utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v63);
    v11 = v61[0];
    if ( v61[0] == v62 )
      goto LABEL_132;
    goto LABEL_131;
  }
  v69[0] = v70;
  v69[1] = v70;
  v70[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v69,
                           L"S-1-5-93-2-2",
                           12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v61[0]);
LABEL_126:
    if ( v69[0] != v70 )
      operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_128;
  }
  ContainerUserProfile = Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile(v61, v69, v67);
  v9 = ContainerUserProfile;
  if ( ContainerUserProfile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)ContainerUserProfile,
      (int)v61[0]);
    goto LABEL_138;
  }
  v75[0] = v76;
  v75[1] = v76;
  v76[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v75,
                           L"ContainerAdministrator",
                           22) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v61[0]);
LABEL_124:
    if ( v75[0] != v76 )
      operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_126;
  }
  v77[0] = v78;
  v77[1] = v78;
  v78[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v77,
                           L"S-1-5-93-2-1",
                           12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v61[0]);
    if ( v77[0] != v78 )
      operator delete(v77[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_124;
  }
  v58 = Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile(v61, v77, v75);
  v9 = v58;
  if ( v58 >= 0 )
  {
    if ( !*(_BYTE *)(v82 + 32) )
    {
      v60 = Container::Manager::Image::_anonymous_namespace_::RebuildCatDb(v61);
      if ( v60 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5E7,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v60,
          (int)v61[0]);
    }
    if ( v77[0] != v78 )
      operator delete(v77[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v75[0] != v76 )
      operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v69[0] != v70 )
      operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v67[0] != v68 )
      operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
    utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v63);
    if ( v61[0] != v62 )
      operator delete(v61[0], (const struct std::nothrow_t *)&std::nothrow);
    Container::Manager::Image::ImageAdjustments::~ImageAdjustments(a2);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E0,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
    (const char *)(unsigned int)v58,
    (int)v61[0]);
  if ( v77[0] != v78 )
    operator delete(v77[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v75[0] != v76 )
    operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_138:
  if ( v69[0] != v70 )
    operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v67[0] != v68 )
    operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
  utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v63);
  v12 = v61[0];
  if ( v61[0] == v62 )
    goto LABEL_144;
LABEL_143:
  operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
LABEL_144:
  Container::Manager::Image::ImageAdjustments::~ImageAdjustments(a2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140016da0  mov     rax, rsp
0x140016da3  mov     [rax+10h], rbx
0x140016da7  mov     [rax+20h], r9
0x140016dab  push    rbp
0x140016dac  push    rsi
0x140016dad  push    rdi
0x140016dae  push    r12
0x140016db0  push    r13
0x140016db2  push    r14
0x140016db4  push    r15
0x140016db6  lea     rbp, [rax-58h]
0x140016dba  sub     rsp, 120h
0x140016dc1  movaps  xmmword ptr [rax-48h], xmm6
0x140016dc5  mov     r13, r9
0x140016dc8  mov     r12, r8
0x140016dcb  mov     r15, rdx
0x140016dce  mov     r14, rcx
0x140016dd1  call    Container__Manager__Image___anonymous_namespace___DeployBootFilesToImage
0x140016dd6  mov     ebx, eax
0x140016dd8  test    eax, eax
0x140016dda  jns     short loc_140016DF9
0x140016ddc  mov     rcx, [rbp+58h]; this
0x140016de0  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016de7  mov     r9d, eax; char *
0x140016dea  mov     edx, 52Ah; void *
0x140016def  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016df4  jmp     loc_14001776C
0x140016df9  lea     rax, [rsp+150h+var_120]
0x140016dfe  mov     [rsp+150h+var_130], rax; int
0x140016e03  lea     rcx, [rsp+150h+var_130]
0x140016e08  lea     rax, [rsp+150h+var_120]
0x140016e0d  mov     qword ptr [rsp+150h+var_128], rax
0x140016e12  xor     eax, eax
0x140016e14  mov     word ptr [rsp+150h+var_120], ax
0x140016e19  cmp     [r13+20h], al
0x140016e1d  jz      short loc_140016E71
0x140016e1f  mov     r8, [r13+8]
0x140016e23  sub     r8, [r13+0]
0x140016e27  mov     rdx, [r13+0]
0x140016e2b  sar     r8, 1
0x140016e2e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140016e33  test    al, al
0x140016e35  jnz     short loc_140016E8E
0x140016e37  mov     edx, 532h; void *
0x140016e3c  mov     rcx, [rbp+58h]; this
0x140016e40  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016e47  mov     r9d, 8007000Eh; char *
0x140016e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016e52  mov     rcx, [rsp+150h+var_130]
0x140016e57  lea     rax, [rsp+150h+var_120]
0x140016e5c  cmp     rcx, rax
0x140016e5f  jz      loc_1400176B7
0x140016e65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140016e6c  jmp     loc_1400176B2
0x140016e71  mov     r8, [r14+8]
0x140016e75  sub     r8, [r14]
0x140016e78  mov     rdx, [r14]
0x140016e7b  sar     r8, 1
0x140016e7e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140016e83  test    al, al
0x140016e85  jnz     short loc_140016E8E
0x140016e87  mov     edx, 536h
0x140016e8c  jmp     short loc_140016E3C
0x140016e8e  mov     rax, [r15+8]
0x140016e92  cmp     [r15], rax
0x140016e95  jnz     short loc_140016EA5
0x140016e97  mov     rax, [r15+50h]
0x140016e9b  cmp     [r15+48h], rax
0x140016e9f  jz      loc_14001709E
0x140016ea5  cmp     byte ptr [r13+20h], 0
0x140016eaa  jz      short loc_140016EE8
0x140016eac  mov     rcx, [rbp+58h]; this
0x140016eb0  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016eb7  mov     r9d, 32h ; '2'; char *
0x140016ebd  mov     edx, 540h; void *
0x140016ec2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016ec7  mov     ebx, eax
0x140016ec9  mov     rcx, [rsp+150h+var_130]
0x140016ece  lea     rax, [rsp+150h+var_120]
0x140016ed3  cmp     rcx, rax
0x140016ed6  jz      loc_14001776C
0x140016edc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140016ee3  jmp     loc_140017767
0x140016ee8  mov     rdi, [rsp+150h+var_130]
0x140016eed  xor     edx, edx
0x140016eef  xor     r8d, r8d
0x140016ef2  mov     [rbp+50h+arg_0], 0
0x140016ef9  mov     [rbp+50h+arg_4], 0
0x140016efd  lea     ecx, [rdx+2]
0x140016f00  call    cs:__imp_DismInitialize
0x140016f07  nop     dword ptr [rax+rax+00h]
0x140016f0c  mov     ebx, eax
0x140016f0e  test    eax, eax
0x140016f10  jns     short loc_140016F19
0x140016f12  mov     edx, 4Eh ; 'N'
0x140016f17  jmp     short loc_140016F64
0x140016f19  lea     r9, [rbp+50h+arg_0]
0x140016f1d  xor     r8d, r8d
0x140016f20  xor     edx, edx
0x140016f22  mov     rcx, rdi
0x140016f25  call    cs:__imp_DismOpenSession
0x140016f2c  nop     dword ptr [rax+rax+00h]
0x140016f31  mov     ebx, eax
0x140016f33  test    eax, eax
0x140016f35  jns     short loc_140016FB5
0x140016f37  call    cs:__imp_DismShutdown
0x140016f3e  nop     dword ptr [rax+rax+00h]
0x140016f43  mov     rcx, [rbp+58h]; this
0x140016f47  test    eax, eax
0x140016f49  jns     short loc_140016F5F
0x140016f4b  mov     r9d, eax; char *
0x140016f4e  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140016f55  mov     edx, 57h ; 'W'; void *
0x140016f5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140016f5f  mov     edx, 58h ; 'X'; void *
0x140016f64  mov     rcx, [rbp+58h]; this
0x140016f68  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140016f6f  mov     r9d, ebx; char *
0x140016f72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016f77  mov     rcx, [rbp+58h]; this
0x140016f7b  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140016f82  mov     r9d, ebx; char *
0x140016f85  mov     edx, 2Eh ; '.'; void *
0x140016f8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016f8f  mov     edx, 545h; void *
0x140016f94  mov     rcx, [rbp+58h]; this
0x140016f98  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016f9f  mov     r9d, ebx; char *
0x140016fa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016fa7  lea     rcx, [rbp+50h+arg_0]; this
0x140016fab  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x140016fb0  jmp     loc_140016EC9
0x140016fb5  mov     rbx, [r15]
0x140016fb8  mov     rdi, [r15+8]
0x140016fbc  mov     [rbp+50h+arg_4], 1
0x140016fc0  cmp     rbx, rdi
0x140016fc3  jz      short loc_14001703D
0x140016fc5  cmp     rbx, rdi
0x140016fc8  jz      short loc_14001703D
0x140016fca  cmp     dword ptr [rbx+20h], 1
0x140016fce  lea     rcx, [rbp+50h+arg_0]
0x140016fd2  mov     rdx, rbx
0x140016fd5  jnz     short loc_140017025
0x140016fd7  call    ?EnableFeature@DismHelper@Csl@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::DismHelper::EnableFeature(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x140016fdc  mov     esi, eax
0x140016fde  test    eax, eax
0x140016fe0  jns     short loc_140017030
0x140016fe2  mov     edx, 54Fh; void *
0x140016fe7  mov     rcx, [rbp+58h]; this
0x140016feb  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016ff2  mov     r9d, esi; char *
0x140016ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016ffa  lea     rcx, [rbp+50h+arg_0]; this
0x140016ffe  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x140017003  mov     rcx, [rsp+150h+var_130]; void *
0x140017008  lea     rax, [rsp+150h+var_120]
0x14001700d  cmp     rcx, rax
0x140017010  jz      short loc_14001701E
0x140017012  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017019  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001701e  mov     ebx, esi
0x140017020  jmp     loc_14001776C
0x140017025  call    ?DisableFeature@DismHelper@Csl@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::DismHelper::DisableFeature(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x14001702a  mov     esi, eax
0x14001702c  test    eax, eax
0x14001702e  js      short loc_140017036
0x140017030  add     rbx, 28h ; '('
0x140017034  jmp     short loc_140016FC5
0x140017036  mov     edx, 556h
0x14001703b  jmp     short loc_140016FE7
0x14001703d  mov     rbx, [r15+48h]
0x140017041  mov     rdi, [r15+50h]
0x140017045  cmp     rbx, rdi
0x140017048  jz      short loc_140017095
0x14001704a  cmp     byte ptr [r12+20h], 0
0x140017050  jnz     short loc_140017061
0x140017052  mov     ebx, 80070057h
0x140017057  mov     edx, 561h
0x14001705c  jmp     loc_140016F94
0x140017061  cmp     rbx, rdi
0x140017064  jz      short loc_140017095
0x140017066  cmp     byte ptr [r12+20h], 0
0x14001706c  jnz     short loc_140017070
0x14001706e  int     2Ch; Windows NT - assertion failure
0x140017070  mov     r8, r12
0x140017073  lea     rcx, [rbp+50h+arg_0]
0x140017077  mov     rdx, rbx
0x14001707a  call    Container__Manager__Image___anonymous_namespace___ApplyPackageAdjustment
0x14001707f  mov     esi, eax
0x140017081  test    eax, eax
0x140017083  js      short loc_14001708B
0x140017085  add     rbx, 28h ; '('
0x140017089  jmp     short loc_140017061
0x14001708b  mov     edx, 566h
0x140017090  jmp     loc_140016FE7
0x140017095  lea     rcx, [rbp+50h+arg_0]; this
0x140017099  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x14001709e  mov     rbx, [r15+30h]
0x1400170a2  mov     rdi, [r15+38h]
0x1400170a6  cmp     rbx, rdi
0x1400170a9  jz      short loc_1400170FB
0x1400170ab  cmp     dword ptr [rbx], 1
0x1400170ae  mov     rdx, rbx
0x1400170b1  jnz     short loc_1400170DE
0x1400170b3  mov     rcx, r14
0x1400170b6  call    Container__Manager__Image___anonymous_namespace___ApplyCommandAdjustment
0x1400170bb  mov     esi, eax
0x1400170bd  test    eax, eax
0x1400170bf  jns     short loc_1400170EE
0x1400170c1  mov     edx, 595h; void *
0x1400170c6  mov     rcx, [rbp+58h]; this
0x1400170ca  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400170d1  mov     r9d, esi; char *
0x1400170d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400170d9  jmp     loc_140017003
0x1400170de  lea     rcx, [rsp+150h+var_130]
0x1400170e3  call    Container__Manager__Image___anonymous_namespace___ApplyCommandAdjustment
0x1400170e8  mov     esi, eax
0x1400170ea  test    eax, eax
0x1400170ec  js      short loc_1400170F4
0x1400170ee  add     rbx, 28h ; '('
0x1400170f2  jmp     short loc_1400170A6
0x1400170f4  mov     edx, 599h
0x1400170f9  jmp     short loc_1400170C6
0x1400170fb  mov     rdi, [r15+18h]
0x1400170ff  lea     rax, [rsp+150h+var_110]
0x140017104  mov     rsi, [r15+20h]
0x140017108  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001710f  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140017117  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14001711e  mov     [rsp+150h+var_110], rax
0x140017123  mov     r13, 8888888888888889h
0x14001712d  lea     rax, [rsp+150h+var_110]
0x140017132  mov     [rsp+150h+var_F8], 0
0x14001713b  mov     [rsp+150h+var_108], rax
0x140017140  mov     [rsp+150h+var_100], rax
0x140017145  cmp     rdi, rsi
0x140017148  jz      loc_14001740B
0x14001714e  cmp     dword ptr [rdi+6Ch], 1
0x140017152  ja      loc_14001737E
0x140017158  lea     rax, [rsp+150h+var_110]
0x14001715d  cmp     [rsp+150h+var_100], rax
0x140017162  jz      short loc_1400171D3
0x140017164  mov     rax, [rsp+150h+var_110]
0x140017169  lea     rcx, [rsp+150h+var_110]
0x14001716e  mov     r8d, [rdi]
0x140017171  cmp     [rax+18h], r8d
0x140017175  jl      short loc_140017181
0x140017177  mov     rcx, rax
0x14001717a  mov     edx, 8
0x14001717f  jmp     short loc_140017186
0x140017181  mov     edx, 10h
0x140017186  mov     rax, [rax+rdx]
0x14001718a  cmp     rax, r12
0x14001718d  jnz     short loc_140017171
0x14001718f  lea     rax, [rsp+150h+var_110]
0x140017194  cmp     rcx, rax
0x140017197  jz      short loc_1400171D3
0x140017199  cmp     r8d, [rcx+18h]
0x14001719d  jl      short loc_1400171D3
0x14001719f  add     rcx, 20h ; ' '
0x1400171a3  mov     rdx, rdi
0x1400171a6  call    ??$emplace_back@URegistryAdjustment@Image@Manager@Container@@$0A@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAURegistryAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(Container::Manager::Image::RegistryAdjustment &&)
0x1400171ab  test    al, al
0x1400171ad  jnz     loc_14001737E
0x1400171b3  mov     rcx, [rbp+58h]; this
0x1400171b7  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400171be  mov     r9d, 8007000Eh; char *
0x1400171c4  mov     edx, 5B4h; void *
0x1400171c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400171ce  jmp     loc_140017696
0x1400171d3  mov     rdx, rdi
0x1400171d6  mov     [rbp+50h+var_90], 0FFFFFFFFFFFFFFFFh
0x1400171de  lea     rcx, [rbp+50h+var_A0]
0x1400171e2  movdqu  xmmword ptr [rbp+50h+var_A0], xmm6
0x1400171e7  call    ??$emplace_back@URegistryAdjustment@Image@Manager@Container@@$0A@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAURegistryAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(Container::Manager::Image::RegistryAdjustment &&)
0x1400171ec  test    al, al
0x1400171ee  jz      loc_140017400
0x1400171f4  mov     rdx, r14; struct std::nothrow_t *
0x1400171f7  mov     ecx, 38h ; '8'; unsigned __int64
0x1400171fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017201  mov     rbx, rax
0x140017204  test    rax, rax
0x140017207  jz      loc_140017330
0x14001720d  mov     eax, [rdi]
0x14001720f  movups  xmm0, xmmword ptr [rbp+50h+var_A0]
0x140017213  mov     [rbx+18h], eax
0x140017216  lea     rax, [rsp+150h+var_110]
0x14001721b  movsd   xmm1, [rbp+50h+var_90]
0x140017220  movups  xmmword ptr [rbx+20h], xmm0
0x140017224  movsd   qword ptr [rbx+30h], xmm1
0x140017229  movdqu  xmmword ptr [rbp+50h+var_A0], xmm6
0x14001722e  cmp     [rsp+150h+var_100], rax
0x140017233  jnz     short loc_140017264
0x140017235  lea     rax, [rsp+150h+var_110]
0x14001723a  or      rax, 1
0x14001723e  mov     [rbx], rax
0x140017241  mov     al, 1
0x140017243  mov     [rbx+8], r12
0x140017247  mov     [rbx+10h], r12
  ... truncated ...
```
