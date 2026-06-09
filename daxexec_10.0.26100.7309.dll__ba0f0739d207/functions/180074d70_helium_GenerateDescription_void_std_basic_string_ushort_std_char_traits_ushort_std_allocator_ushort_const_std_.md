# helium::GenerateDescription(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,OfflineRegistry::HivePaths const &,bool,helium::ContainerType,std::vector<WriteVirtualization::RegistryExclusion,std::allocator<WriteVirtualization::RegistryExclusion>> const &)

- ea: `0x180074d70`
- end: `0x180076383`
- name: `?GenerateDescription@helium@@YA?AUContainerDescription@1@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBUHivePaths@OfflineRegistry@@_NW4ContainerType@1@AEBV?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@4@@Z`
- size: `5651`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070084`

## callees

- `0x1800053a0`
- `0x1800116b0`
- `0x180011820`
- `0x180011b04`
- `0x180013148`
- `0x180013188`
- `0x180015314`
- `0x18002031c`
- `0x180020390`
- `0x18002c0f4`
- `0x18002c9c8`
- `0x1800319a4`
- `0x180034460`
- `0x18006df4c`
- `0x18006e170`
- `0x18006e228`
- `0x180071644`
- `0x18007170c`
- `0x180072058`
- `0x18007376c`
- `0x18007383c`
- `0x180073db4`
- `0x180073e44`
- `0x180073f24`
- `0x180073ff4`
- `0x1800740d0`
- `0x18007448c`
- `0x1800746c8`
- `0x180074d70`
- `0x18007638c`
- `0x18007656c`
- `0x1800966b8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800752a5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800753d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800752a5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800753d0`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180074e07`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180074e07`

## string_xrefs

- `0x180074fd7`: `\Registry\machine\software`
- `0x180074eb0`: `\Registry\user\`
- `0x180075c30`: `\registry\machine\software`
- `0x180075d60`: `\registry\user`
- `0x180075d73`: `\registry\user`
- `0x180075e2c`: `\registry\comroot`
- `0x180075748`: `user_sid`
- `0x180075d99`: `user_sid`
- `0x180075b29`: `\registry`
- `0x180075b3c`: `\registry`
- `0x180075ba9`: `\registry\machine`
- `0x180075bbc`: `\registry\machine`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
__int64 __fastcall helium::GenerateDescription(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        char a6,
        int a7,
        __int64 a8)
{
  const char *v11; // r9
  void **Src; // rax
  int v13; // r14d
  __int128 v14; // xmm7
  __int128 v15; // xmm6
  __int64 *v16; // rdi
  __int64 *v17; // rbx
  const WCHAR **v18; // rsi
  const WCHAR *v19; // r8
  const WCHAR *v20; // rcx
  __int64 v21; // rax
  const WCHAR *v22; // r8
  const WCHAR *v23; // rcx
  const WCHAR *v24; // rcx
  __int64 v25; // rax
  LPCWCH *v26; // rax
  __int64 v27; // rax
  _BYTE *v28; // rcx
  __int64 v29; // rax
  __int64 **v30; // rax
  __int64 *i; // rax
  __int64 *j; // rcx
  char *v33; // rdi
  char *v34; // rsi
  char *v35; // r14
  __int64 v36; // r14
  __int64 v37; // rbx
  unsigned __int64 v38; // r8
  char v40; // [rsp+48h] [rbp-C0h]
  __int128 v41; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v42[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+88h] [rbp-80h]
  __int128 v44; // [rsp+98h] [rbp-70h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-60h]
  __int128 v46; // [rsp+B8h] [rbp-50h] BYREF
  void *v47[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-30h]
  __int128 v49; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v50; // [rsp+F0h] [rbp-18h]
  _QWORD v51[4]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v52; // [rsp+118h] [rbp+10h] BYREF
  __m128i v53; // [rsp+128h] [rbp+20h]
  __int128 v54; // [rsp+138h] [rbp+30h] BYREF
  __m128i v55; // [rsp+148h] [rbp+40h]
  __int128 v56; // [rsp+158h] [rbp+50h]
  int v57; // [rsp+168h] [rbp+60h]
  char v58; // [rsp+16Ch] [rbp+64h]
  __int64 v59; // [rsp+170h] [rbp+68h]
  __int128 v60; // [rsp+178h] [rbp+70h] BYREF
  __m128i si128; // [rsp+188h] [rbp+80h]
  __int128 v62; // [rsp+198h] [rbp+90h] BYREF
  __m128i v63; // [rsp+1A8h] [rbp+A0h]
  __int128 v64; // [rsp+1B8h] [rbp+B0h]
  int v65; // [rsp+1C8h] [rbp+C0h]
  char v66; // [rsp+1CCh] [rbp+C4h]
  __int64 v67; // [rsp+1D0h] [rbp+C8h]
  __int64 v68[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v69; // [rsp+1E8h] [rbp+E0h]
  void *DuplicateTokenHandle[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int128 v71; // [rsp+208h] [rbp+100h]
  LPCWCH v72[2]; // [rsp+218h] [rbp+110h] BYREF
  int v73[2]; // [rsp+228h] [rbp+120h]
  unsigned __int64 v74; // [rsp+230h] [rbp+128h]
  _OWORD v75[2]; // [rsp+238h] [rbp+130h] BYREF
  __int64 v76[2]; // [rsp+258h] [rbp+150h] BYREF
  __int64 v77; // [rsp+268h] [rbp+160h]
  void *v78[2]; // [rsp+278h] [rbp+170h] BYREF
  __int64 v79; // [rsp+288h] [rbp+180h]
  unsigned __int64 v80; // [rsp+290h] [rbp+188h]
  LPCWCH lpString2[2]; // [rsp+298h] [rbp+190h] BYREF
  int cchCount2; // [rsp+2A8h] [rbp+1A0h]
  unsigned __int64 v83; // [rsp+2B0h] [rbp+1A8h]
  __int128 v84; // [rsp+2B8h] [rbp+1B0h] BYREF
  __m128i v85; // [rsp+2C8h] [rbp+1C0h]
  _OWORD v86[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _OWORD v87[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  int v88; // [rsp+318h] [rbp+210h]
  __int16 v89; // [rsp+31Ch] [rbp+214h]
  __int128 v90; // [rsp+328h] [rbp+220h] BYREF
  __m128i v91; // [rsp+338h] [rbp+230h]
  _OWORD v92[2]; // [rsp+348h] [rbp+240h] BYREF
  _OWORD v93[2]; // [rsp+368h] [rbp+260h] BYREF
  int v94; // [rsp+388h] [rbp+280h]
  __int16 v95; // [rsp+38Ch] [rbp+284h]
  __int128 v96; // [rsp+398h] [rbp+290h] BYREF
  __m128i v97; // [rsp+3A8h] [rbp+2A0h]
  _OWORD v98[2]; // [rsp+3B8h] [rbp+2B0h] BYREF
  _OWORD v99[2]; // [rsp+3D8h] [rbp+2D0h] BYREF
  int v100; // [rsp+3F8h] [rbp+2F0h]
  __int16 v101; // [rsp+3FCh] [rbp+2F4h]
  _OWORD v102[2]; // [rsp+408h] [rbp+300h] BYREF
  _OWORD v103[2]; // [rsp+428h] [rbp+320h] BYREF
  _OWORD v104[2]; // [rsp+448h] [rbp+340h] BYREF
  int v105; // [rsp+468h] [rbp+360h]
  __int16 v106; // [rsp+46Ch] [rbp+364h]
  _OWORD v107[2]; // [rsp+478h] [rbp+370h] BYREF
  _OWORD v108[2]; // [rsp+498h] [rbp+390h] BYREF
  _OWORD v109[2]; // [rsp+4B8h] [rbp+3B0h] BYREF
  int v110; // [rsp+4D8h] [rbp+3D0h]
  __int16 v111; // [rsp+4DCh] [rbp+3D4h]
  __int128 v112; // [rsp+4E8h] [rbp+3E0h] BYREF
  __m128i v113; // [rsp+4F8h] [rbp+3F0h]
  _OWORD v114[2]; // [rsp+508h] [rbp+400h] BYREF
  _OWORD v115[2]; // [rsp+528h] [rbp+420h] BYREF
  int v116; // [rsp+548h] [rbp+440h]
  __int16 v117; // [rsp+54Ch] [rbp+444h]
  __int128 v118; // [rsp+558h] [rbp+450h] BYREF
  __m128i v119; // [rsp+568h] [rbp+460h]
  _OWORD v120[2]; // [rsp+578h] [rbp+470h] BYREF
  _OWORD v121[2]; // [rsp+598h] [rbp+490h] BYREF
  int v122; // [rsp+5B8h] [rbp+4B0h]
  __int16 v123; // [rsp+5BCh] [rbp+4B4h]
  _OWORD v124[2]; // [rsp+5C8h] [rbp+4C0h] BYREF
  _OWORD v125[3]; // [rsp+5E8h] [rbp+4E0h] BYREF
  __int128 v126; // [rsp+618h] [rbp+510h] BYREF
  __int64 v127; // [rsp+628h] [rbp+520h]
  _OWORD v128[2]; // [rsp+638h] [rbp+530h] BYREF
  _OWORD v129[3]; // [rsp+658h] [rbp+550h] BYREF
  __int128 v130; // [rsp+688h] [rbp+580h] BYREF
  __int64 v131; // [rsp+698h] [rbp+590h]
  _OWORD v132[2]; // [rsp+6A8h] [rbp+5A0h] BYREF
  _OWORD v133[3]; // [rsp+6C8h] [rbp+5C0h] BYREF
  __int128 v134; // [rsp+6F8h] [rbp+5F0h] BYREF
  __int64 v135; // [rsp+708h] [rbp+600h]
  _OWORD v136[2]; // [rsp+718h] [rbp+610h] BYREF
  _OWORD v137[3]; // [rsp+738h] [rbp+630h] BYREF
  __int128 v138; // [rsp+768h] [rbp+660h] BYREF
  __int64 v139; // [rsp+778h] [rbp+670h]
  _OWORD v140[2]; // [rsp+788h] [rbp+680h] BYREF
  _BYTE v141[32]; // [rsp+7A8h] [rbp+6A0h] BYREF
  _BYTE v142[32]; // [rsp+7C8h] [rbp+6C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+850h] [rbp+748h]

  v51[2] = a1;
  Schema::Containers::Definition::Container::Container((Schema::Containers::Definition::Container *)a1);
  *(_QWORD *)(a1 + 600) = 0;
  DuplicateTokenHandle[0] = (void *)(a1 + 600);
  DuplicateTokenHandle[1] = 0;
  LOBYTE(v71) = 1;
  if ( !DuplicateToken(a2, SecurityImpersonation, &DuplicateTokenHandle[1]) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x151,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumdescription.cpp",
      v11);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(DuplicateTokenHandle);
  GetUserSidFromToken(v78, a2);
  v41 = 0;
  v46 = 0;
  helium::CreatePackageGuids(a4, v78, &v41, &v46);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v79) < 0xF )
    std::_Xlen_string();
  Src = v78;
  if ( v80 > 7 )
    Src = (void **)v78[0];
  std::wstring::wstring(v68, 15, Src, v79);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v69) < 8 )
    std::_Xlen_string();
  std::wstring::wstring(v76, v69, L"_Classes", 8);
  v13 = 7;
  v136[0] = 0;
  v136[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v136[0]) = 0;
  memset(v137, 0, sizeof(v137));
  v138 = 0;
  v139 = 0;
  std::wstring::operator=(v136, L"software");
  v60 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60) = 0;
  v62 = 0;
  v63 = si128;
  LOWORD(v62) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  std::wstring::operator=(&v60, L"\\Registry\\machine\\software");
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v137,
    &v60);
  v52 = 0;
  v53 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v52) = 0;
  v54 = 0;
  v55 = v53;
  LOWORD(v54) = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  std::wstring::operator=(&v54);
  v14 = v41;
  v56 = v41;
  v58 = 1;
  BYTE1(v57) = 1;
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v137,
    &v52);
  std::wstring::~wstring(&v54);
  std::wstring::~wstring(&v52);
  std::wstring::~wstring(&v62);
  std::wstring::~wstring(&v60);
  v132[0] = 0;
  v132[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v132[0]) = 0;
  memset(v133, 0, sizeof(v133));
  v134 = 0;
  v135 = 0;
  std::wstring::operator=(v132, L"com");
  v60 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60) = 0;
  v62 = 0;
  v63 = si128;
  LOWORD(v62) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  std::wstring::operator=(&v62);
  v15 = v46;
  v64 = v46;
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v133,
    &v60);
  v52 = 0;
  v53 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v52) = 0;
  v54 = 0;
  v55 = v53;
  LOWORD(v54) = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  std::wstring::operator=(&v54);
  v56 = v14;
  v58 = 1;
  BYTE1(v57) = 1;
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v133,
    &v52);
  std::wstring::~wstring(&v54);
  std::wstring::~wstring(&v52);
  std::wstring::~wstring(&v62);
  std::wstring::~wstring(&v60);
  v49 = 0;
  v50 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v40 = 0;
  if ( a7 == 2 || a6 )
    goto LABEL_47;
  WriteVirtualization::RegistryPath::RegistryPath(
    (WriteVirtualization::RegistryPath *)lpString2,
    (const unsigned __int16 *const *)&off_1800D0818);
  WriteVirtualization::RegistryPath::RegistryPath(
    (WriteVirtualization::RegistryPath *)v72,
    (const unsigned __int16 *const *)&off_1800D0810);
  helium::GetRegistryWriteVirtualizationExclusions(v51, a4, a8);
  v16 = (__int64 *)v51[0];
  v17 = *(__int64 **)v51[0];
  while ( v17 != v16 )
  {
    v18 = (const WCHAR **)(v17 + 4);
    v19 = (const WCHAR *)lpString2;
    if ( v83 > 7 )
      v19 = lpString2[0];
    v20 = (const WCHAR *)(v17 + 4);
    if ( (unsigned __int64)v17[7] > 7 )
      v20 = *v18;
    if ( CompareStringOrdinal(v20, *((_DWORD *)v17 + 12), v19, cchCount2, 1) == 2 )
    {
      if ( v69 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      std::wstring::wstring(v141, v69, (void *)L"\\", 1);
      v21 = std::wstring::append(v141);
      v140[0] = *(_OWORD *)v21;
      v140[1] = *(_OWORD *)(v21 + 16);
      *(_QWORD *)(v21 + 16) = 0;
      *(_QWORD *)(v21 + 24) = 7;
      *(_WORD *)v21 = 0;
      v13 |= 0x18u;
      helium::AddExitNode(&v49, v140);
      std::wstring::~wstring(v140);
      std::wstring::~wstring(v141);
      v40 = 1;
    }
    else
    {
      v22 = (const WCHAR *)v72;
      if ( v74 > 7 )
        v22 = v72[0];
      v23 = (const WCHAR *)(v17 + 4);
      if ( (unsigned __int64)v17[7] > 7 )
        v23 = *v18;
      if ( CompareStringOrdinal(v23, *((_DWORD *)v17 + 12), v22, v73[0], 1) == 2 )
      {
        v40 = 1;
      }
      else
      {
        v24 = (const WCHAR *)(v17 + 4);
        if ( (unsigned __int64)v17[7] > 7 )
          v24 = *v18;
        v25 = v17[6];
        *(_QWORD *)&v46 = v24;
        *((_QWORD *)&v46 + 1) = v25;
        v26 = v72;
        if ( v74 > 7 )
          v26 = (LPCWCH *)v72[0];
        *(_QWORD *)&v41 = v26;
        *((_QWORD *)&v41 + 1) = *(_QWORD *)v73;
        v75[0] = v46;
        *(_OWORD *)DuplicateTokenHandle = v41;
        if ( (unsigned __int8)IsAncestorPathLexicallyNormal(DuplicateTokenHandle, v75) )
        {
          WriteVirtualization::RegistryPath::PathRelativeTo(v17 + 4, v142, v72);
          if ( v77 == 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          std::wstring::wstring(v75, v77, (void *)L"\\", 1);
          v27 = std::wstring::append(v75);
          *(_OWORD *)DuplicateTokenHandle = *(_OWORD *)v27;
          v71 = *(_OWORD *)(v27 + 16);
          *(_QWORD *)(v27 + 16) = 0;
          *(_QWORD *)(v27 + 24) = 7;
          *(_WORD *)v27 = 0;
          v13 |= 0x60u;
          helium::AddExitNode(v47, DuplicateTokenHandle);
          std::wstring::~wstring(DuplicateTokenHandle);
          std::wstring::~wstring(v75);
          v28 = v142;
        }
        else
        {
          if ( v69 == 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          std::wstring::wstring(v75, v69, (void *)L"\\", 1);
          v29 = std::wstring::append(v75);
          *(_OWORD *)DuplicateTokenHandle = *(_OWORD *)v29;
          v71 = *(_OWORD *)(v29 + 16);
          *(_QWORD *)(v29 + 16) = 0;
          *(_QWORD *)(v29 + 24) = 7;
          *(_WORD *)v29 = 0;
          v13 |= 0x180u;
          helium::AddExitNode(&v49, DuplicateTokenHandle);
          std::wstring::~wstring(DuplicateTokenHandle);
          v28 = v75;
        }
        std::wstring::~wstring(v28);
      }
    }
    v30 = (__int64 **)v17[2];
    if ( *((_BYTE *)v30 + 25) )
    {
      for ( i = (__int64 *)v17[1]; !*((_BYTE *)i + 25) && v17 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v17 = i;
      v17 = i;
    }
    else
    {
      v17 = (__int64 *)v17[2];
      for ( j = *v30; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v17 = j;
    }
  }
  std::_Tree<std::_Tset_traits<WriteVirtualization::NormalizedFileSystemPath,std::less<WriteVirtualization::NormalizedFileSystemPath>,std::allocator<WriteVirtualization::NormalizedFileSystemPath>,0>>::~_Tree<std::_Tset_traits<WriteVirtualization::NormalizedFileSystemPath,std::less<WriteVirtualization::NormalizedFileSystemPath>,std::allocator<WriteVirtualization::NormalizedFileSystemPath>,0>>(v51);
  std::wstring::~wstring(v72);
  std::wstring::~wstring(lpString2);
  if ( !v40 )
  {
LABEL_47:
    v34 = (char *)v47[1];
    v33 = (char *)v47[0];
  }
  else
  {
    v33 = (char *)v47[0];
    v34 = (char *)v47[1];
    if ( v47[0] != v47[1] )
    {
      v35 = (char *)v47[0];
      do
      {
        std::wstring::~wstring(v35 + 64);
        std::wstring::~wstring(v35 + 32);
        std::wstring::~wstring(v35);
        v35 += 104;
      }
      while ( v35 != v34 );
      v34 = v33;
      v47[1] = v33;
    }
  }
  v128[0] = 0;
  v128[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v128[0]) = 0;
  memset(v129, 0, sizeof(v129));
  v130 = 0;
  v131 = 0;
  std::wstring::operator=(v128, L"user_sid");
  if ( a7 != 2 )
  {
    v60 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v60) = 0;
    v62 = 0;
    v63 = si128;
    LOWORD(v62) = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    std::wstring::operator=(&v60);
    std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
      v129,
      &v60);
    if ( a5[10] )
    {
      v52 = 0;
      v53 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v52) = 0;
      v54 = 0;
      v55 = v53;
      LOWORD(v54) = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      std::wstring::operator=(&v54);
      v56 = v15;
      *(_WORD *)((char *)&v57 + 1) = 257;
      v58 = 1;
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v129,
        &v52);
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v52);
    }
    if ( a5[18] )
    {
      v52 = 0;
      v53 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v52) = 0;
      v54 = 0;
      v55 = v53;
      LOWORD(v54) = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      std::wstring::operator=(&v54);
      v56 = v14;
      BYTE2(v57) = 1;
      v59 = *(_QWORD *)(a1 + 600);
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v129,
        &v52);
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v52);
    }
    std::wstring::~wstring(&v62);
    std::wstring::~wstring(&v60);
  }
  v124[0] = 0;
  v124[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v124[0]) = 0;
  memset(v125, 0, sizeof(v125));
  v126 = 0;
  v127 = 0;
  std::wstring::operator=(v124, L"user_classes");
  if ( a7 != 2 )
  {
    v60 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v60) = 0;
    v62 = 0;
    v63 = si128;
    LOWORD(v62) = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    std::wstring::operator=(&v60);
    std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
      v125,
      &v60);
    if ( a5[14] )
    {
      v52 = 0;
      v53 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v52) = 0;
      v54 = 0;
      v55 = v53;
      LOWORD(v54) = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      std::wstring::operator=(&v54);
      v56 = v15;
      *(_WORD *)((char *)&v57 + 1) = 257;
      v58 = 1;
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v125,
        &v52);
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v52);
    }
    if ( a5[22] && !v40 )
    {
      v52 = 0;
      v53 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v52) = 0;
      v54 = 0;
      v55 = v53;
      LOWORD(v54) = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      std::wstring::operator=(&v54);
      v56 = v14;
      BYTE2(v57) = 1;
      v59 = *(_QWORD *)(a1 + 600);
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v125,
        &v52);
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v52);
    }
    std::wstring::~wstring(&v62);
    std::wstring::~wstring(&v60);
  }
  v118 = 0;
  v119 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v118) = 0;
  v120[0] = 0;
  v120[1] = v119;
  LOWORD(v120[0]) = 0;
  v121[0] = 0;
  v121[1] = v119;
  LOWORD(v121[0]) = 0;
  v122 = 0;
  v123 = 0;
  std::wstring::operator=(&v118, L"\\registry");
  std::wstring::operator=(v120, L"\\registry");
  v96 = 0;
  v97 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v96) = 0;
  v98[0] = 0;
  v98[1] = v97;
  LOWORD(v98[0]) = 0;
  v99[0] = 0;
  v99[1] = v97;
  LOWORD(v99[0]) = 0;
  v100 = 0;
  v101 = 0;
  std::wstring::operator=(&v96, L"\\registry\\machine");
  std::wstring::operator=(v98, L"\\registry\\machine");
  LOBYTE(v101) = 1;
  v90 = 0;
  v91 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v90) = 0;
  v92[0] = 0;
  v92[1] = v91;
  LOWORD(v92[0]) = 0;
  v93[0] = 0;
  v93[1] = v91;
  LOWORD(v93[0]) = 0;
  v94 = 0;
  v95 = 0;
  std::wstring::operator=(&v90, L"\\registry\\machine\\software");
  std::wstring::operator=(v93, L"software");
  LOBYTE(v95) = 1;
  v112 = 0;
  v113 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v112) = 0;
  v114[0] = 0;
  v114[1] = v113;
  LOWORD(v114[0]) = 0;
  v115[0] = 0;
  v115[1] = v113;
  LOWORD(v115[0]) = 0;
  v116 = 0;
  v117 = 0;
  v107[0] = 0;
  v107[1] = v113;
  LOWORD(v107[0]) = 0;
  v108[0] = 0;
  v108[1] = v113;
  LOWORD(v108[0]) = 0;
  v109[0] = 0;
  v109[1] = v113;
  LOWORD(v109[0]) = 0;
  v110 = 0;
  v111 = 0;
  v102[0] = 0;
  v102[1] = v113;
  LOWORD(v102[0]) = 0;
  v103[0] = 0;
  v103[1] = v113;
  LOWORD(v103[0]) = 0;
  v104[0] = 0;
  v104[1] = v113;
  LOWORD(v104[0]) = 0;
  v105 = 0;
  v106 = 0;
  if ( a7 != 2 )
  {
    std::wstring::operator=(&v112, L"\\registry\\user");
    std::wstring::operator=(v114, L"\\registry\\user");
    std::wstring::operator=(v107);
    std::wstring::operator=(v109, L"user_sid");
    std::wstring::operator=(v102);
    std::wstring::operator=(v104, L"user_classes");
  }
  v84 = 0;
  v85 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v84) = 0;
  v86[0] = 0;
  v86[1] = v85;
  LOWORD(v86[0]) = 0;
  v87[0] = 0;
  v87[1] = v85;
  LOWORD(v87[0]) = 0;
  v88 = 0;
  v89 = 0;
  std::wstring::operator=(&v84, L"\\registry\\comroot");
  std::wstring::operator=(v87, L"COM");
  LOBYTE(v89) = 1;
  memset(v42, 0, sizeof(v42));
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v36 = *((_QWORD *)&v49 + 1);
  v37 = v49;
  if ( a7 == 2 )
  {
    *(_QWORD *)&v41 = 2;
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Reallocate<0>(&v44, &v41);
    *(_QWORD *)&v41 = 3;
    if ( (unsigned __int64)(0x4EC4EC4EC4EC4EC5LL * ((__int64)(*((_QWORD *)&v43 + 1) - v42[3]) >> 3)) >= 3 )
      goto LABEL_66;
    goto LABEL_65;
  }
  *(_QWORD *)&v41 = 4;
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Reallocate<0>(&v44, &v41);
  v38 = 0x4EC4EC4EC4EC4EC5LL * ((v36 - v37) >> 3) + 6 + 0x4EC4EC4EC4EC4EC5LL * ((v34 - v33) >> 3);
  *(_QWORD *)&v41 = v38;
  if ( v38 > 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*((_QWORD *)&v43 + 1) - v42[3]) >> 3) )
  {
    if ( v38 > 0x276276276276276LL )
      std::vector<PackageFamilyCompatValues::AppDataRedirectionExclusion::ExclusionInfo>::_Xlength();
LABEL_65:
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Reallocate<0>(&v42[3], &v41);
  }
LABEL_66:
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
    &v44,
    v136);
  if ( a7 != 2 )
  {
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
      &v44,
      v128);
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
      &v44,
      v124);
  }
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
    &v44,
    v132);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v42[3],
    &v118);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v42[3],
    &v96);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v42[3],
    &v90);
  if ( a7 != 2 )
  {
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
      &v42[3],
      &v112);
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
      &v42[3],
      v107);
    while ( v37 != v36 )
    {
      std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode const>(
        &v42[3],
        v37);
      v37 += 104;
    }
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
      &v42[3],
      v102);
    while ( v33 != v34 )
    {
      std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode const>(
        &v42[3],
        v33);
      v33 += 104;
    }
  }
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v42[3],
    &v84);
  if ( (_QWORD *)(a1 + 320) != v42 )
  {
    std::vector<Schema::Containers::Definition::RegistrySymlink>::_Tidy(a1 + 320);
    *(_QWORD *)(a1 + 320) = v42[0];
    *(_OWORD *)(a1 + 328) = *(_OWORD *)&v42[1];
    memset(v42, 0, 24);
  }
  if ( (_QWORD *)(a1 + 344) != &v42[3] )
  {
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(a1 + 344);
    *(_QWORD *)(a1 + 344) = v42[3];
    *(_OWORD *)(a1 + 352) = v43;
    v42[3] = 0;
    v43 = 0;
  }
  if ( (__int128 *)(a1 + 368) != &v44 )
  {
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Tidy(a1 + 368);
    *(_OWORD *)(a1 + 368) = v44;
    *(_QWORD *)(a1 + 384) = v45;
    v44 = 0;
    v45 = 0;
  }
  *(_BYTE *)(a1 + 392) = 1;
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Tidy(&v44);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(&v42[3]);
  std::vector<Schema::Containers::Definition::RegistrySymlink>::_Tidy(v42);
  std::wstring::~wstring(v87);
  std::wstring::~wstring(v86);
  std::wstring::~wstring(&v84);
  std::wstring::~wstring(v104);
  std::wstring::~wstring(v103);
  std::wstring::~wstring(v102);
  std::wstring::~wstring(v109);
  std::wstring::~wstring(v108);
  std::wstring::~wstring(v107);
  std::wstring::~wstring(v115);
  std::wstring::~wstring(v114);
  std::wstring::~wstring(&v112);
  std::wstring::~wstring(v93);
  std::wstring::~wstring(v92);
  std::wstring::~wstring(&v90);
  std::wstring::~wstring(v99);
  std::wstring::~wstring(v98);
  std::wstring::~wstring(&v96);
  std::wstring::~wstring(v121);
  std::wstring::~wstring(v120);
  std::wstring::~wstring(&v118);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v126);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v125[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v125);
  std::wstring::~wstring(v124);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v130);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v129[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v129);
  std::wstring::~wstring(v128);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(v47);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(&v49);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v134);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v133[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v133);
  std::wstring::~wstring(v132);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v138);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v137[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v137);
  std::wstring::~wstring(v136);
  std::wstring::~wstring(v76);
  std::wstring::~wstring(v68);
  std::wstring::~wstring(v78);
  return a1;
}

```

