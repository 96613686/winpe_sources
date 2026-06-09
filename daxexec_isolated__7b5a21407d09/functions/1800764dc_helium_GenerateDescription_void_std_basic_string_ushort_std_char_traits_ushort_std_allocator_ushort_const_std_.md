# helium::GenerateDescription(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,OfflineRegistry::HivePaths const &,bool,helium::ContainerType,std::vector<WriteVirtualization::RegistryExclusion,std::allocator<WriteVirtualization::RegistryExclusion>> const &)

- ea: `0x1800764dc`
- end: `0x180077b74`
- name: `?GenerateDescription@helium@@YA?AUContainerDescription@1@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBUHivePaths@OfflineRegistry@@_NW4ContainerType@1@AEBV?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@4@@Z`
- size: `5784`
- prototype: `Schema::Containers::Definition::Container *__fastcall(Schema::Containers::Definition::Container *, void *, __int64, __int64, _QWORD *, char, int, __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180071bec`

## callees

- `0x180004f70`
- `0x18000b132`
- `0x180012ddc`
- `0x180012f3c`
- `0x1800130e4`
- `0x180013320`
- `0x180013510`
- `0x18001377c`
- `0x180014ebc`
- `0x1800210fc`
- `0x18002ca9c`
- `0x18002d4f0`
- `0x1800360e0`
- `0x18006f7f4`
- `0x18006fa34`
- `0x18006faf8`
- `0x180072fa0`
- `0x180073070`
- `0x180073978`
- `0x180075344`
- `0x1800753d4`
- `0x1800754b4`
- `0x180075584`
- `0x180075660`
- `0x180075c2c`
- `0x180075e48`
- `0x1800764dc`
- `0x180077b7c`
- `0x180077cc8`
- `0x180077da4`
- `0x1800784f0`
- `0x1800785d4`
- `0x180098008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800765c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800765c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800765a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800765a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800765ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800765ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180076a92`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180076bbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180076a92`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180076bbe`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180076573`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180076573`

## string_xrefs

