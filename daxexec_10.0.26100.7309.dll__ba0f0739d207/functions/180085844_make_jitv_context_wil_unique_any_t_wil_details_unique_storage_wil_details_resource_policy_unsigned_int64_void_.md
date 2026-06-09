# make_jitv_context(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,void (*)(unsigned __int64),&close_jitv_silo(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180085844`
- end: `0x180085fa5`
- name: `?make_jitv_context@@YA?AV?$shared_ptr@Vjitv_context@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AX_K@Z$1?close_jitv_silo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `1889`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180085350`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180009338`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x180013100`
- `0x180015ec8`
- `0x18002031c`
- `0x18002b240`
- `0x18002c4e4`
- `0x18002f468`
- `0x180034398`
- `0x180034460`
- `0x180037468`
- `0x1800374e0`
- `0x180037600`
- `0x18005120c`
- `0x18005ddfc`
- `0x1800814fc`
- `0x180084a8c`
- `0x180084e84`
- `0x180084fd4`
- `0x18008508c`
- `0x180085670`
- `0x180085844`
- `0x180087808`
- `0x18008aafc`
- `0x18008acd4`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800859f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800859f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180085a63`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180085a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085aba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085aba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180085a0c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180085a0c`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18008594f`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18008594f`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
_QWORD *__fastcall make_jitv_context(_QWORD *a1, unsigned __int64 *a2, char *a3)
{
  char *v3; // r13
  char *v4; // r14
  __int64 v5; // rdx
  int v6; // r12d
  const wchar_t *v7; // rcx
  signed __int64 v8; // r8
  __int64 v9; // r8
  PWSTR v10; // rdx
  const WCHAR *v11; // rcx
  unsigned int PackagesByPackageFamily; // eax
  DWORD CurrentProcessId; // eax
  WCHAR *v14; // rbx
  const char *v15; // r9
  void **v16; // rax
  const char *v17; // r9
  char *v18; // r15
  WCHAR *v19; // rbx
  PWSTR v20; // r13
  __int64 v21; // rdi
  __int64 v22; // rsi
  __int64 v23; // rax
  _QWORD *v24; // rdi
  _QWORD *v25; // rbx
  char *v26; // rsi
  char *v27; // rdi
  _QWORD *v28; // r14
  void (__fastcall ***v29)(_QWORD, __int64); // rsi
  _QWORD *v30; // rcx
  unsigned int bufferLength; // [rsp+20h] [rbp-E0h]
  UINT32 v33[2]; // [rsp+78h] [rbp-88h] BYREF
  PWSTR packageFullNames; // [rsp+80h] [rbp-80h] BYREF
  UINT32 count[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h] BYREF
  char *v37; // [rsp+A0h] [rbp-60h]
  char *v38; // [rsp+A8h] [rbp-58h]
  unsigned __int64 *v39; // [rsp+B0h] [rbp-50h]
  _QWORD *v40; // [rsp+B8h] [rbp-48h]
  __int128 v41; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  _QWORD v44[3]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR *v45; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR *v46; // [rsp+100h] [rbp+0h]
  __int128 v47; // [rsp+110h] [rbp+10h] BYREF
  __int64 v48; // [rsp+120h] [rbp+20h]
  __int128 v49; // [rsp+128h] [rbp+28h] BYREF
  __int64 v50; // [rsp+138h] [rbp+38h]
  __int128 v51; // [rsp+140h] [rbp+40h] BYREF
  __int64 v52; // [rsp+150h] [rbp+50h]
  __int128 v53; // [rsp+158h] [rbp+58h] BYREF
  __int64 v54; // [rsp+168h] [rbp+68h]
  _QWORD *v55; // [rsp+170h] [rbp+70h]
  unsigned __int64 *v56; // [rsp+178h] [rbp+78h]
  char v57[8]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD *v58; // [rsp+188h] [rbp+88h] BYREF
  char v59[40]; // [rsp+198h] [rbp+98h] BYREF
  char v60[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v61; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v62; // [rsp+1F0h] [rbp+F0h]
  __int64 v63; // [rsp+1F8h] [rbp+F8h]
  _BYTE v64[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v65[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v66[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v67[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v68[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v69[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR buffer[128]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v3 = a3;
  v38 = a3;
  v39 = a2;
  v40 = a1;
  v55 = a1;
  v56 = a2;
  v4 = 0;
  v5 = *((_QWORD *)a3 + 2);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(char **)a3;
  v6 = 2;
  if ( v5 == 38 )
  {
    v7 = L"Microsoft.Office.Desktop_8wekyb3d8bbwe";
    v8 = a3 - (char *)L"Microsoft.Office.Desktop_8wekyb3d8bbwe";
    while ( *(const wchar_t *)((char *)v7 + v8) == *v7 )
    {
      ++v7;
      if ( !--v5 )
      {
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v9 = 83;
        v10 = L"Microsoft.Office.Desktop_8wekyb3d8bbwe_LOOSE_FILE_REGISTERED_C2RX_PACKAGE_FULL_NAME";
        goto LABEL_14;
      }
    }
  }
  packageFullNames = 0;
  count[0] = 1;
  memset_0(buffer, 0, sizeof(buffer));
  v33[0] = 128;
  v11 = (const WCHAR *)v3;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v11 = *(const WCHAR **)v3;
  PackagesByPackageFamily = FindPackagesByPackageFamily(v11, 0x10u, count, &packageFullNames, v33, buffer, 0);
  if ( PackagesByPackageFamily )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
      (const char *)PackagesByPackageFamily,
      bufferLength);
  if ( !count[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
      (const char *)0x80070554LL,
      bufferLength);
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v10 = packageFullNames;
  v9 = -1;
  do
    ++v9;
  while ( packageFullNames[v9] );
LABEL_14:
  std::wstring::_Construct<1,unsigned short const *>(&v61, v10, v9);
  get_package_path(v69, &v61);
  v53 = 0;
  v54 = 0;
  v51 = 0;
  v52 = 0;
  v49 = 0;
  v50 = 0;
  v47 = 0;
  v48 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v14 = (WCHAR *)OpenProcess(0x20410u, 0, CurrentProcessId);
  packageFullNames = v14;
  if ( (((unsigned __int64)v14 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && !v14 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
      v15);
  *(_QWORD *)v33 = 0;
  v16 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(v33);
  if ( !OpenProcessToken(v14, 0x20008u, v16) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
      v17);
  if ( (unsigned __int64)v14 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  helium::MakeHeliumSpecification(count, &v61, *(_QWORD *)v33);
  if ( (unsigned __int64)(*(_QWORD *)v33 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)v33);
  DesktopAppXVFS::GenerateVfsMappings(
    (unsigned int)&v45,
    (unsigned int)&v53,
    count[0],
    0,
    (__int64)v69,
    (__int64)&v51,
    (__int64)&v49,
    1,
    1,
    0,
    0,
    0,
    (__int64)&v47);
  v36 = 0;
  v37 = 0;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v57);
  packageFullNames = v46;
  v18 = (char *)*((_QWORD *)&v36 + 1);
  if ( v45 != v46 )
  {
    v19 = v45 + 16;
    v20 = v46;
    do
    {
      std::wstring::wstring(v67, v19);
      v6 |= 8u;
      v21 = *((_QWORD *)v19 + 4);
      v22 = *((_QWORD *)v19 + 5);
      if ( v21 != v22 )
      {
        do
        {
          std::wstring::wstring(v68, v21);
          v6 |= 0x10u;
          v23 = std::wstring::wstring(v60, v19 - 16);
          vfs_mapping::vfs_mapping(v64, v23, v67, v68);
          std::wstring::~wstring(v68);
          if ( v18 == v4 )
          {
            std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(&v36, v18, v64);
            v18 = (char *)*((_QWORD *)&v36 + 1);
            v4 = v37;
          }
          else
          {
            *(_QWORD *)v33 = v18;
            std::wstring::wstring(v18, v64);
            std::wstring::wstring(v18 + 32, v65);
            std::wstring::wstring(v18 + 64, v66);
            v18 += 96;
            *((_QWORD *)&v36 + 1) = v18;
          }
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(
            v57,
            &v41,
            v67);
          std::wstring::~wstring(v66);
          std::wstring::~wstring(v65);
          std::wstring::~wstring(v64);
          v21 += 32;
        }
        while ( v21 != v22 );
        v20 = packageFullNames;
      }
      std::wstring::~wstring(v67);
      v19 += 60;
    }
    while ( v19 - 16 != v20 );
    v3 = v38;
  }
  v24 = v58;
  v25 = (_QWORD *)*v58;
  v26 = v37;
  while ( v25 != v24 )
  {
    v41 = 0;
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v41, &String1, 0);
    vfs_mapping::vfs_mapping(v64, &v41, v25 + 2, v25 + 2);
    if ( v18 == v26 )
    {
      std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(&v36, v18, v64);
      v18 = (char *)*((_QWORD *)&v36 + 1);
      v26 = v37;
    }
    else
    {
      v38 = v18;
      std::wstring::wstring(v18, v64);
      std::wstring::wstring(v18 + 32, v65);
      std::wstring::wstring(v18 + 64, v66);
      v18 += 96;
      *((_QWORD *)&v36 + 1) = v18;
    }
    std::wstring::~wstring(v66);
    std::wstring::~wstring(v65);
    std::wstring::~wstring(v64);
    v25 = (_QWORD *)*v25;
  }
  vreg::client::construct_vreg_mappings(v44, v3);
  v27 = (char *)operator new(0x68u);
  v38 = v27;
  *(_OWORD *)v27 = 0;
  *((_DWORD *)v27 + 2) = 1;
  *((_DWORD *)v27 + 3) = 1;
  *(_QWORD *)v27 = &std::_Ref_count_obj2<jitv_context>::`vftable';
  *(_QWORD *)v33 = *v39;
  *v39 = 0;
  packageFullNames = (PWSTR)v33;
  std::wstring::wstring(v27 + 16, v3);
  *((_QWORD *)v27 + 6) = 0;
  *((_QWORD *)v27 + 7) = 0;
  *((_QWORD *)v27 + 8) = 0;
  *((_QWORD *)v27 + 9) = 0;
  *((_QWORD *)v27 + 10) = 0;
  *((_QWORD *)v27 + 11) = 0;
  *((_QWORD *)v27 + 12) = *(_QWORD *)v33;
  v28 = v40;
  *v40 = v27 + 16;
  v28[1] = v27;
  v29 = *(void (__fastcall ****)(_QWORD, __int64))count;
  if ( v27 + 48 != (char *)&v36 )
    std::vector<vfs_mapping>::_Assign_counted_range<vfs_mapping *>(
      v27 + 48,
      v36,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)&v18[-v36] >> 5));
  v30 = (_QWORD *)(*v28 + 56LL);
  if ( v30 != v44 )
    std::vector<vreg_mapping>::_Assign_counted_range<vreg_mapping *>(
      v30,
      v44[0],
      0x8E38E38E38E38E39uLL * ((__int64)(v44[1] - v44[0]) >> 3));
  std::vector<vreg_mapping>::~vector<vreg_mapping>(v44);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v59);
  std::list<std::wstring>::~list<std::wstring>(&v58);
  std::vector<vfs_mapping>::~vector<vfs_mapping>(&v36);
  std::vector<DesktopAppXVFS::Mapping>::_Tidy(&v45);
  if ( v29 )
    (**v29)(v29, 1);
  std::vector<PackageFamilyCompatValues::AppDataRedirectionExclusion::ExclusionInfo>::~vector<PackageFamilyCompatValues::AppDataRedirectionExclusion::ExclusionInfo>(&v47);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v49);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v51);
  std::vector<DesktopAppXVFS::Mapping>::_Tidy(&v53);
  std::wstring::~wstring(v69);
  std::wstring::~wstring(&v61);
  if ( *v39 )
    close_jitv_silo(*v39);
  return v28;
}

```

## disassembly

```asm
0x180085844  mov     [rsp-8+arg_18], rbx
0x180085849  push    rbp
0x18008584a  push    rsi
0x18008584b  push    rdi
0x18008584c  push    r12
0x18008584e  push    r13
0x180085850  push    r14
0x180085852  push    r15
0x180085854  lea     rbp, [rsp-2D0h]
0x18008585c  sub     rsp, 3D0h
0x180085863  mov     rax, cs:__security_cookie
0x18008586a  xor     rax, rsp
0x18008586d  mov     [rbp+300h+var_40], rax
0x180085874  mov     r13, r8
0x180085877  mov     [rbp+300h+var_358], r8
0x18008587b  mov     [rbp+300h+var_350], rdx
0x18008587f  mov     [rbp+300h+var_348], rcx
0x180085883  mov     [rbp+300h+var_290], rcx
0x180085887  mov     [rbp+300h+var_288], rdx
0x18008588b  xor     r14d, r14d
0x18008588e  mov     [rsp+400h+var_390], r14d
0x180085893  mov     rdx, [r8+10h]
0x180085897  cmp     qword ptr [r8+18h], 7
0x18008589c  jbe     short loc_1800858A1
0x18008589e  mov     r8, [r8]
0x1800858a1  mov     r12d, 2
0x1800858a7  cmp     rdx, 26h ; '&'
0x1800858ab  jnz     short loc_1800858F2
0x1800858ad  lea     rcx, aMicrosoftOffic; "Microsoft.Office.Desktop_8wekyb3d8bbwe"
0x1800858b4  sub     r8, rcx
0x1800858b7  movzx   eax, word ptr [rcx+r8]
0x1800858bc  cmp     ax, [rcx]
0x1800858bf  jnz     short loc_1800858F2
0x1800858c1  add     rcx, r12
0x1800858c4  sub     rdx, 1
0x1800858c8  jnz     short loc_1800858B7
0x1800858ca  xorps   xmm0, xmm0
0x1800858cd  movups  [rbp+300h+var_220], xmm0
0x1800858d4  mov     [rbp+300h+var_210], r14
0x1800858db  mov     [rbp+300h+var_208], r14
0x1800858e2  lea     r8d, [rdx+53h]
0x1800858e6  lea     rdx, aMicrosoftOffic_0; "Microsoft.Office.Desktop_8wekyb3d8bbwe_"...
0x1800858ed  jmp     loc_1800859AA
0x1800858f2  mov     [rbp+300h+packageFullNames], r14
0x1800858f6  mov     [rbp+300h+count], 1
0x1800858fd  xor     edx, edx; Val
0x1800858ff  mov     r8d, 100h; Size
0x180085905  lea     rcx, [rbp+300h+var_140]; void *
0x18008590c  call    memset_0
0x180085911  mov     [rsp+400h+var_388], 80h
0x180085919  mov     rcx, r13
0x18008591c  cmp     qword ptr [r13+18h], 7
0x180085921  jbe     short loc_180085927
0x180085923  mov     rcx, [r13+0]; packageFamilyName
0x180085927  mov     [rsp+400h+packageProperties], r14; packageProperties
0x18008592c  lea     rax, [rbp+300h+var_140]
0x180085933  mov     [rsp+400h+buffer], rax; buffer
0x180085938  lea     rax, [rsp+400h+var_388]
0x18008593d  mov     [rsp+400h+bufferLength], rax; int
0x180085942  lea     r9, [rbp+300h+packageFullNames]; packageFullNames
0x180085946  lea     r8, [rbp+300h+count]; count
0x18008594a  mov     edx, 10h; packageFilters
0x18008594f  call    cs:__imp_FindPackagesByPackageFamily
0x180085956  nop     dword ptr [rax+rax+00h]
0x18008595b  mov     rcx, [rbp+308h]; this
0x180085962  test    eax, eax
0x180085964  jnz     loc_180085F66
0x18008596a  cmp     [rbp+300h+count], 1
0x18008596e  setb    al
0x180085971  mov     rcx, [rbp+308h]; this
0x180085978  test    al, al
0x18008597a  jnz     loc_180085F7B
0x180085980  xorps   xmm0, xmm0
0x180085983  movups  [rbp+300h+var_220], xmm0
0x18008598a  mov     [rbp+300h+var_210], r14
0x180085991  mov     [rbp+300h+var_208], r14
0x180085998  mov     rdx, [rbp+300h+packageFullNames]
0x18008599c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800859a0  inc     r8
0x1800859a3  cmp     [rdx+r8*2], r14w
0x1800859a8  jnz     short loc_1800859A0
0x1800859aa  lea     rcx, [rbp+300h+var_220]
0x1800859b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800859b6  mov     [rsp+400h+var_390], r12d
0x1800859bb  lea     rdx, [rbp+300h+var_220]
0x1800859c2  lea     rcx, [rbp+300h+var_160]
0x1800859c9  call    ?get_package_path@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; get_package_path(std::wstring const &)
0x1800859ce  nop
0x1800859cf  xorps   xmm0, xmm0
0x1800859d2  movdqu  [rbp+300h+var_2A8], xmm0
0x1800859d7  mov     [rbp+300h+var_298], r14
0x1800859db  movdqu  [rbp+300h+var_2C0], xmm0
0x1800859e0  mov     [rbp+300h+var_2B0], r14
0x1800859e4  movdqu  [rbp+300h+var_2D8], xmm0
0x1800859e9  mov     [rbp+300h+var_2C8], r14
0x1800859ed  movdqu  [rbp+300h+var_2F0], xmm0
0x1800859f2  mov     [rbp+300h+var_2E0], r14
0x1800859f6  call    cs:__imp_GetCurrentProcessId
0x1800859fd  nop     dword ptr [rax+rax+00h]
0x180085a02  mov     r8d, eax; dwProcessId
0x180085a05  xor     edx, edx; bInheritHandle
0x180085a07  mov     ecx, 20410h; dwDesiredAccess
0x180085a0c  call    cs:__imp_OpenProcess
0x180085a13  nop     dword ptr [rax+rax+00h]
0x180085a18  mov     rbx, rax
0x180085a1b  mov     [rbp+300h+packageFullNames], rax
0x180085a1f  inc     rax
0x180085a22  test    rax, 0FFFFFFFFFFFFFFFEh
0x180085a28  jnz     short loc_180085A3A
0x180085a2a  mov     rcx, [rbp+308h]; this
0x180085a31  test    rbx, rbx
0x180085a34  jz      loc_180085F93
0x180085a3a  mov     qword ptr [rsp+400h+var_388], r14
0x180085a3f  mov     [rsp+400h+var_390], 6
0x180085a47  lea     rcx, [rsp+400h+var_388]
0x180085a4c  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180085a51  mov     rdi, [rbp+308h]
0x180085a58  mov     r8, rax; TokenHandle
0x180085a5b  mov     edx, 20008h; DesiredAccess
0x180085a60  mov     rcx, rbx; ProcessHandle
0x180085a63  call    cs:__imp_OpenProcessToken
0x180085a6a  nop     dword ptr [rax+rax+00h]
0x180085a6f  test    eax, eax
0x180085a71  jz      loc_180085F51
0x180085a77  lea     rax, [rbx-1]
0x180085a7b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180085a7f  ja      short loc_180085A90
0x180085a81  mov     rcx, rbx; hObject
0x180085a84  call    cs:__imp_CloseHandle
0x180085a8b  nop     dword ptr [rax+rax+00h]
0x180085a90  mov     r8, qword ptr [rsp+400h+var_388]
0x180085a95  lea     rdx, [rbp+300h+var_220]
0x180085a9c  lea     rcx, [rbp+300h+count]
0x180085aa0  call    ?MakeHeliumSpecification@helium@@YA?AV?$unique_ptr@VHeliumSpecification@helium@@U?$default_delete@VHeliumSpecification@helium@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAX@Z; helium::MakeHeliumSpecification(std::wstring const &,void *)
0x180085aa5  nop
0x180085aa6  mov     [rsp+400h+var_390], r12d
0x180085aab  mov     rcx, qword ptr [rsp+400h+var_388]; hObject
0x180085ab0  lea     rax, [rcx-1]
0x180085ab4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180085ab8  ja      short loc_180085AC6
0x180085aba  call    cs:__imp_CloseHandle
0x180085ac1  nop     dword ptr [rax+rax+00h]
0x180085ac6  lea     rax, [rbp+300h+var_2F0]
0x180085aca  mov     [rsp+400h+var_3A0], rax
0x180085acf  mov     [rsp+400h+var_3A8], r14b
0x180085ad4  mov     [rsp+400h+var_3B0], r14b
0x180085ad9  mov     [rsp+400h+var_3B8], r14b
0x180085ade  mov     [rsp+400h+var_3C0], 1
0x180085ae3  mov     [rsp+400h+var_3C8], 1
0x180085ae8  lea     rax, [rbp+300h+var_2D8]
0x180085aec  mov     [rsp+400h+packageProperties], rax
0x180085af1  lea     rax, [rbp+300h+var_2C0]
0x180085af5  mov     [rsp+400h+buffer], rax
0x180085afa  lea     rax, [rbp+300h+var_160]
0x180085b01  mov     [rsp+400h+bufferLength], rax
0x180085b06  xor     r9d, r9d
0x180085b09  mov     r8, qword ptr [rbp+300h+count]
0x180085b0d  lea     rdx, [rbp+300h+var_2A8]
0x180085b11  lea     rcx, [rbp+300h+var_308]
0x180085b15  call    ?GenerateVfsMappings@DesktopAppXVFS@@YA?AV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@std@@AEAV23@AEBVHeliumSpecification@helium@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@4_N5555AEBV?$vector@UFileSystemExclusion@WriteVirtualization@@V?$allocator@UFileSystemExclusion@WriteVirtualization@@@std@@@3@@Z; DesktopAppXVFS::GenerateVfsMappings(std::vector<DesktopAppXVFS::Mapping> &,helium::HeliumSpecification const &,void *,std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &,bool,bool,bool,bool,bool,std::vector<WriteVirtualization::FileSystemExclusion> const &)
0x180085b1a  nop
0x180085b1b  xorps   xmm0, xmm0
0x180085b1e  movdqu  [rbp+300h+var_370], xmm0
0x180085b23  mov     [rbp+300h+var_360], r14
0x180085b27  lea     rcx, [rbp+300h+var_280]
0x180085b2e  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180085b33  nop
0x180085b34  mov     rax, [rbp+300h+var_300]
0x180085b38  mov     [rbp+300h+packageFullNames], rax
0x180085b3c  mov     rbx, [rbp+300h+var_308]
0x180085b40  mov     r15, qword ptr [rbp+300h+var_370+8]
0x180085b44  cmp     rbx, rax
0x180085b47  jz      loc_180085C9E
0x180085b4d  add     rbx, 20h ; ' '
0x180085b51  mov     r13, rax
0x180085b54  mov     rdx, rbx
0x180085b57  lea     rcx, [rbp+300h+var_1A0]
0x180085b5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085b63  or      r12d, 8
0x180085b67  mov     [rsp+400h+var_390], r12d
0x180085b6c  mov     rdi, [rbx+20h]
0x180085b70  mov     rsi, [rbx+28h]
0x180085b74  cmp     rdi, rsi
0x180085b77  jz      loc_180085C7D
0x180085b7d  mov     rdx, rdi
0x180085b80  lea     rcx, [rbp+300h+var_180]
0x180085b87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085b8c  or      r12d, 10h
0x180085b90  mov     [rsp+400h+var_390], r12d
0x180085b95  lea     rdx, [rbx-20h]
0x180085b99  lea     rcx, [rbp+300h+var_240]
0x180085ba0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085ba5  lea     r9, [rbp+300h+var_180]
0x180085bac  lea     r8, [rbp+300h+var_1A0]
0x180085bb3  mov     rdx, rax
0x180085bb6  lea     rcx, [rbp+300h+var_200]
0x180085bbd  call    ??0vfs_mapping@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@1@Z; vfs_mapping::vfs_mapping(std::wstring,std::wstring const &,std::wstring const &)
0x180085bc2  nop
0x180085bc3  lea     rcx, [rbp+300h+var_180]; void *
0x180085bca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085bcf  cmp     r15, r14
0x180085bd2  jz      short loc_180085C15
0x180085bd4  mov     qword ptr [rsp+400h+var_388], r15
0x180085bd9  lea     rdx, [rbp+300h+var_200]
0x180085be0  mov     rcx, r15
0x180085be3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085be8  nop
0x180085be9  lea     rcx, [r15+20h]
0x180085bed  lea     rdx, [rbp+300h+var_1E0]
0x180085bf4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085bf9  nop
0x180085bfa  lea     rcx, [r15+40h]
0x180085bfe  lea     rdx, [rbp+300h+var_1C0]
0x180085c05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085c0a  nop
0x180085c0b  add     r15, 60h ; '`'
0x180085c0f  mov     qword ptr [rbp+300h+var_370+8], r15
0x180085c13  jmp     short loc_180085C30
0x180085c15  lea     r8, [rbp+300h+var_200]
0x180085c1c  mov     rdx, r15
0x180085c1f  lea     rcx, [rbp+300h+var_370]
0x180085c23  call    ??$_Emplace_reallocate@AEBVvfs_mapping@@@?$vector@Vvfs_mapping@@V?$allocator@Vvfs_mapping@@@std@@@std@@AEAAPEAVvfs_mapping@@QEAV2@AEBV2@@Z; std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(vfs_mapping * const,vfs_mapping const &)
0x180085c28  mov     r15, qword ptr [rbp+300h+var_370+8]
0x180085c2c  mov     r14, [rbp+300h+var_360]
0x180085c30  lea     r8, [rbp+300h+var_1A0]
0x180085c37  lea     rdx, [rbp+300h+var_340]
0x180085c3b  lea     rcx, [rbp+300h+var_280]
0x180085c42  call    ?insert@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x180085c47  nop
0x180085c48  lea     rcx, [rbp+300h+var_1C0]; void *
0x180085c4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085c54  lea     rcx, [rbp+300h+var_1E0]; void *
0x180085c5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085c60  lea     rcx, [rbp+300h+var_200]; void *
0x180085c67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085c6c  add     rdi, 20h ; ' '
0x180085c70  cmp     rdi, rsi
0x180085c73  jnz     loc_180085B7D
0x180085c79  mov     r13, [rbp+300h+packageFullNames]
0x180085c7d  lea     rcx, [rbp+300h+var_1A0]; void *
0x180085c84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085c89  add     rbx, 78h ; 'x'
0x180085c8d  lea     rax, [rbx-20h]
0x180085c91  cmp     rax, r13
0x180085c94  jnz     loc_180085B54
0x180085c9a  mov     r13, [rbp+300h+var_358]
0x180085c9e  mov     rdi, [rbp+300h+var_278]
0x180085ca5  mov     rbx, [rdi]
0x180085ca8  mov     rsi, [rbp+300h+var_360]
0x180085cac  cmp     rbx, rdi
0x180085caf  jz      loc_180085D7E
0x180085cb5  xorps   xmm0, xmm0
0x180085cb8  movups  [rbp+300h+var_340], xmm0
0x180085cbc  and     [rbp+300h+var_330], 0
0x180085cc1  and     [rbp+300h+var_328], 0
0x180085cc6  xor     r8d, r8d
0x180085cc9  lea     rdx, String1
0x180085cd0  lea     rcx, [rbp+300h+var_340]
0x180085cd4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180085cd9  lea     r9, [rbx+10h]
0x180085cdd  lea     r8, [rbx+10h]
0x180085ce1  lea     rdx, [rbp+300h+var_340]
0x180085ce5  lea     rcx, [rbp+300h+var_200]
0x180085cec  call    ??0vfs_mapping@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@1@Z; vfs_mapping::vfs_mapping(std::wstring,std::wstring const &,std::wstring const &)
0x180085cf1  nop
0x180085cf2  cmp     r15, rsi
0x180085cf5  jz      short loc_180085D37
0x180085cf7  mov     [rbp+300h+var_358], r15
0x180085cfb  lea     rdx, [rbp+300h+var_200]
0x180085d02  mov     rcx, r15
0x180085d05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085d0a  nop
0x180085d0b  lea     rcx, [r15+20h]
0x180085d0f  lea     rdx, [rbp+300h+var_1E0]
0x180085d16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085d1b  nop
0x180085d1c  lea     rcx, [r15+40h]
0x180085d20  lea     rdx, [rbp+300h+var_1C0]
0x180085d27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085d2c  nop
0x180085d2d  add     r15, 60h ; '`'
0x180085d31  mov     qword ptr [rbp+300h+var_370+8], r15
0x180085d35  jmp     short loc_180085D52
0x180085d37  lea     r8, [rbp+300h+var_200]
0x180085d3e  mov     rdx, r15
0x180085d41  lea     rcx, [rbp+300h+var_370]
0x180085d45  call    ??$_Emplace_reallocate@AEBVvfs_mapping@@@?$vector@Vvfs_mapping@@V?$allocator@Vvfs_mapping@@@std@@@std@@AEAAPEAVvfs_mapping@@QEAV2@AEBV2@@Z; std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(vfs_mapping * const,vfs_mapping const &)
0x180085d4a  mov     r15, qword ptr [rbp+300h+var_370+8]
0x180085d4e  mov     rsi, [rbp+300h+var_360]
0x180085d52  lea     rcx, [rbp+300h+var_1C0]; void *
0x180085d59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085d5e  lea     rcx, [rbp+300h+var_1E0]; void *
0x180085d65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085d6a  lea     rcx, [rbp+300h+var_200]; void *
0x180085d71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085d76  mov     rbx, [rbx]
0x180085d79  jmp     loc_180085CAC
0x180085d7e  mov     rdx, r13
0x180085d81  lea     rcx, [rbp+300h+var_320]
0x180085d85  call    ?construct_vreg_mappings@client@vreg@@YA?AV?$vector@Uvreg_mapping@@V?$allocator@Uvreg_mapping@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAX@Z; vreg::client::construct_vreg_mappings(std::wstring const &,void *)
  ... truncated ...
```