## disassembly

```asm
0x180074d70  mov     rax, rsp
0x180074d73  mov     [rax+18h], rbx
0x180074d77  push    rbp
0x180074d78  push    rsi
0x180074d79  push    rdi
0x180074d7a  push    r12
0x180074d7c  push    r13
0x180074d7e  push    r14
0x180074d80  push    r15
0x180074d82  lea     rbp, [rax-748h]
0x180074d89  sub     rsp, 810h
0x180074d90  movaps  xmmword ptr [rax-48h], xmm6
0x180074d94  movaps  xmmword ptr [rax-58h], xmm7
0x180074d98  mov     rax, cs:__security_cookie
0x180074d9f  xor     rax, rsp
0x180074da2  mov     [rbp+740h+var_60], rax
0x180074da9  mov     rdi, r9
0x180074dac  mov     rbx, rdx
0x180074daf  mov     r13, rcx
0x180074db2  mov     [rbp+740h+var_740], rcx
0x180074db6  mov     r15, [rbp+740h+arg_20]
0x180074dbd  mov     rsi, [rbp+740h+arg_38]
0x180074dc4  xor     r12d, r12d
0x180074dc7  mov     [rsp+840h+var_7FC], r12d
0x180074dcc  call    ??0Container@Definition@Containers@Schema@@QEAA@XZ
0x180074dd1  lea     rax, [r13+258h]
0x180074dd8  mov     [rax], r12
0x180074ddb  mov     [rsp+840h+var_7FC], 1
0x180074de3  mov     [rbp+740h+DuplicateTokenHandle], rax
0x180074dea  mov     [rbp+740h+DuplicateTokenHandle+8], r12
0x180074df1  mov     byte ptr [rbp+740h+var_640], 1
0x180074df8  lea     r8, [rbp+740h+DuplicateTokenHandle+8]; DuplicateTokenHandle
0x180074dff  lea     edx, [r12+2]; ImpersonationLevel
0x180074e04  mov     rcx, rbx; ExistingTokenHandle
0x180074e07  call    cs:__imp_DuplicateToken
0x180074e0e  nop     dword ptr [rax+rax+00h]
0x180074e13  mov     rcx, [rbp+748h]; this
0x180074e1a  test    eax, eax
0x180074e1c  jz      loc_180076359
0x180074e22  lea     rcx, [rbp+740h+DuplicateTokenHandle]
0x180074e29  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x180074e2e  mov     rdx, rbx
0x180074e31  lea     rcx, [rbp+740h+var_5D0]
0x180074e38  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z
0x180074e3d  nop
0x180074e3e  xorps   xmm0, xmm0
0x180074e41  movups  [rsp+840h+var_7F8+8], xmm0
0x180074e46  xorps   xmm1, xmm1
0x180074e49  movups  [rbp+740h+var_790], xmm1
0x180074e4d  lea     r9, [rbp+740h+var_790]
0x180074e51  lea     r8, [rsp+840h+var_7F8+8]
0x180074e56  lea     rdx, [rbp+740h+var_5D0]
0x180074e5d  mov     rcx, rdi
0x180074e60  call    ?CreatePackageGuids@helium@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@PEAU_GUID@@2@Z
0x180074e65  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180074e6f  mov     rax, rbx
0x180074e72  mov     rcx, [rbp+740h+var_5C0]
0x180074e79  sub     rax, rcx
0x180074e7c  cmp     rax, 0Fh
0x180074e80  jb      loc_18007636B
0x180074e86  lea     rax, [rbp+740h+var_5D0]
0x180074e8d  cmp     [rbp+740h+var_5B8], 7
0x180074e95  cmova   rax, [rbp+740h+var_5D0]
0x180074e9d  mov     [rsp+840h+var_810], rcx; __int64
0x180074ea2  mov     [rsp+840h+Src], rax; Src
0x180074ea7  mov     qword ptr [rsp+840h+bIgnoreCase], 0Fh; __int64
0x180074eb0  lea     r9, aRegistryUser_0
0x180074eb7  lea     rcx, [rbp+740h+var_670]; void *
0x180074ebe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z
0x180074ec3  mov     [rsp+840h+var_7FC], 3
0x180074ecb  mov     rax, rbx
0x180074ece  mov     rcx, [rbp+740h+var_660]
0x180074ed5  sub     rax, rcx
0x180074ed8  cmp     rax, 8
0x180074edc  jb      loc_180076371
0x180074ee2  lea     r9, [rbp+740h+var_670]
0x180074ee9  cmp     [rbp+740h+var_658], 7
0x180074ef1  cmova   r9, [rbp+740h+var_670]
0x180074ef9  mov     [rsp+840h+var_810], 8; __int64
0x180074f02  lea     rax, aClasses_1
0x180074f09  mov     [rsp+840h+Src], rax; Src
0x180074f0e  mov     qword ptr [rsp+840h+bIgnoreCase], rcx; __int64
0x180074f13  lea     rcx, [rbp+740h+var_5F0]; void *
0x180074f1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z
0x180074f1f  lea     r14d, [r12+7]
0x180074f24  mov     [rsp+840h+var_7FC], r14d
0x180074f29  xorps   xmm0, xmm0
0x180074f2c  movups  [rbp+740h+var_130], xmm0
0x180074f33  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180074f3b  movdqa  [rbp+740h+var_120], xmm1
0x180074f43  mov     word ptr [rbp+740h+var_130], r12w
0x180074f4b  movdqa  [rbp+740h+var_110], xmm0
0x180074f53  xorps   xmm1, xmm1
0x180074f56  movdqa  [rbp+740h+var_100], xmm1
0x180074f5e  movdqa  [rbp+740h+var_F0], xmm0
0x180074f66  movdqa  [rbp+740h+var_E0], xmm1
0x180074f6e  mov     [rbp+740h+var_D0], r12
0x180074f75  lea     rdx, aSoftware_0
0x180074f7c  lea     rcx, [rbp+740h+var_130]; void *
0x180074f83  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z
0x180074f88  xorps   xmm0, xmm0
0x180074f8b  movups  [rbp+740h+var_6D0], xmm0
0x180074f8f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180074f97  movdqa  [rbp+740h+var_6C0], xmm1
0x180074f9f  mov     word ptr [rbp+740h+var_6D0], r12w
0x180074fa4  movups  [rbp+740h+var_6B0], xmm0
0x180074fab  movdqa  [rbp+740h+var_6A0], xmm1
0x180074fb3  mov     word ptr [rbp+740h+var_6B0], r12w
0x180074fbb  movups  [rbp+740h+var_690], xmm0
0x180074fc2  mov     [rbp+740h+var_680], r12d
0x180074fc9  mov     [rbp+740h+var_67C], r12b
0x180074fd0  mov     [rbp+740h+var_678], r12
0x180074fd7  lea     rdx, aRegistryMachin_0
0x180074fde  lea     rcx, [rbp+740h+var_6D0]; void *
0x180074fe2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z
0x180074fe7  lea     rdx, [rbp+740h+var_6D0]
0x180074feb  lea     rcx, [rbp+740h+var_110]
0x180074ff2  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAA?A_T$$QEAURegistryLayer@Definition@Containers@Schema@@@Z
0x180074ff7  xorps   xmm0, xmm0
0x180074ffa  movups  [rbp+740h+var_730], xmm0
0x180074ffe  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180075006  movdqa  [rbp+740h+var_720], xmm1
0x18007500b  mov     word ptr [rbp+740h+var_730], r12w
0x180075010  movups  [rbp+740h+var_710], xmm0
0x180075014  movdqa  [rbp+740h+var_700], xmm1
0x180075019  mov     word ptr [rbp+740h+var_710], r12w
0x18007501e  movups  [rbp+740h+var_6F0], xmm0
0x180075022  mov     [rbp+740h+var_6E0], r12d
0x180075026  mov     [rbp+740h+var_6DC], r12b
0x18007502a  mov     [rbp+740h+var_6D8], r12
0x18007502e  mov     rdx, r15
0x180075031  lea     rcx, [rbp+740h+var_710]; void *
0x180075035  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z
0x18007503a  movups  xmm7, [rsp+840h+var_7F8+8]
0x18007503f  movdqu  [rbp+740h+var_6F0], xmm7
0x180075044  mov     [rbp+740h+var_6DC], 1
0x180075048  mov     byte ptr [rbp+740h+var_6E0+1], 1
0x18007504c  lea     rdx, [rbp+740h+var_730]
0x180075050  lea     rcx, [rbp+740h+var_110]
0x180075057  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAA?A_T$$QEAURegistryLayer@Definition@Containers@Schema@@@Z
0x18007505c  nop
0x18007505d  lea     rcx, [rbp+740h+var_710]; void *
0x180075061  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180075066  lea     rcx, [rbp+740h+var_730]; void *
0x18007506a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18007506f  nop
0x180075070  lea     rcx, [rbp+740h+var_6B0]; void *
0x180075077  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18007507c  lea     rcx, [rbp+740h+var_6D0]; void *
0x180075080  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180075085  xorps   xmm0, xmm0
0x180075088  movups  [rbp+740h+var_1A0], xmm0
0x18007508f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180075097  movdqa  [rbp+740h+var_190], xmm1
0x18007509f  mov     word ptr [rbp+740h+var_1A0], r12w
0x1800750a7  movdqa  [rbp+740h+var_180], xmm0
0x1800750af  xorps   xmm1, xmm1
0x1800750b2  movdqa  [rbp+740h+var_170], xmm1
0x1800750ba  movdqa  [rbp+740h+var_160], xmm0
0x1800750c2  movdqa  [rbp+740h+var_150], xmm1
0x1800750ca  mov     [rbp+740h+var_140], r12
0x1800750d1  lea     rdx, aCom_0
0x1800750d8  lea     rcx, [rbp+740h+var_1A0]; void *
0x1800750df  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z
0x1800750e4  xorps   xmm0, xmm0
0x1800750e7  movups  [rbp+740h+var_6D0], xmm0
0x1800750eb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800750f3  movdqa  [rbp+740h+var_6C0], xmm1
0x1800750fb  mov     word ptr [rbp+740h+var_6D0], r12w
0x180075100  movups  [rbp+740h+var_6B0], xmm0
0x180075107  movdqa  [rbp+740h+var_6A0], xmm1
0x18007510f  mov     word ptr [rbp+740h+var_6B0], r12w
0x180075117  movups  [rbp+740h+var_690], xmm0
0x18007511e  mov     [rbp+740h+var_680], r12d
0x180075125  mov     [rbp+740h+var_67C], r12b
0x18007512c  mov     [rbp+740h+var_678], r12
0x180075133  lea     rdx, [r15+20h]
0x180075137  lea     rcx, [rbp+740h+var_6B0]; void *
0x18007513e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z
0x180075143  movups  xmm6, [rbp+740h+var_790]
0x180075147  movdqu  [rbp+740h+var_690], xmm6
0x18007514f  lea     rdx, [rbp+740h+var_6D0]
0x180075153  lea     rcx, [rbp+740h+var_180]
0x18007515a  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAA?A_T$$QEAURegistryLayer@Definition@Containers@Schema@@@Z
0x18007515f  xorps   xmm0, xmm0
0x180075162  movups  [rbp+740h+var_730], xmm0
0x180075166  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007516e  movdqa  [rbp+740h+var_720], xmm1
0x180075173  mov     word ptr [rbp+740h+var_730], r12w
0x180075178  movups  [rbp+740h+var_710], xmm0
0x18007517c  movdqa  [rbp+740h+var_700], xmm1
0x180075181  mov     word ptr [rbp+740h+var_710], r12w
0x180075186  movups  [rbp+740h+var_6F0], xmm0
0x18007518a  mov     [rbp+740h+var_6E0], r12d
0x18007518e  mov     [rbp+740h+var_6DC], r12b
0x180075192  mov     [rbp+740h+var_6D8], r12
0x180075196  mov     rdx, r15
0x180075199  lea     rcx, [rbp+740h+var_710]; void *
0x18007519d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z
0x1800751a2  movdqu  [rbp+740h+var_6F0], xmm7
0x1800751a7  mov     [rbp+740h+var_6DC], 1
0x1800751ab  mov     byte ptr [rbp+740h+var_6E0+1], 1
0x1800751af  lea     rdx, [rbp+740h+var_730]
0x1800751b3  lea     rcx, [rbp+740h+var_180]
0x1800751ba  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAA?A_T$$QEAURegistryLayer@Definition@Containers@Schema@@@Z
0x1800751bf  nop
0x1800751c0  lea     rcx, [rbp+740h+var_710]; void *
0x1800751c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800751c9  lea     rcx, [rbp+740h+var_730]; void *
0x1800751cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800751d2  nop
0x1800751d3  lea     rcx, [rbp+740h+var_6B0]; void *
0x1800751da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800751df  lea     rcx, [rbp+740h+var_6D0]; void *
0x1800751e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800751e8  xorps   xmm0, xmm0
0x1800751eb  movdqu  [rbp+740h+var_768], xmm0
0x1800751f0  mov     [rbp+740h+var_758], r12
0x1800751f4  movdqu  xmmword ptr [rbp+740h+var_780], xmm0
0x1800751f9  mov     [rbp+740h+var_770], r12
0x1800751fd  mov     [rsp+840h+var_800], r12b
0x180075202  mov     r12d, [rbp+740h+arg_30]
0x180075209  cmp     r12d, 2
0x18007520d  jz      loc_1800756F3
0x180075213  xor     ecx, ecx
0x180075215  cmp     [rbp+740h+arg_28], cl
0x18007521b  jnz     loc_1800756F3
0x180075221  lea     rdx, off_1800D0818; unsigned __int16 **
0x180075228  lea     rcx, [rbp+740h+lpString2]; this
0x18007522f  call    ??$?0AEBQEBG@RegistryPath@WriteVirtualization@@QEAA@AEBQEBG@Z
0x180075234  nop
0x180075235  lea     rdx, off_1800D0810; unsigned __int16 **
0x18007523c  lea     rcx, [rbp+740h+var_630]; this
0x180075243  call    ??$?0AEBQEBG@RegistryPath@WriteVirtualization@@QEAA@AEBQEBG@Z
0x180075248  nop
0x180075249  mov     r8, rsi
0x18007524c  mov     rdx, rdi
0x18007524f  lea     rcx, [rbp+740h+var_750]
0x180075253  call    ?GetRegistryWriteVirtualizationExclusions@helium@@YA?AV?$NormalizedExclusionPathList@VRegistryPath@WriteVirtualization@@@WriteVirtualization@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@5@@Z
0x180075258  nop
0x180075259  mov     rdi, [rbp+740h+var_750]
0x18007525d  mov     rbx, [rdi]
0x180075260  xor     esi, esi
0x180075262  cmp     rbx, rdi
0x180075265  jz      loc_18007568D
0x18007526b  lea     rsi, [rbx+20h]
0x18007526f  lea     r8, [rbp+740h+lpString2]
0x180075276  cmp     [rbp+740h+var_598], 7
0x18007527e  cmova   r8, [rbp+740h+lpString2]; lpString2
0x180075286  mov     rcx, rsi
0x180075289  cmp     qword ptr [rsi+18h], 7
0x18007528e  jbe     short loc_180075293
0x180075290  mov     rcx, [rsi]; lpString1
0x180075293  mov     [rsp+840h+bIgnoreCase], 1; bIgnoreCase
0x18007529b  mov     r9d, [rbp+740h+cchCount2]; cchCount2
0x1800752a2  mov     edx, [rsi+10h]; cchCount1
0x1800752a5  call    cs:__imp_CompareStringOrdinal
0x1800752ac  nop     dword ptr [rax+rax+00h]
0x1800752b1  cmp     eax, 2
0x1800752b4  jnz     loc_18007539A
0x1800752ba  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800752c4  mov     rcx, [rbp+740h+var_660]
0x1800752cb  sub     rax, rcx
0x1800752ce  cmp     rax, 1
0x1800752d2  jb      loc_180076377
0x1800752d8  lea     r9, [rbp+740h+var_670]
0x1800752df  cmp     [rbp+740h+var_658], 7
0x1800752e7  cmova   r9, [rbp+740h+var_670]
0x1800752ef  mov     [rsp+840h+var_810], 1; __int64
0x1800752f8  lea     rax, asc_1800D5864
0x1800752ff  mov     [rsp+840h+Src], rax; Src
0x180075304  mov     qword ptr [rsp+840h+bIgnoreCase], rcx; __int64
0x180075309  lea     rcx, [rbp+740h+var_A0]; void *
0x180075310  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z
0x180075315  or      r14d, 8
0x180075319  mov     [rsp+840h+var_7FC], r14d
0x18007531e  mov     r8d, 8
0x180075324  lea     rdx, aSoftware_1
0x18007532b  lea     rcx, [rbp+740h+var_A0]; Src
0x180075332  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z
0x180075337  movups  xmm0, xmmword ptr [rax]
0x18007533a  movups  [rbp+740h+var_C0], xmm0
0x180075341  movups  xmm1, xmmword ptr [rax+10h]
0x180075345  movups  [rbp+740h+var_B0], xmm1
0x18007534c  xor     esi, esi
0x18007534e  mov     [rax+10h], rsi
0x180075352  mov     qword ptr [rax+18h], 7
0x18007535a  mov     [rax], si
0x18007535d  or      r14d, 10h
0x180075361  mov     [rsp+840h+var_7FC], r14d
0x180075366  lea     rdx, [rbp+740h+var_C0]
0x18007536d  lea     rcx, [rbp+740h+var_768]
0x180075371  call    ?AddExitNode@helium@@YAXAEAV?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z
0x180075376  nop
0x180075377  lea     rcx, [rbp+740h+var_C0]; void *
0x18007537e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180075383  nop
0x180075384  lea     rcx, [rbp+740h+var_A0]; void *
0x18007538b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180075390  mov     [rsp+840h+var_800], 1
  ... truncated ...
```