- `0x180076665`: `\Registry\user\`
- `0x180076799`: `\Registry\machine\software`
- `0x1800773fc`: `\registry\machine`
- `0x18007740f`: `\registry\machine`
- `0x180077481`: `\registry\machine\software`
- `0x1800775bd`: `\registry\user`
- `0x1800775d0`: `\registry\user`
- `0x180077687`: `\registry\comroot`
- `0x180076e62`: `user_sid`
- `0x1800775f6`: `user_sid`
- `0x18007733a`: `\registry`
- `0x180077378`: `\registry`
- `0x18007738e`: `\registry`

## pseudocode

```c
Schema::Containers::Definition::Container *__fastcall helium::GenerateDescription(
        Schema::Containers::Definition::Container *a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        char a6,
        int a7,
        __int64 a8)
{
  __int64 v8; // rbx
  Schema::Containers::Definition::Container *v10; // r15
  _QWORD *v11; // rdi
  __int64 v12; // rcx
  const char *v13; // r9
  void *v14; // r12
  void *v15; // rsi
  DWORD LastError; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  _QWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  _QWORD *v22; // r9
  int v23; // r12d
  __int64 v24; // r8
  __m128i si128; // xmm6
  __int64 v26; // r8
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // r14
  void *v29; // rsi
  __int64 v30; // r8
  char v31; // r13
  __int64 *v32; // rdi
  __int64 *v33; // rbx
  const WCHAR **v34; // r15
  const WCHAR *v35; // r8
  const WCHAR *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  _QWORD *v39; // r9
  __int64 v40; // rax
  const WCHAR *v41; // r8
  const WCHAR *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r8
  __int64 v46; // r15
  _QWORD *v47; // r9
  __int64 v48; // rax
  _BYTE *v49; // rcx
  _QWORD *v50; // r9
  __int64 v51; // rax
  __int64 **v52; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  char *v55; // rdi
  char *v56; // rbx
  __int64 v57; // r8
  __int64 v58; // rbx
  __int64 v59; // r8
  __int64 v60; // r8
  _WORD *v61; // rbx
  __int64 v62; // rdx
  __int64 k; // rbx
  __int64 v64; // rdi
  char *v65; // rbx
  char *v66; // rdi
  _QWORD v68[6]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v69; // [rsp+88h] [rbp-80h] BYREF
  __int64 v70; // [rsp+98h] [rbp-70h]
  void *DuplicateTokenHandle[2]; // [rsp+A8h] [rbp-60h] BYREF
  char v72; // [rsp+B8h] [rbp-50h]
  Schema::Containers::Definition::Container *v73; // [rsp+C0h] [rbp-48h]
  void *v74[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-30h]
  __int128 v76; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v77; // [rsp+F0h] [rbp-18h]
  __int128 v78; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v79; // [rsp+108h] [rbp+0h]
  _QWORD v80[5]; // [rsp+110h] [rbp+8h] BYREF
  __int128 v81; // [rsp+138h] [rbp+30h] BYREF
  __m128i v82; // [rsp+148h] [rbp+40h]
  __int128 v83; // [rsp+158h] [rbp+50h] BYREF
  __m128i v84; // [rsp+168h] [rbp+60h]
  __int128 v85; // [rsp+178h] [rbp+70h]
  int v86; // [rsp+188h] [rbp+80h]
  char v87; // [rsp+18Ch] [rbp+84h]
  __int64 v88; // [rsp+190h] [rbp+88h]
  __int128 v89; // [rsp+198h] [rbp+90h] BYREF
  __m128i v90; // [rsp+1A8h] [rbp+A0h]
  __int128 v91; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v92; // [rsp+1C8h] [rbp+C0h]
  unsigned __int128 v93; // [rsp+1D8h] [rbp+D0h]
  int v94; // [rsp+1E8h] [rbp+E0h]
  char v95; // [rsp+1ECh] [rbp+E4h]
  __int64 v96; // [rsp+1F0h] [rbp+E8h]
  _QWORD v97[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v98; // [rsp+208h] [rbp+100h]
  unsigned __int64 v99; // [rsp+210h] [rbp+108h]
  __int128 v100; // [rsp+218h] [rbp+110h] BYREF
  __m128i v101; // [rsp+228h] [rbp+120h]
  __int128 v102; // [rsp+238h] [rbp+130h] BYREF
  __m128i v103; // [rsp+248h] [rbp+140h]
  __int128 v104; // [rsp+258h] [rbp+150h]
  int v105; // [rsp+268h] [rbp+160h]
  char v106; // [rsp+26Ch] [rbp+164h]
  __int64 v107; // [rsp+270h] [rbp+168h]
  __int128 v108; // [rsp+278h] [rbp+170h] BYREF
  __int64 v109; // [rsp+288h] [rbp+180h]
  __int64 v110; // [rsp+290h] [rbp+188h]
  void *v111[2]; // [rsp+298h] [rbp+190h] BYREF
  __int64 v112; // [rsp+2A8h] [rbp+1A0h]
  unsigned __int64 v113; // [rsp+2B0h] [rbp+1A8h]
  _OWORD v114[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  int v115; // [rsp+2D8h] [rbp+1D0h]
  __int16 v116; // [rsp+2DCh] [rbp+1D4h]
  LPCWCH v117[2]; // [rsp+2E8h] [rbp+1E0h] BYREF
  int v118; // [rsp+2F8h] [rbp+1F0h]
  unsigned __int64 v119; // [rsp+300h] [rbp+1F8h]
  _QWORD v120[2]; // [rsp+308h] [rbp+200h] BYREF
  __int64 v121; // [rsp+318h] [rbp+210h]
  unsigned __int64 v122; // [rsp+320h] [rbp+218h]
  _QWORD v123[2]; // [rsp+328h] [rbp+220h] BYREF
  __int64 v124; // [rsp+338h] [rbp+230h]
  unsigned __int64 v125; // [rsp+340h] [rbp+238h]
  _BYTE v126[32]; // [rsp+348h] [rbp+240h] BYREF
  LPCWCH lpString2[2]; // [rsp+368h] [rbp+260h] BYREF
  int cchCount2; // [rsp+378h] [rbp+270h]
  unsigned __int64 v129; // [rsp+380h] [rbp+278h]
  _OWORD v130[2]; // [rsp+388h] [rbp+280h] BYREF
  _OWORD v131[2]; // [rsp+3A8h] [rbp+2A0h] BYREF
  _OWORD v132[2]; // [rsp+3C8h] [rbp+2C0h] BYREF
  int v133; // [rsp+3E8h] [rbp+2E0h]
  __int16 v134; // [rsp+3ECh] [rbp+2E4h]
  _OWORD v135[2]; // [rsp+3F8h] [rbp+2F0h] BYREF
  _OWORD v136[2]; // [rsp+418h] [rbp+310h] BYREF
  _OWORD v137[2]; // [rsp+438h] [rbp+330h] BYREF
  int v138; // [rsp+458h] [rbp+350h]
  __int16 v139; // [rsp+45Ch] [rbp+354h]
  _OWORD v140[2]; // [rsp+468h] [rbp+360h] BYREF
  _OWORD v141[2]; // [rsp+488h] [rbp+380h] BYREF
  _OWORD v142[2]; // [rsp+4A8h] [rbp+3A0h] BYREF
  int v143; // [rsp+4C8h] [rbp+3C0h]
  __int16 v144; // [rsp+4CCh] [rbp+3C4h]
  int v145; // [rsp+4D8h] [rbp+3D0h] BYREF
  __int64 v146; // [rsp+4DCh] [rbp+3D4h]
  int v147; // [rsp+4E4h] [rbp+3DCh]
  __int64 v148; // [rsp+4E8h] [rbp+3E0h]
  __int64 v149; // [rsp+4F0h] [rbp+3E8h]
  _OWORD v150[3]; // [rsp+4F8h] [rbp+3F0h] BYREF
  __int128 v151; // [rsp+528h] [rbp+420h] BYREF
  __int64 v152; // [rsp+538h] [rbp+430h]
  _OWORD v153[2]; // [rsp+548h] [rbp+440h] BYREF
  _OWORD v154[2]; // [rsp+568h] [rbp+460h] BYREF
  _OWORD v155[2]; // [rsp+588h] [rbp+480h] BYREF
  int v156; // [rsp+5A8h] [rbp+4A0h]
  __int16 v157; // [rsp+5ACh] [rbp+4A4h]
  _OWORD v158[2]; // [rsp+5B8h] [rbp+4B0h] BYREF
  _OWORD v159[2]; // [rsp+5D8h] [rbp+4D0h] BYREF
  _OWORD v160[2]; // [rsp+5F8h] [rbp+4F0h] BYREF
  int v161; // [rsp+618h] [rbp+510h]
  __int16 v162; // [rsp+61Ch] [rbp+514h]
  _OWORD v163[2]; // [rsp+628h] [rbp+520h] BYREF
  _OWORD v164[2]; // [rsp+648h] [rbp+540h] BYREF
  _OWORD v165[2]; // [rsp+668h] [rbp+560h] BYREF
  int v166; // [rsp+688h] [rbp+580h]
  __int16 v167; // [rsp+68Ch] [rbp+584h]
  __int128 v168; // [rsp+698h] [rbp+590h] BYREF
  __int64 v169; // [rsp+6A8h] [rbp+5A0h]
  __int64 v170; // [rsp+6B0h] [rbp+5A8h]
  _OWORD v171[3]; // [rsp+6B8h] [rbp+5B0h] BYREF
  __int128 v172; // [rsp+6E8h] [rbp+5E0h] BYREF
  __int64 v173; // [rsp+6F8h] [rbp+5F0h]
  __int128 v174; // [rsp+708h] [rbp+600h] BYREF
  __int64 v175; // [rsp+718h] [rbp+610h]
  __int64 v176; // [rsp+720h] [rbp+618h]
  _OWORD v177[3]; // [rsp+728h] [rbp+620h] BYREF
  __int128 v178; // [rsp+758h] [rbp+650h] BYREF
  __int64 v179; // [rsp+768h] [rbp+660h]
  __int128 v180; // [rsp+778h] [rbp+670h] BYREF
  __int64 v181; // [rsp+788h] [rbp+680h]
  __int64 v182; // [rsp+790h] [rbp+688h]
  _OWORD v183[3]; // [rsp+798h] [rbp+690h] BYREF
  __int128 v184; // [rsp+7C8h] [rbp+6C0h] BYREF
  __int64 v185; // [rsp+7D8h] [rbp+6D0h]
  _OWORD v186[2]; // [rsp+7E8h] [rbp+6E0h] BYREF
  _BYTE v187[32]; // [rsp+808h] [rbp+700h] BYREF
  _BYTE Src[32]; // [rsp+828h] [rbp+720h] BYREF
  _BYTE v189[32]; // [rsp+848h] [rbp+740h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8C0h] [rbp+7B8h]

  v8 = a4;
  v77 = a4;
  v10 = a1;
  v73 = a1;
  v80[3] = a1;
  v11 = a5;
  v80[0] = a8;
  Schema::Containers::Definition::Container::Container(a1);
  *(_QWORD *)(v12 + 600) = 0;
  DuplicateTokenHandle[0] = (void *)(v12 + 600);
  DuplicateTokenHandle[1] = 0;
  v72 = 1;
  if ( !DuplicateToken(a2, SecurityImpersonation, &DuplicateTokenHandle[1]) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x151,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumdescription.cpp",
      v13);
  if ( v72 )
  {
    v14 = DuplicateTokenHandle[1];
    v15 = *(void **)DuplicateTokenHandle[0];
    if ( (unsigned __int64)(*(_QWORD *)DuplicateTokenHandle[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v15);
      SetLastError(LastError);
      v8 = v77;
    }
    *(_QWORD *)DuplicateTokenHandle[0] = v14;
    v11 = a5;
  }
  GetUserSidFromToken(v123, a2);
  v76 = 0;
  *(_OWORD *)DuplicateTokenHandle = 0;
  helium::CreatePackageGuids(v8, v123, &v76, DuplicateTokenHandle);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v124) < 0xF )
    std::_Xlen_string();
  v19 = v123;
  if ( v125 > 7 )
    v19 = (_QWORD *)v123[0];
  std::wstring::wstring(v97, v17, v18, L"\\Registry\\user\\", 15, v19, v124);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v98) < 8 )
    std::_Xlen_string();
  v22 = v97;
  if ( v99 > 7 )
    v22 = (_QWORD *)v97[0];
  std::wstring::wstring(v120, v20, v21, v22, v98, L"_Classes", 8);
  v23 = 7;
  v180 = 0;
  v181 = 0;
  v182 = 7;
  LOWORD(v180) = 0;
  memset(v183, 0, sizeof(v183));
  v184 = 0;
  v185 = 0;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    &v180,
    8,
    v24,
    L"software");
  v89 = 0;
  v90.m128i_i64[0] = 0;
  v90.m128i_i64[1] = 7;
  LOWORD(v89) = 0;
  v91 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v92 = si128;
  LOWORD(v91) = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    &v89,
    26,
    v26,
    L"\\Registry\\machine\\software");
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v183,
    &v89);
  v81 = 0;
  v82 = si128;
  LOWORD(v81) = 0;
  v83 = 0;
  v84 = si128;
  LOWORD(v83) = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  std::wstring::operator=(&v83, v11);
  __SET_PAIR__(v28, v27, v76);
  v85 = v76;
  v87 = 1;
  BYTE1(v86) = 1;
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v183,
    &v81);
  std::wstring::~wstring(&v83);
  std::wstring::~wstring(&v81);
  std::wstring::~wstring(&v91);
  std::wstring::~wstring(&v89);
  v147 = 0;
  v149 = 7;
  memset(v150, 0, sizeof(v150));
  v151 = 0;
  v152 = 0;
  v148 = 3;
  v145 = *(_DWORD *)L"com";
  v146 = aCom_0[2];
  v81 = 0;
  v82 = si128;
  LOWORD(v81) = 0;
  v83 = 0;
  v84 = si128;
  LOWORD(v83) = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  std::wstring::operator=(&v83, v11 + 4);
  v85 = *(_OWORD *)DuplicateTokenHandle;
  v29 = DuplicateTokenHandle[1];
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v150,
    &v81);
  v89 = 0;
  v90 = si128;
  LOWORD(v89) = 0;
  v91 = 0;
  v92 = si128;
  LOWORD(v91) = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  std::wstring::operator=(&v91, v11);
  v93 = __PAIR128__(v28, v27);
  v95 = 1;
  BYTE1(v94) = 1;
  std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
    v150,
    &v89);
  std::wstring::~wstring(&v91);
  std::wstring::~wstring(&v89);
  std::wstring::~wstring(&v83);
  std::wstring::~wstring(&v81);
  v78 = 0;
  v79 = 0;
  *(_OWORD *)v74 = 0;
  v75 = 0;
  v31 = 0;
  if ( a7 != 2 && !a6 )
  {
    WriteVirtualization::RegistryPath::RegistryPath(
      (WriteVirtualization::RegistryPath *)lpString2,
      (const unsigned __int16 *const *)&off_1800D17C8);
    WriteVirtualization::RegistryPath::RegistryPath(
      (WriteVirtualization::RegistryPath *)v117,
      (const unsigned __int16 *const *)&off_1800D17C0);
    helium::GetRegistryWriteVirtualizationExclusions(v80, v8, v80[0]);
    v32 = (__int64 *)v80[0];
    v33 = *(__int64 **)v80[0];
    while ( 1 )
    {
      if ( v33 == v32 )
      {
        std::_Tree<std::_Tset_traits<WriteVirtualization::NormalizedFileSystemPath,std::less<WriteVirtualization::NormalizedFileSystemPath>,std::allocator<WriteVirtualization::NormalizedFileSystemPath>,0>>::~_Tree<std::_Tset_traits<WriteVirtualization::NormalizedFileSystemPath,std::less<WriteVirtualization::NormalizedFileSystemPath>,std::allocator<WriteVirtualization::NormalizedFileSystemPath>,0>>(v80);
        std::wstring::~wstring(v117);
        std::wstring::~wstring(lpString2);
        if ( v31 )
        {
          v55 = (char *)v74[1];
          v56 = (char *)v74[0];
          if ( v74[0] != v74[1] )
          {
            do
            {
              std::wstring::~wstring(v56 + 64);
              std::wstring::~wstring(v56 + 32);
              std::wstring::~wstring(v56);
              v56 += 104;
            }
            while ( v56 != v55 );
            v74[1] = v74[0];
          }
        }
        v10 = v73;
        v11 = a5;
        goto LABEL_57;
      }
      v34 = (const WCHAR **)(v33 + 4);
      v35 = (const WCHAR *)lpString2;
      if ( v129 > 7 )
        v35 = lpString2[0];
      v36 = (unsigned __int64)v33[7] <= 7 ? (const WCHAR *)(v33 + 4) : *v34;
      if ( CompareStringOrdinal(v36, *((_DWORD *)v33 + 12), v35, cchCount2, 1) == 2 )
        break;
      v41 = (const WCHAR *)v117;
      if ( v119 > 7 )
        v41 = v117[0];
      if ( (unsigned __int64)v33[7] <= 7 )
        v42 = (const WCHAR *)(v33 + 4);
      else
        v42 = *v34;
      if ( CompareStringOrdinal(v42, *((_DWORD *)v33 + 12), v41, v118, 1) == 2 )
        goto LABEL_32;
      if ( WriteVirtualization::RegistryPath::IsAncestorOf(
             (LPCWCH)v117,
             (const struct WriteVirtualization::RegistryPath *)(v33 + 4)) )
      {
        v46 = WriteVirtualization::RegistryPath::PathRelativeTo(v33 + 4, v187, v117);
        if ( v121 == 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        v47 = v120;
        if ( v122 > 7 )
          v47 = (_QWORD *)v120[0];
        std::wstring::wstring(v126, v121, v45, v47, v121, L"\\", 1);
        v23 |= 0x20u;
        v48 = std::operator+<unsigned short>(v189, v126, v46);
        helium::AddExitNode(v74, v48);
        std::wstring::~wstring(v189);
        std::wstring::~wstring(v126);
        v49 = v187;
      }
      else
      {
        if ( v98 == 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        v50 = v97;
        if ( v99 > 7 )
          v50 = (_QWORD *)v97[0];
        std::wstring::wstring(v126, v43, v44, v50, v98, L"\\", 1);
        v23 |= 0x40u;
        v51 = std::operator+<unsigned short>(v187, v126, v33 + 4);
        helium::AddExitNode(&v78, v51);
        std::wstring::~wstring(v187);
        v49 = v126;
      }
      std::wstring::~wstring(v49);
LABEL_43:
      v52 = (__int64 **)v33[2];
      if ( *((_BYTE *)v52 + 25) )
      {
        for ( i = (__int64 *)v33[1]; !*((_BYTE *)i + 25) && v33 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v33 = i;
        v33 = i;
      }
      else
      {
        v33 = (__int64 *)v33[2];
        for ( j = *v52; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v33 = j;
      }
    }
    if ( v98 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v39 = v97;
    if ( v99 > 7 )
      v39 = (_QWORD *)v97[0];
    std::wstring::wstring(Src, v37, v38, v39, v98, L"\\", 1);
    v40 = std::wstring::_Append<unsigned short>(Src);
    v186[0] = *(_OWORD *)v40;
    v186[1] = *(_OWORD *)(v40 + 16);
    *(_QWORD *)(v40 + 16) = 0;
    *(_QWORD *)(v40 + 24) = 7;
    *(_WORD *)v40 = 0;
    v23 |= 0x18u;
    helium::AddExitNode(&v78, v186);
    std::wstring::~wstring(v186);
    std::wstring::~wstring(Src);
LABEL_32:
    v31 = 1;
    goto LABEL_43;
  }
LABEL_57:
  v174 = 0;
  v175 = 0;
  v176 = 7;
  LOWORD(v174) = 0;
  memset(v177, 0, sizeof(v177));
  v178 = 0;
  v179 = 0;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    &v174,
    8,
    v30,
    L"user_sid");
  if ( a7 == 2 )
  {
    v58 = v76;
  }
  else
  {
    v100 = 0;
    v101 = si128;
    LOWORD(v100) = 0;
    v102 = 0;
    v103 = si128;
    LOWORD(v102) = 0;
    v104 = 0;
    v105 = 0;
    v106 = 0;
    v107 = 0;
    std::wstring::operator=(&v100, v97);
    std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
      v177,
      &v100);
    if ( v11[10] )
    {
      v81 = 0;
      v82 = si128;
      LOWORD(v81) = 0;
      v83 = 0;
      v84 = si128;
      LOWORD(v83) = 0;
      v85 = 0;
      v86 = 0;
      v87 = 0;
      v88 = 0;
      std::wstring::operator=(&v83, v11 + 8);
      *(void **)&v85 = DuplicateTokenHandle[0];
      *((_QWORD *)&v85 + 1) = v29;
      *(_WORD *)((char *)&v86 + 1) = 257;
      v87 = 1;
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v177,
        &v81);
      std::wstring::~wstring(&v83);
      std::wstring::~wstring(&v81);
    }
    if ( v11[18] )
    {
      v89 = 0;
      v90 = si128;
      LOWORD(v89) = 0;
      v91 = 0;
      v92 = si128;
      LOWORD(v91) = 0;
      v93 = 0;
      v94 = 0;
      v95 = 0;
      v96 = 0;
      std::wstring::operator=(&v91, v11 + 16);
      v58 = v76;
      *(_QWORD *)&v93 = v76;
      *((_QWORD *)&v93 + 1) = v28;
      BYTE2(v94) = 1;
      v96 = *((_QWORD *)v10 + 75);
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v177,
        &v89);
      std::wstring::~wstring(&v91);
      std::wstring::~wstring(&v89);
    }
    else
    {
      v58 = v76;
    }
    std::wstring::~wstring(&v102);
    std::wstring::~wstring(&v100);
  }
  v168 = 0;
  v169 = 0;
  v170 = 7;
  LOWORD(v168) = 0;
  memset(v171, 0, sizeof(v171));
  v172 = 0;
  v173 = 0;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    &v168,
    12,
    v57,
    L"user_classes");
  if ( a7 != 2 )
  {
    v100 = 0;
    v101 = si128;
    LOWORD(v100) = 0;
    v102 = 0;
    v103 = si128;
    LOWORD(v102) = 0;
    v104 = 0;
    v105 = 0;
    v106 = 0;
    v107 = 0;
    std::wstring::operator=(&v100, v120);
    std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
      v171,
      &v100);
    if ( v11[14] )
    {
      v81 = 0;
      v82 = si128;
      LOWORD(v81) = 0;
      v83 = 0;
      v84 = si128;
      LOWORD(v83) = 0;
      v85 = 0;
      v86 = 0;
      v87 = 0;
      v88 = 0;
      std::wstring::operator=(&v83, v11 + 12);
      *(void **)&v85 = DuplicateTokenHandle[0];
      *((_QWORD *)&v85 + 1) = v29;
      *(_WORD *)((char *)&v86 + 1) = 257;
      v87 = 1;
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v171,
        &v81);
      std::wstring::~wstring(&v83);
      std::wstring::~wstring(&v81);
    }
    if ( v11[22] && !v31 )
    {
      v89 = 0;
      v90 = si128;
      LOWORD(v89) = 0;
      v91 = 0;
      v92 = si128;
      LOWORD(v91) = 0;
      v93 = 0;
      v94 = 0;
      v95 = 0;
      v96 = 0;
      std::wstring::operator=(&v91, v11 + 20);
      *(_QWORD *)&v93 = v58;
      *((_QWORD *)&v93 + 1) = v28;
      BYTE2(v94) = 1;
      v96 = *((_QWORD *)v10 + 75);
      std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(
        v171,
        &v89);
      std::wstring::~wstring(&v91);
      std::wstring::~wstring(&v89);
    }
    std::wstring::~wstring(&v102);
    std::wstring::~wstring(&v100);
  }
  v108 = 0;
  v109 = 0;
  v110 = 7;
  LOWORD(v108) = 0;
  *(_OWORD *)v111 = 0;
  v112 = 0;
  v113 = 7;
  LOWORD(v111[0]) = 0;
  v114[0] = 0;
  v114[1] = si128;
  LOWORD(v114[0]) = 0;
  v115 = 0;
  v116 = 0;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    &v108,
    9,
    v59,
    L"\\registry");
  if ( v113 < 9 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v111,
      9,
      v60,
      L"\\registry");
  }
  else
  {
    v61 = v111[0];
    v112 = 9;
    memmove_0(v111[0], L"\\registry", 0x12u);
    v61[9] = 0;
  }
  v140[0] = 0;
  v140[1] = si128;
  LOWORD(v140[0]) = 0;
  v141[0] = 0;
  v141[1] = si128;
  LOWORD(v141[0]) = 0;
  v142[0] = 0;
  v142[1] = si128;
  LOWORD(v142[0]) = 0;
  v143 = 0;
  v144 = 0;
  std::wstring::operator=(v140, L"\\registry\\machine");
  std::wstring::operator=(v141, L"\\registry\\machine");
  LOBYTE(v144) = 1;
  v135[0] = 0;
  v135[1] = si128;
  LOWORD(v135[0]) = 0;
  v136[0] = 0;
  v136[1] = si128;
  LOWORD(v136[0]) = 0;
  v137[0] = 0;
  v137[1] = si128;
  LOWORD(v137[0]) = 0;
  v138 = 0;
  v139 = 0;
  std::wstring::operator=(v135, L"\\registry\\machine\\software");
  std::wstring::operator=(v137, L"software");
  LOBYTE(v139) = 1;
  v163[0] = 0;
  v163[1] = si128;
  LOWORD(v163[0]) = 0;
  v164[0] = 0;
  v164[1] = si128;
  LOWORD(v164[0]) = 0;
  v165[0] = 0;
  v165[1] = si128;
  LOWORD(v165[0]) = 0;
  v166 = 0;
  v167 = 0;
  v158[0] = 0;
  v158[1] = si128;
  LOWORD(v158[0]) = 0;
  v159[0] = 0;
  v159[1] = si128;
  LOWORD(v159[0]) = 0;
  v160[0] = 0;
  v160[1] = si128;
  LOWORD(v160[0]) = 0;
  v161 = 0;
  v162 = 0;
  v153[0] = 0;
  v153[1] = si128;
  LOWORD(v153[0]) = 0;
  v154[0] = 0;
  v154[1] = si128;
  LOWORD(v154[0]) = 0;
  v155[0] = 0;
  v155[1] = si128;
  LOWORD(v155[0]) = 0;
  v156 = 0;
  v157 = 0;
  if ( a7 != 2 )
  {
    std::wstring::operator=(v163, L"\\registry\\user");
    std::wstring::operator=(v164, L"\\registry\\user");
    std::wstring::operator=(v158, v97);
    std::wstring::operator=(v160, L"user_sid");
    std::wstring::operator=(v153, v120);
    std::wstring::operator=(v155, L"user_classes");
  }
  v130[0] = 0;
  v130[1] = si128;
  LOWORD(v130[0]) = 0;
  v131[0] = 0;
  v131[1] = si128;
  LOWORD(v131[0]) = 0;
  v132[0] = 0;
  v132[1] = si128;
  LOWORD(v132[0]) = 0;
  v133 = 0;
  v134 = 0;
  std::wstring::operator=(v130, L"\\registry\\comroot");
  std::wstring::operator=(v132, L"COM");
  LOBYTE(v134) = 1;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  v70 = 0;
  if ( a7 == 2 )
  {
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::reserve(&v69, 2);
    v62 = 3;
  }
  else
  {
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::reserve(&v69, 4);
    v62 = 0x4EC4EC4EC4EC4EC5LL * (((char *)v74[1] - (char *)v74[0]) >> 3)
        + 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*((_QWORD *)&v78 + 1) - v78) >> 3)
        + 6;
  }
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::reserve(&v68[3], v62);
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
    &v69,
    &v180);
  if ( a7 != 2 )
  {
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
      &v69,
      &v174);
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
      &v69,
      &v168);
  }
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::emplace_back<Schema::Containers::Definition::RegistryHiveStack>(
    &v69,
    &v145);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v68[3],
    &v108);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v68[3],
    v140);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v68[3],
    v135);
  if ( a7 != 2 )
  {
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
      &v68[3],
      v163);
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
      &v68[3],
      v158);
    v64 = *((_QWORD *)&v78 + 1);
    for ( k = v78; k != v64; k += 104 )
      std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode const>(
        &v68[3],
        k);
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
      &v68[3],
      v153);
    v65 = (char *)v74[0];
    v66 = (char *)v74[1];
    while ( v65 != v66 )
    {
      std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode const>(
        &v68[3],
        v65);
      v65 += 104;
    }
  }
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::emplace_back<Schema::Containers::Definition::RegistryRedirectionNode>(
    &v68[3],
    v130);
  if ( (_QWORD *)((char *)v10 + 320) != v68 )
  {
    std::vector<Schema::Containers::Definition::RegistrySymlink>::_Tidy((char *)v10 + 320);
    *((_QWORD *)v10 + 40) = v68[0];
    *(_OWORD *)((char *)v10 + 328) = *(_OWORD *)&v68[1];
    memset(v68, 0, 24);
  }
  if ( (_QWORD *)((char *)v10 + 344) != &v68[3] )
  {
    std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy((char *)v10 + 344);
    *(_OWORD *)((char *)v10 + 344) = *(_OWORD *)&v68[3];
    *((_QWORD *)v10 + 45) = v68[5];
    memset(&v68[3], 0, 24);
  }
  if ( (__int128 *)((char *)v10 + 368) != &v69 )
  {
    std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Tidy((char *)v10 + 368);
    *((_OWORD *)v10 + 23) = v69;
    *((_QWORD *)v10 + 48) = v70;
    v69 = 0;
    v70 = 0;
  }
  *((_BYTE *)v10 + 392) = 1;
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Tidy(&v69);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(&v68[3]);
  std::vector<Schema::Containers::Definition::RegistrySymlink>::_Tidy(v68);
  std::wstring::~wstring(v132);
  std::wstring::~wstring(v131);
  std::wstring::~wstring(v130);
  std::wstring::~wstring(v155);
  std::wstring::~wstring(v154);
  std::wstring::~wstring(v153);
  std::wstring::~wstring(v160);
  std::wstring::~wstring(v159);
  std::wstring::~wstring(v158);
  std::wstring::~wstring(v165);
  std::wstring::~wstring(v164);
  std::wstring::~wstring(v163);
  std::wstring::~wstring(v137);
  std::wstring::~wstring(v136);
  std::wstring::~wstring(v135);
  std::wstring::~wstring(v142);
  std::wstring::~wstring(v141);
  std::wstring::~wstring(v140);
  std::wstring::~wstring(v114);
  std::wstring::~wstring(v111);
  std::wstring::~wstring(&v108);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v172);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v171[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v171);
  std::wstring::~wstring(&v168);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v178);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v177[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v177);
  std::wstring::~wstring(&v174);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(v74);
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Tidy(&v78);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v151);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v150[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v150);
  std::wstring::~wstring(&v145);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v184);
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::~vector<Schema::Containers::Definition::RegistryMakeKey>((char *)&v183[1] + 8);
  std::vector<Schema::Containers::Definition::RegistryLayer>::~vector<Schema::Containers::Definition::RegistryLayer>(v183);
  std::wstring::~wstring(&v180);
  std::wstring::~wstring(v120);
  std::wstring::~wstring(v97);
  std::wstring::~wstring(v123);
  return v10;
}

```

## disassembly

```asm
0x1800764dc  mov     rax, rsp
0x1800764df  mov     [rax+18h], rbx
0x1800764e3  push    rbp
0x1800764e4  push    rsi
0x1800764e5  push    rdi
0x1800764e6  push    r12
0x1800764e8  push    r13
0x1800764ea  push    r14
0x1800764ec  push    r15
0x1800764ee  lea     rbp, [rax-7B8h]
0x1800764f5  sub     rsp, 880h
0x1800764fc  movaps  xmmword ptr [rax-48h], xmm6
0x180076500  mov     rax, cs:__security_cookie
0x180076507  xor     rax, rsp
0x18007650a  mov     [rbp+7B0h+var_50], rax
0x180076511  mov     rbx, r9
0x180076514  mov     [rbp+7B0h+var_7C8], rbx
0x180076518  mov     r14, rdx
0x18007651b  mov     r15, rcx
0x18007651e  mov     [rbp+7B0h+var_7F8], rcx
0x180076522  mov     [rbp+7B0h+var_790], rcx
0x180076526  mov     rdi, [rbp+7B0h+arg_20]
0x18007652d  mov     qword ptr [rsp+8B0h+var_868], rdi
0x180076532  mov     rax, [rbp+7B0h+arg_38]
0x180076539  mov     [rbp+7B0h+var_7A8], rax
0x18007653d  xor     r13d, r13d
0x180076540  mov     dword ptr [rsp+8B0h+var_870], r13d
0x180076545  call    ??0Container@Definition@Containers@Schema@@QEAA@XZ; Schema::Containers::Definition::Container::Container(void)
0x18007654a  lea     rax, [rcx+258h]
0x180076551  mov     [rax], r13
0x180076554  mov     dword ptr [rsp+8B0h+var_870], 1
0x18007655c  mov     [rbp+7B0h+DuplicateTokenHandle], rax
0x180076560  mov     [rbp+7B0h+DuplicateTokenHandle+8], r13
0x180076564  mov     [rbp+7B0h+var_800], 1
0x180076568  lea     r8, [rbp+7B0h+DuplicateTokenHandle+8]; DuplicateTokenHandle
0x18007656c  lea     edx, [r13+2]; ImpersonationLevel
0x180076570  mov     rcx, r14; ExistingTokenHandle
0x180076573  call    cs:__imp_DuplicateToken
0x18007657a  nop     dword ptr [rax+rax+00h]
0x18007657f  mov     rcx, [rbp+7B8h]; this
0x180076586  test    eax, eax
0x180076588  jz      loc_180077B4A
0x18007658e  cmp     [rbp+7B0h+var_800], r13b
0x180076592  jz      short loc_1800765E0
0x180076594  mov     r12, [rbp+7B0h+DuplicateTokenHandle+8]
0x180076598  mov     rdi, [rbp+7B0h+DuplicateTokenHandle]
0x18007659c  mov     rsi, [rdi]
0x18007659f  lea     rax, [rsi-1]
0x1800765a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800765a7  ja      short loc_1800765D8
0x1800765a9  call    cs:__imp_GetLastError
0x1800765b0  nop     dword ptr [rax+rax+00h]
0x1800765b5  mov     ebx, eax
0x1800765b7  mov     rcx, rsi; hObject
0x1800765ba  call    cs:__imp_CloseHandle
0x1800765c1  nop     dword ptr [rax+rax+00h]
0x1800765c6  mov     ecx, ebx; dwErrCode
0x1800765c8  call    cs:__imp_SetLastError
0x1800765cf  nop     dword ptr [rax+rax+00h]
0x1800765d4  mov     rbx, [rbp+7B0h+var_7C8]
0x1800765d8  mov     [rdi], r12
0x1800765db  mov     rdi, qword ptr [rsp+8B0h+var_868]
0x1800765e0  mov     rdx, r14
0x1800765e3  lea     rcx, [rbp+7B0h+var_590]
0x1800765ea  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x1800765ef  nop
0x1800765f0  xorps   xmm0, xmm0
0x1800765f3  movups  [rbp+7B0h+var_7D8], xmm0
0x1800765f7  xorps   xmm1, xmm1
0x1800765fa  movups  xmmword ptr [rbp+7B0h+DuplicateTokenHandle], xmm1
0x1800765fe  lea     r9, [rbp+7B0h+DuplicateTokenHandle]
0x180076602  lea     r8, [rbp+7B0h+var_7D8]
0x180076606  lea     rdx, [rbp+7B0h+var_590]
0x18007660d  mov     rcx, rbx
0x180076610  call    ?CreatePackageGuids@helium@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@PEAU_GUID@@2@Z; helium::CreatePackageGuids(std::wstring const &,std::wstring &,_GUID *,_GUID *)
0x180076615  mov     rcx, [rbp+7B0h+var_580]
0x18007661c  mov     r12, 7FFFFFFFFFFFFFFEh
0x180076626  mov     rax, r12
0x180076629  sub     rax, rcx
0x18007662c  cmp     rax, 0Fh
0x180076630  jb      loc_180077B5C
0x180076636  lea     rax, [rbp+7B0h+var_590]
0x18007663d  mov     r14d, 7
0x180076643  cmp     [rbp+7B0h+var_578], r14
0x18007664a  cmova   rax, [rbp+7B0h+var_590]
0x180076652  mov     [rsp+8B0h+var_880], rcx
0x180076657  mov     [rsp+8B0h+var_888], rax
0x18007665c  mov     qword ptr [rsp+8B0h+bIgnoreCase], 0Fh
0x180076665  lea     r9, aRegistryUser_0; "\\Registry\\user\\"
0x18007666c  lea     rcx, [rbp+7B0h+var_6C0]
0x180076673  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180076678  lea     esi, [r14-4]
0x18007667c  mov     dword ptr [rsp+8B0h+var_870], esi
0x180076680  mov     rcx, [rbp+7B0h+var_6B0]
0x180076687  mov     rax, r12
0x18007668a  sub     rax, rcx
0x18007668d  cmp     rax, 8
0x180076691  jb      loc_180077B62
0x180076697  lea     r9, [rbp+7B0h+var_6C0]
0x18007669e  cmp     [rbp+7B0h+var_6A8], r14
0x1800766a5  cmova   r9, [rbp+7B0h+var_6C0]
0x1800766ad  mov     [rsp+8B0h+var_880], 8
0x1800766b6  lea     rax, aClasses_1; "_Classes"
0x1800766bd  mov     [rsp+8B0h+var_888], rax
0x1800766c2  mov     qword ptr [rsp+8B0h+bIgnoreCase], rcx
0x1800766c7  lea     rcx, [rbp+7B0h+var_5B0]
0x1800766ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800766d3  mov     r12d, r14d
0x1800766d6  mov     dword ptr [rsp+8B0h+var_870], r14d
0x1800766db  xorps   xmm0, xmm0
0x1800766de  movups  [rbp+7B0h+var_140], xmm0
0x1800766e5  mov     [rbp+7B0h+var_130], r13
0x1800766ec  mov     [rbp+7B0h+var_128], r14
0x1800766f3  mov     word ptr [rbp+7B0h+var_140], r13w
0x1800766fb  movdqa  [rbp+7B0h+var_120], xmm0
0x180076703  xorps   xmm1, xmm1
0x180076706  movdqa  [rbp+7B0h+var_110], xmm1
0x18007670e  movdqa  [rbp+7B0h+var_100], xmm0
0x180076716  movdqa  [rbp+7B0h+var_F0], xmm1
0x18007671e  mov     [rbp+7B0h+var_E0], r13
0x180076725  lea     r9, aSoftware_0; "software"
0x18007672c  lea     edx, [rsi+5]
0x18007672f  lea     rcx, [rbp+7B0h+var_140]
0x180076736  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18007673b  xorps   xmm0, xmm0
0x18007673e  movups  [rbp+7B0h+var_720], xmm0
0x180076745  mov     qword ptr [rbp+7B0h+var_710], r13
0x18007674c  mov     qword ptr [rbp+7B0h+var_710+8], r14
0x180076753  mov     word ptr [rbp+7B0h+var_720], r13w
0x18007675b  movups  [rbp+7B0h+var_700], xmm0
0x180076762  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007676a  movdqa  [rbp+7B0h+var_6F0], xmm6
0x180076772  mov     word ptr [rbp+7B0h+var_700], r13w
0x18007677a  movups  [rbp+7B0h+var_6E0], xmm0
0x180076781  mov     [rbp+7B0h+var_6D0], r13d
0x180076788  mov     [rbp+7B0h+var_6CC], r13b
0x18007678f  mov     [rbp+7B0h+var_6C8], r13
0x180076796  lea     edx, [rsi+17h]
0x180076799  lea     r9, aRegistryMachin_0; "\\Registry\\machine\\software"
0x1800767a0  lea     rcx, [rbp+7B0h+var_720]
0x1800767a7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800767ac  lea     rdx, [rbp+7B0h+var_720]
0x1800767b3  lea     rcx, [rbp+7B0h+var_120]
0x1800767ba  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(Schema::Containers::Definition::RegistryLayer &&)
0x1800767bf  xorps   xmm0, xmm0
0x1800767c2  movups  [rbp+7B0h+var_780], xmm0
0x1800767c6  movdqa  [rbp+7B0h+var_770], xmm6
0x1800767cb  mov     word ptr [rbp+7B0h+var_780], r13w
0x1800767d0  movups  [rbp+7B0h+var_760], xmm0
0x1800767d4  movdqa  [rbp+7B0h+var_750], xmm6
0x1800767d9  mov     word ptr [rbp+7B0h+var_760], r13w
0x1800767de  movups  [rbp+7B0h+var_740], xmm0
0x1800767e2  mov     [rbp+7B0h+var_730], r13d
0x1800767e9  mov     [rbp+7B0h+var_72C], r13b
0x1800767f0  mov     [rbp+7B0h+var_728], r13
0x1800767f7  mov     rdx, rdi
0x1800767fa  lea     rcx, [rbp+7B0h+var_760]
0x1800767fe  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180076803  mov     r13, qword ptr [rbp+7B0h+var_7D8]
0x180076807  mov     qword ptr [rbp+7B0h+var_740], r13
0x18007680b  mov     r14, qword ptr [rbp+7B0h+var_7D8+8]
0x18007680f  mov     qword ptr [rbp+7B0h+var_740+8], r14
0x180076813  mov     [rbp+7B0h+var_72C], 1
0x18007681a  mov     byte ptr [rbp+7B0h+var_730+1], 1
0x180076821  lea     rdx, [rbp+7B0h+var_780]
0x180076825  lea     rcx, [rbp+7B0h+var_120]
0x18007682c  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(Schema::Containers::Definition::RegistryLayer &&)
0x180076831  nop
0x180076832  lea     rcx, [rbp+7B0h+var_760]; void *
0x180076836  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007683b  lea     rcx, [rbp+7B0h+var_780]; void *
0x18007683f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076844  nop
0x180076845  lea     rcx, [rbp+7B0h+var_700]; void *
0x18007684c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076851  lea     rcx, [rbp+7B0h+var_720]; void *
0x180076858  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007685d  xorps   xmm0, xmm0
0x180076860  movups  [rbp+7B0h+var_3E0], xmm0
0x180076867  mov     [rbp+7B0h+var_3C8], 7
0x180076872  xor     ecx, ecx
0x180076874  movdqa  [rbp+7B0h+var_3C0], xmm0
0x18007687c  xorps   xmm1, xmm1
0x18007687f  movdqa  [rbp+7B0h+var_3B0], xmm1
0x180076887  movdqa  [rbp+7B0h+var_3A0], xmm0
0x18007688f  movdqa  [rbp+7B0h+var_390], xmm1
0x180076897  mov     [rbp+7B0h+var_380], rcx
0x18007689e  mov     [rbp+7B0h+var_3D0], rsi
0x1800768a5  mov     rax, qword ptr cs:aCom_0; "com"
0x1800768ac  mov     dword ptr [rbp+7B0h+var_3E0], eax
0x1800768b2  movzx   eax, word ptr cs:aCom_0+4; "m"
0x1800768b9  mov     word ptr [rbp+7B0h+var_3E0+4], ax
0x1800768c0  mov     word ptr [rbp+7B0h+var_3E0+6], cx
0x1800768c7  movups  [rbp+7B0h+var_780], xmm0
0x1800768cb  movdqa  [rbp+7B0h+var_770], xmm6
0x1800768d0  mov     word ptr [rbp+7B0h+var_780], cx
0x1800768d4  movups  [rbp+7B0h+var_760], xmm0
0x1800768d8  movdqa  [rbp+7B0h+var_750], xmm6
0x1800768dd  mov     word ptr [rbp+7B0h+var_760], cx
0x1800768e1  movups  [rbp+7B0h+var_740], xmm0
0x1800768e5  mov     [rbp+7B0h+var_730], ecx
0x1800768eb  mov     [rbp+7B0h+var_72C], cl
0x1800768f1  mov     [rbp+7B0h+var_728], rcx
0x1800768f8  lea     rdx, [rdi+20h]
0x1800768fc  lea     rcx, [rbp+7B0h+var_760]
0x180076900  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180076905  mov     rax, [rbp+7B0h+DuplicateTokenHandle]
0x180076909  mov     qword ptr [rbp+7B0h+var_740], rax
0x18007690d  mov     rsi, [rbp+7B0h+DuplicateTokenHandle+8]
0x180076911  mov     qword ptr [rbp+7B0h+var_740+8], rsi
0x180076915  lea     rdx, [rbp+7B0h+var_780]
0x180076919  lea     rcx, [rbp+7B0h+var_3C0]
0x180076920  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(Schema::Containers::Definition::RegistryLayer &&)
0x180076925  xorps   xmm0, xmm0
0x180076928  movups  [rbp+7B0h+var_720], xmm0
0x18007692f  movdqa  [rbp+7B0h+var_710], xmm6
0x180076937  xor     ecx, ecx
0x180076939  mov     word ptr [rbp+7B0h+var_720], cx
0x180076940  movups  [rbp+7B0h+var_700], xmm0
0x180076947  movdqa  [rbp+7B0h+var_6F0], xmm6
0x18007694f  mov     word ptr [rbp+7B0h+var_700], cx
0x180076956  movups  [rbp+7B0h+var_6E0], xmm0
0x18007695d  mov     [rbp+7B0h+var_6D0], ecx
0x180076963  mov     [rbp+7B0h+var_6CC], cl
0x180076969  mov     [rbp+7B0h+var_6C8], rcx
0x180076970  mov     rdx, rdi
0x180076973  lea     rcx, [rbp+7B0h+var_700]
0x18007697a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007697f  mov     qword ptr [rbp+7B0h+var_6E0], r13
0x180076986  mov     qword ptr [rbp+7B0h+var_6E0+8], r14
0x18007698d  mov     [rbp+7B0h+var_6CC], 1
0x180076994  mov     byte ptr [rbp+7B0h+var_6D0+1], 1
0x18007699b  lea     rdx, [rbp+7B0h+var_720]
0x1800769a2  lea     rcx, [rbp+7B0h+var_3C0]
0x1800769a9  call    ??$emplace_back@URegistryLayer@Definition@Containers@Schema@@@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAAAEAURegistryLayer@Definition@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Definition::RegistryLayer>::emplace_back<Schema::Containers::Definition::RegistryLayer>(Schema::Containers::Definition::RegistryLayer &&)
0x1800769ae  nop
0x1800769af  lea     rcx, [rbp+7B0h+var_700]; void *
0x1800769b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800769bb  lea     rcx, [rbp+7B0h+var_720]; void *
0x1800769c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800769c7  nop
0x1800769c8  lea     rcx, [rbp+7B0h+var_760]; void *
0x1800769cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800769d1  lea     rcx, [rbp+7B0h+var_780]; void *
0x1800769d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800769da  xorps   xmm0, xmm0
0x1800769dd  movdqu  [rbp+7B0h+var_7C0], xmm0
0x1800769e2  xor     eax, eax
0x1800769e4  mov     [rbp+7B0h+var_7B0], rax
0x1800769e8  movdqu  xmmword ptr [rbp+7B0h+var_7F0], xmm0
0x1800769ed  mov     [rbp+7B0h+var_7E0], rax
0x1800769f1  mov     r13b, al
0x1800769f4  cmp     [rbp+7B0h+arg_30], 2
0x1800769fb  jz      loc_180076E11
0x180076a01  cmp     [rbp+7B0h+arg_28], al
0x180076a07  jnz     loc_180076E11
0x180076a0d  lea     rdx, off_1800D17C8; unsigned __int16 **
0x180076a14  lea     rcx, [rbp+7B0h+lpString2]; this
0x180076a1b  call    ??$?0AEBQEBG@RegistryPath@WriteVirtualization@@QEAA@AEBQEBG@Z; WriteVirtualization::RegistryPath::RegistryPath(ushort const * const &)
0x180076a20  nop
0x180076a21  lea     rdx, off_1800D17C0; unsigned __int16 **
0x180076a28  lea     rcx, [rbp+7B0h+var_5D0]; this
0x180076a2f  call    ??$?0AEBQEBG@RegistryPath@WriteVirtualization@@QEAA@AEBQEBG@Z; WriteVirtualization::RegistryPath::RegistryPath(ushort const * const &)
0x180076a34  nop
0x180076a35  mov     r8, [rbp+7B0h+var_7A8]
0x180076a39  mov     rdx, rbx
0x180076a3c  lea     rcx, [rbp+7B0h+var_7A8]
0x180076a40  call    ?GetRegistryWriteVirtualizationExclusions@helium@@YA?AV?$NormalizedExclusionPathList@VRegistryPath@WriteVirtualization@@@WriteVirtualization@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@5@@Z; helium::GetRegistryWriteVirtualizationExclusions(std::wstring const &,std::vector<WriteVirtualization::RegistryExclusion> const &)
0x180076a45  nop
0x180076a46  mov     rdi, [rbp+7B0h+var_7A8]
0x180076a4a  mov     rbx, [rdi]
0x180076a4d  cmp     rbx, rdi
0x180076a50  jz      loc_180076DA3
0x180076a56  lea     r15, [rbx+20h]
0x180076a5a  lea     r8, [rbp+7B0h+lpString2]
0x180076a61  cmp     [rbp+7B0h+var_538], 7
0x180076a69  cmova   r8, [rbp+7B0h+lpString2]; lpString2
0x180076a71  cmp     qword ptr [r15+18h], 7
0x180076a76  jbe     short loc_180076A7D
0x180076a78  mov     rcx, [r15]
0x180076a7b  jmp     short loc_180076A80
0x180076a7d  mov     rcx, r15; lpString1
0x180076a80  mov     [rsp+8B0h+bIgnoreCase], 1; bIgnoreCase
0x180076a88  mov     r9d, [rbp+7B0h+cchCount2]; cchCount2
0x180076a8f  mov     edx, [rbx+30h]; cchCount1
0x180076a92  call    cs:__imp_CompareStringOrdinal
0x180076a99  nop     dword ptr [rax+rax+00h]
0x180076a9e  cmp     eax, 2
0x180076aa1  jnz     loc_180076B86
0x180076aa7  mov     rcx, [rbp+7B0h+var_6B0]
0x180076aae  mov     rax, 7FFFFFFFFFFFFFFEh
0x180076ab8  sub     rax, rcx
0x180076abb  cmp     rax, 1
0x180076abf  jb      loc_180077B68
0x180076ac5  lea     r9, [rbp+7B0h+var_6C0]
0x180076acc  cmp     [rbp+7B0h+var_6A8], 7
0x180076ad4  cmova   r9, [rbp+7B0h+var_6C0]
0x180076adc  mov     [rsp+8B0h+var_880], 1
0x180076ae5  lea     rax, S; "\\"
0x180076aec  mov     [rsp+8B0h+var_888], rax
  ... truncated ...
```
