# make_jitv_context(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,void (*)(unsigned __int64),&close_jitv_silo(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180086e80`
- end: `0x1800875bd`
- name: `?make_jitv_context@@YA?AV?$shared_ptr@Vjitv_context@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AX_K@Z$1?close_jitv_silo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `1853`
- prototype: `_QWORD *__fastcall(_QWORD *, UINT32 *, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800869b0`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ae88`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x180014e74`
- `0x180017aa4`
- `0x1800210fc`
- `0x18002bab4`
- `0x18002cecc`
- `0x180030254`
- `0x180036010`
- `0x1800360e0`
- `0x180038214`
- `0x180038de8`
- `0x180038e70`
- `0x180038f88`
- `0x180052d0c`
- `0x18005f7e4`
- `0x180082be0`
- `0x180085f80`
- `0x180086374`
- `0x1800865b4`
- `0x18008667c`
- `0x180086cb4`
- `0x180086e80`
- `0x180088efc`
- `0x18008c1c8`
- `0x18008c37c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180087095`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180087095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087028`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800870b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800870ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800870b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800870ee`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008703e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008703e`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180086f7d`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180086f7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall make_jitv_context(_QWORD *a1, UINT32 *a2, __int64 a3)
{
  _QWORD *v4; // r13
  __int64 v5; // r8
  const wchar_t *v6; // rcx
  __int64 v7; // r8
  PWSTR v8; // rdx
  const WCHAR *v9; // rcx
  unsigned int PackagesByPackageFamily; // eax
  int v11; // esi
  DWORD CurrentProcessId; // eax
  WCHAR *v13; // rbx
  const char *v14; // r9
  void **v15; // rax
  const char *v16; // r9
  PWSTR v17; // r15
  __int64 v18; // rbx
  __int64 v19; // r13
  __int64 v20; // r12
  __int64 v21; // r15
  __int64 v22; // rax
  __int64 v23; // rdi
  _QWORD *v24; // r12
  _QWORD *i; // rbx
  __int64 v26; // rdi
  _DWORD *v27; // rdi
  unsigned __int64 *v28; // r12
  _QWORD *v29; // rcx
  unsigned int bufferLength; // [rsp+20h] [rbp-E0h]
  UINT32 v32[2]; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h]
  PWSTR packageFullNames; // [rsp+80h] [rbp-80h] BYREF
  UINT32 count; // [rsp+88h] [rbp-78h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-60h]
  _QWORD *v38; // [rsp+A8h] [rbp-58h]
  UINT32 *v39; // [rsp+B0h] [rbp-50h]
  __int128 v40; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  _QWORD v43[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v44; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  __int128 v46; // [rsp+108h] [rbp+8h] BYREF
  __int64 v47; // [rsp+118h] [rbp+18h]
  __int128 v48; // [rsp+120h] [rbp+20h] BYREF
  __int64 v49; // [rsp+130h] [rbp+30h]
  __int128 v50; // [rsp+138h] [rbp+38h] BYREF
  __int64 v51; // [rsp+148h] [rbp+48h]
  __int128 v52; // [rsp+150h] [rbp+50h] BYREF
  __int64 v53; // [rsp+160h] [rbp+60h]
  _QWORD *v54; // [rsp+168h] [rbp+68h]
  UINT32 *v55; // [rsp+170h] [rbp+70h]
  char v56[8]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD *v57; // [rsp+188h] [rbp+88h] BYREF
  char v58[40]; // [rsp+198h] [rbp+98h] BYREF
  char v59[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v60; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v61; // [rsp+1F0h] [rbp+F0h]
  __int64 v62; // [rsp+1F8h] [rbp+F8h]
  _BYTE v63[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v64[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v65[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v66[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v67[32]; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v68[4]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR buffer[128]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v39 = a2;
  v4 = a1;
  v38 = a1;
  v54 = a1;
  v55 = a2;
  v33 = 0;
  v5 = *(_QWORD *)(a3 + 16);
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v6 = (const wchar_t *)a3;
  else
    v6 = *(const wchar_t **)a3;
  if ( v5 == 38 && !wmemcmp(v6, L"Microsoft.Office.Desktop_8wekyb3d8bbwe", 0x26u) )
  {
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v7 = 83;
    v8 = (PWSTR)L"Microsoft.Office.Desktop_8wekyb3d8bbwe_LOOSE_FILE_REGISTERED_C2RX_PACKAGE_FULL_NAME";
  }
  else
  {
    packageFullNames = 0;
    count = 1;
    memset_0(buffer, 0, sizeof(buffer));
    v32[0] = 128;
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v9 = (const WCHAR *)a3;
    else
      v9 = *(const WCHAR **)a3;
    PackagesByPackageFamily = FindPackagesByPackageFamily(v9, 0x10u, &count, &packageFullNames, v32, buffer, 0);
    if ( PackagesByPackageFamily )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
        (const char *)PackagesByPackageFamily,
        bufferLength);
    if ( !count )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
        (const char *)0x80070554LL,
        bufferLength);
    v8 = packageFullNames;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v7 = -1;
    do
      ++v7;
    while ( packageFullNames[v7] );
  }
  std::wstring::_Construct<1,unsigned short const *>(&v60, v8, v7);
  v11 = 2;
  v33 = 2;
  get_package_path(v68, &v60);
  v52 = 0;
  v53 = 0;
  v50 = 0;
  v51 = 0;
  v48 = 0;
  v49 = 0;
  v46 = 0;
  v47 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v13 = (WCHAR *)OpenProcess(0x20410u, 0, CurrentProcessId);
  packageFullNames = v13;
  if ( (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && !v13 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
      v14);
  *(_QWORD *)v32 = 0;
  v33 = 6;
  v15 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(v32);
  if ( !OpenProcessToken(v13, 0x20008u, v15) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\make_jitv_context.cpp",
      v16);
  if ( (unsigned __int64)v13 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v13);
  helium::MakeHeliumSpecification((char *)&packageFullNames, (const unsigned __int16 *)&v60, *(__int64 *)v32, 0);
  v33 = 2;
  if ( (unsigned __int64)(*(_QWORD *)v32 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)v32);
  v17 = packageFullNames;
  DesktopAppXVFS::GenerateVfsMappings(
    &v44,
    (__int64 *)&v52,
    (__int64)packageFullNames,
    0,
    v68,
    &v50,
    &v48,
    1,
    1,
    0,
    0,
    0,
    (__int64 *)&v46);
  v36 = 0;
  v37 = 0;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v56);
  v18 = v44;
  if ( v44 != v45 )
  {
    v19 = v45;
    do
    {
      std::wstring::wstring(v66, v18 + 32);
      v11 |= 8u;
      v33 = v11;
      v20 = *(_QWORD *)(v18 + 64);
      if ( v20 != *(_QWORD *)(v18 + 72) )
      {
        v21 = *(_QWORD *)(v18 + 72);
        do
        {
          std::wstring::wstring(v67, v20);
          v11 |= 0x10u;
          v33 = v11;
          v22 = std::wstring::wstring(v59, v18);
          vfs_mapping::vfs_mapping(v63, v22, v66, v67);
          std::wstring::~wstring(v67);
          v23 = *((_QWORD *)&v36 + 1);
          if ( *((_QWORD *)&v36 + 1) == v37 )
          {
            std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(&v36, *((_QWORD *)&v36 + 1), v63);
          }
          else
          {
            *(_QWORD *)v32 = *((_QWORD *)&v36 + 1);
            std::wstring::wstring(*((_QWORD *)&v36 + 1), v63);
            std::wstring::wstring(v23 + 32, v64);
            std::wstring::wstring(v23 + 64, v65);
            *((_QWORD *)&v36 + 1) += 96LL;
          }
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(
            v56,
            &v40,
            v66);
          std::wstring::~wstring(v65);
          std::wstring::~wstring(v64);
          std::wstring::~wstring(v63);
          v20 += 32;
        }
        while ( v20 != v21 );
      }
      std::wstring::~wstring(v66);
      v18 += 120;
    }
    while ( v18 != v19 );
    v17 = packageFullNames;
    v4 = v38;
  }
  v24 = v57;
  for ( i = (_QWORD *)*v57; i != v24; i = (_QWORD *)*i )
  {
    v40 = 0;
    v41 = 0;
    v42 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v40, &String1, 0);
    vfs_mapping::vfs_mapping(v63, &v40, i + 2, i + 2);
    v26 = *((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) == v37 )
    {
      std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(&v36, *((_QWORD *)&v36 + 1), v63);
    }
    else
    {
      v38 = (_QWORD *)*((_QWORD *)&v36 + 1);
      std::wstring::wstring(*((_QWORD *)&v36 + 1), v63);
      std::wstring::wstring(v26 + 32, v64);
      std::wstring::wstring(v26 + 64, v65);
      *((_QWORD *)&v36 + 1) += 96LL;
    }
    std::wstring::~wstring(v65);
    std::wstring::~wstring(v64);
    std::wstring::~wstring(v63);
  }
  vreg::client::construct_vreg_mappings(v43, a3);
  v27 = operator new(0x68u);
  v38 = v27;
  *(_OWORD *)v27 = 0;
  v27[2] = 1;
  v27[3] = 1;
  *(_QWORD *)v27 = &std::_Ref_count_obj2<jitv_context>::`vftable';
  v28 = (unsigned __int64 *)v39;
  *(_QWORD *)v32 = *(_QWORD *)v39;
  *(_QWORD *)v39 = 0;
  v39 = v32;
  std::wstring::wstring(v27 + 4, a3);
  *((_QWORD *)v27 + 6) = 0;
  *((_QWORD *)v27 + 7) = 0;
  *((_QWORD *)v27 + 8) = 0;
  *((_QWORD *)v27 + 9) = 0;
  *((_QWORD *)v27 + 10) = 0;
  *((_QWORD *)v27 + 11) = 0;
  *((_QWORD *)v27 + 12) = *(_QWORD *)v32;
  *v4 = v27 + 4;
  v4[1] = v27;
  v33 = v11 | 0x21;
  if ( v27 + 12 != (_DWORD *)&v36 )
    std::vector<vfs_mapping>::_Assign_counted_range<vfs_mapping *>(
      v27 + 12,
      v36,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v36 + 1) - v36) >> 5));
  v29 = (_QWORD *)(*v4 + 56LL);
  if ( v29 != v43 )
    std::vector<vreg_mapping>::_Assign_counted_range<vreg_mapping *>(
      v29,
      v43[0],
      0x8E38E38E38E38E39uLL * ((__int64)(v43[1] - v43[0]) >> 3));
  std::vector<vreg_mapping>::~vector<vreg_mapping>(v43);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v58);
  std::list<std::wstring>::~list<std::wstring>(&v57);
  std::vector<vfs_mapping>::~vector<vfs_mapping>(&v36);
  std::vector<DesktopAppXVFS::Mapping>::_Tidy(&v44);
  if ( v17 )
    (**(void (__fastcall ***)(PWSTR, __int64))v17)(v17, 1);
  std::vector<PackageFamilyCompatValues::AppDataRedirectionExclusion::ExclusionInfo>::~vector<PackageFamilyCompatValues::AppDataRedirectionExclusion::ExclusionInfo>(&v46);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v48);
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v50);
  std::vector<DesktopAppXVFS::Mapping>::_Tidy(&v52);
  std::wstring::~wstring(v68);
  std::wstring::~wstring(&v60);
  if ( *v28 )
    close_jitv_silo(*v28);
  return v4;
}

```

## disassembly

```asm
0x180086e80  mov     [rsp-8+arg_18], rbx
0x180086e85  push    rbp
0x180086e86  push    rsi
0x180086e87  push    rdi
0x180086e88  push    r12
0x180086e8a  push    r13
0x180086e8c  push    r14
0x180086e8e  push    r15
0x180086e90  lea     rbp, [rsp-2D0h]
0x180086e98  sub     rsp, 3D0h
0x180086e9f  mov     rax, cs:__security_cookie
0x180086ea6  xor     rax, rsp
0x180086ea9  mov     [rbp+300h+var_40], rax
0x180086eb0  mov     r14, r8
0x180086eb3  mov     [rbp+300h+var_350], rdx
0x180086eb7  mov     r13, rcx
0x180086eba  mov     [rbp+300h+var_358], rcx
0x180086ebe  mov     [rbp+300h+var_298], rcx
0x180086ec2  mov     [rbp+300h+var_290], rdx
0x180086ec6  xor     r12d, r12d
0x180086ec9  mov     [rsp+400h+var_388], r12d
0x180086ece  mov     r8, [r8+10h]; N
0x180086ed2  cmp     qword ptr [r14+18h], 7
0x180086ed7  jbe     short loc_180086EDE
0x180086ed9  mov     rcx, [r14]
0x180086edc  jmp     short loc_180086EE1
0x180086ede  mov     rcx, r14; S1
0x180086ee1  cmp     r8, 26h ; '&'
0x180086ee5  jnz     short loc_180086F1F
0x180086ee7  lea     rdx, aMicrosoftOffic; "Microsoft.Office.Desktop_8wekyb3d8bbwe"
0x180086eee  call    wmemcmp
0x180086ef3  test    eax, eax
0x180086ef5  jnz     short loc_180086F1F
0x180086ef7  xorps   xmm0, xmm0
0x180086efa  movups  [rbp+300h+var_220], xmm0
0x180086f01  mov     [rbp+300h+var_210], r12
0x180086f08  mov     [rbp+300h+var_208], r12
0x180086f0f  lea     r8d, [rax+53h]
0x180086f13  lea     rdx, aMicrosoftOffic_0; "Microsoft.Office.Desktop_8wekyb3d8bbwe_"...
0x180086f1a  jmp     loc_180086FD8
0x180086f1f  mov     [rbp+300h+packageFullNames], r12
0x180086f23  mov     [rbp+300h+count], 1
0x180086f2a  xor     edx, edx; Val
0x180086f2c  mov     r8d, 100h; Size
0x180086f32  lea     rcx, [rbp+300h+var_140]; void *
0x180086f39  call    memset_0
0x180086f3e  mov     [rsp+400h+var_390], 80h
0x180086f46  cmp     qword ptr [r14+18h], 7
0x180086f4b  jbe     short loc_180086F52
0x180086f4d  mov     rcx, [r14]
0x180086f50  jmp     short loc_180086F55
0x180086f52  mov     rcx, r14; packageFamilyName
0x180086f55  mov     [rsp+400h+packageProperties], r12; packageProperties
0x180086f5a  lea     rax, [rbp+300h+var_140]
0x180086f61  mov     [rsp+400h+buffer], rax; buffer
0x180086f66  lea     rax, [rsp+400h+var_390]
0x180086f6b  mov     [rsp+400h+bufferLength], rax; int
0x180086f70  lea     r9, [rbp+300h+packageFullNames]; packageFullNames
0x180086f74  lea     r8, [rbp+300h+count]; count
0x180086f78  mov     edx, 10h; packageFilters
0x180086f7d  call    cs:__imp_FindPackagesByPackageFamily
0x180086f84  nop     dword ptr [rax+rax+00h]
0x180086f89  mov     rcx, [rbp+308h]; this
0x180086f90  test    eax, eax
0x180086f92  jnz     loc_18008757E
0x180086f98  cmp     [rbp+300h+count], 1
0x180086f9c  setb    al
0x180086f9f  mov     rcx, [rbp+308h]; this
0x180086fa6  test    al, al
0x180086fa8  jnz     loc_180087593
0x180086fae  mov     rdx, [rbp+300h+packageFullNames]
0x180086fb2  xorps   xmm0, xmm0
0x180086fb5  movups  [rbp+300h+var_220], xmm0
0x180086fbc  mov     [rbp+300h+var_210], r12
0x180086fc3  mov     [rbp+300h+var_208], r12
0x180086fca  or      r8, 0FFFFFFFFFFFFFFFFh
0x180086fce  inc     r8
0x180086fd1  cmp     [rdx+r8*2], r12w
0x180086fd6  jnz     short loc_180086FCE
0x180086fd8  lea     rcx, [rbp+300h+var_220]
0x180086fdf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180086fe4  mov     esi, 2
0x180086fe9  mov     [rsp+400h+var_388], esi
0x180086fed  lea     rdx, [rbp+300h+var_220]
0x180086ff4  lea     rcx, [rbp+300h+var_160]
0x180086ffb  call    ?get_package_path@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; get_package_path(std::wstring const &)
0x180087000  nop
0x180087001  xorps   xmm0, xmm0
0x180087004  movdqu  [rbp+300h+var_2B0], xmm0
0x180087009  mov     [rbp+300h+var_2A0], r12
0x18008700d  movdqu  [rbp+300h+var_2C8], xmm0
0x180087012  mov     [rbp+300h+var_2B8], r12
0x180087016  movdqu  [rbp+300h+var_2E0], xmm0
0x18008701b  mov     [rbp+300h+var_2D0], r12
0x18008701f  movdqu  [rbp+300h+var_2F8], xmm0
0x180087024  mov     [rbp+300h+var_2E8], r12
0x180087028  call    cs:__imp_GetCurrentProcessId
0x18008702f  nop     dword ptr [rax+rax+00h]
0x180087034  mov     r8d, eax; dwProcessId
0x180087037  xor     edx, edx; bInheritHandle
0x180087039  mov     ecx, 20410h; dwDesiredAccess
0x18008703e  call    cs:__imp_OpenProcess
0x180087045  nop     dword ptr [rax+rax+00h]
0x18008704a  mov     rbx, rax
0x18008704d  mov     [rbp+300h+packageFullNames], rax
0x180087051  inc     rax
0x180087054  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008705a  jnz     short loc_18008706C
0x18008705c  mov     rcx, [rbp+308h]; this
0x180087063  test    rbx, rbx
0x180087066  jz      loc_1800875AB
0x18008706c  mov     qword ptr [rsp+400h+var_390], r12
0x180087071  mov     [rsp+400h+var_388], 6
0x180087079  lea     rcx, [rsp+400h+var_390]
0x18008707e  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180087083  mov     rdi, [rbp+308h]
0x18008708a  mov     r8, rax; TokenHandle
0x18008708d  mov     edx, 20008h; DesiredAccess
0x180087092  mov     rcx, rbx; ProcessHandle
0x180087095  call    cs:__imp_OpenProcessToken
0x18008709c  nop     dword ptr [rax+rax+00h]
0x1800870a1  test    eax, eax
0x1800870a3  jz      loc_180087569
0x1800870a9  lea     rax, [rbx-1]
0x1800870ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800870b1  ja      short loc_1800870C2
0x1800870b3  mov     rcx, rbx; hObject
0x1800870b6  call    cs:__imp_CloseHandle
0x1800870bd  nop     dword ptr [rax+rax+00h]
0x1800870c2  xor     r9d, r9d
0x1800870c5  mov     r8, qword ptr [rsp+400h+var_390]
0x1800870ca  lea     rdx, [rbp+300h+var_220]
0x1800870d1  lea     rcx, [rbp+300h+packageFullNames]
0x1800870d5  call    ?MakeHeliumSpecification@helium@@YA?AV?$unique_ptr@VHeliumSpecification@helium@@U?$default_delete@VHeliumSpecification@helium@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAX_N@Z; helium::MakeHeliumSpecification(std::wstring const &,void *,bool)
0x1800870da  nop
0x1800870db  mov     [rsp+400h+var_388], esi
0x1800870df  mov     rcx, qword ptr [rsp+400h+var_390]; hObject
0x1800870e4  lea     rax, [rcx-1]
0x1800870e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800870ec  ja      short loc_1800870FA
0x1800870ee  call    cs:__imp_CloseHandle
0x1800870f5  nop     dword ptr [rax+rax+00h]
0x1800870fa  lea     rax, [rbp+300h+var_2F8]
0x1800870fe  mov     [rsp+400h+var_3A0], rax
0x180087103  mov     [rsp+400h+var_3A8], r12b
0x180087108  mov     [rsp+400h+var_3B0], r12b
0x18008710d  mov     [rsp+400h+var_3B8], r12b
0x180087112  mov     [rsp+400h+var_3C0], 1
0x180087117  mov     [rsp+400h+var_3C8], 1
0x18008711c  lea     rax, [rbp+300h+var_2E0]
0x180087120  mov     [rsp+400h+packageProperties], rax
0x180087125  lea     rax, [rbp+300h+var_2C8]
0x180087129  mov     [rsp+400h+buffer], rax
0x18008712e  lea     rax, [rbp+300h+var_160]
0x180087135  mov     [rsp+400h+bufferLength], rax
0x18008713a  xor     r9d, r9d
0x18008713d  mov     r15, [rbp+300h+packageFullNames]
0x180087141  mov     r8, r15
0x180087144  lea     rdx, [rbp+300h+var_2B0]
0x180087148  lea     rcx, [rbp+300h+var_310]
0x18008714c  call    ?GenerateVfsMappings@DesktopAppXVFS@@YA?AV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@std@@AEAV23@AEBVHeliumSpecification@helium@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@4_N5555AEBV?$vector@UFileSystemExclusion@WriteVirtualization@@V?$allocator@UFileSystemExclusion@WriteVirtualization@@@std@@@3@@Z; DesktopAppXVFS::GenerateVfsMappings(std::vector<DesktopAppXVFS::Mapping> &,helium::HeliumSpecification const &,void *,std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &,bool,bool,bool,bool,bool,std::vector<WriteVirtualization::FileSystemExclusion> const &)
0x180087151  nop
0x180087152  xorps   xmm0, xmm0
0x180087155  movdqu  [rbp+300h+var_370], xmm0
0x18008715a  mov     [rbp+300h+var_360], r12
0x18008715e  lea     rcx, [rbp+300h+var_280]
0x180087165  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18008716a  nop
0x18008716b  mov     rbx, [rbp+300h+var_310]
0x18008716f  mov     rax, [rbp+300h+var_308]
0x180087173  cmp     rbx, rax
0x180087176  jz      loc_1800872BE
0x18008717c  mov     r13, rax
0x18008717f  lea     rdx, [rbx+20h]
0x180087183  lea     rcx, [rbp+300h+var_1A0]
0x18008718a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008718f  or      esi, 8
0x180087192  mov     [rsp+400h+var_388], esi
0x180087196  mov     r12, [rbx+40h]
0x18008719a  mov     rax, [rbx+48h]
0x18008719e  cmp     r12, rax
0x1800871a1  jz      loc_18008729D
0x1800871a7  mov     r15, rax
0x1800871aa  mov     rdx, r12
0x1800871ad  lea     rcx, [rbp+300h+var_180]
0x1800871b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800871b9  or      esi, 10h
0x1800871bc  mov     [rsp+400h+var_388], esi
0x1800871c0  mov     rdx, rbx
0x1800871c3  lea     rcx, [rbp+300h+var_240]
0x1800871ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800871cf  lea     r9, [rbp+300h+var_180]
0x1800871d6  lea     r8, [rbp+300h+var_1A0]
0x1800871dd  mov     rdx, rax
0x1800871e0  lea     rcx, [rbp+300h+var_200]
0x1800871e7  call    ??0vfs_mapping@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@1@Z; vfs_mapping::vfs_mapping(std::wstring,std::wstring const &,std::wstring const &)
0x1800871ec  nop
0x1800871ed  lea     rcx, [rbp+300h+var_180]; void *
0x1800871f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800871f9  mov     rdi, qword ptr [rbp+300h+var_370+8]
0x1800871fd  cmp     rdi, [rbp+300h+var_360]
0x180087201  jz      short loc_180087241
0x180087203  mov     qword ptr [rsp+400h+var_390], rdi
0x180087208  lea     rdx, [rbp+300h+var_200]
0x18008720f  mov     rcx, rdi
0x180087212  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087217  nop
0x180087218  lea     rcx, [rdi+20h]
0x18008721c  lea     rdx, [rbp+300h+var_1E0]
0x180087223  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087228  nop
0x180087229  lea     rcx, [rdi+40h]
0x18008722d  lea     rdx, [rbp+300h+var_1C0]
0x180087234  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087239  nop
0x18008723a  add     qword ptr [rbp+300h+var_370+8], 60h ; '`'
0x18008723f  jmp     short loc_180087254
0x180087241  lea     r8, [rbp+300h+var_200]
0x180087248  mov     rdx, rdi
0x18008724b  lea     rcx, [rbp+300h+var_370]
0x18008724f  call    ??$_Emplace_reallocate@AEBVvfs_mapping@@@?$vector@Vvfs_mapping@@V?$allocator@Vvfs_mapping@@@std@@@std@@AEAAPEAVvfs_mapping@@QEAV2@AEBV2@@Z; std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(vfs_mapping * const,vfs_mapping const &)
0x180087254  lea     r8, [rbp+300h+var_1A0]
0x18008725b  lea     rdx, [rbp+300h+var_348]
0x18008725f  lea     rcx, [rbp+300h+var_280]
0x180087266  call    ?insert@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x18008726b  nop
0x18008726c  lea     rcx, [rbp+300h+var_1C0]; void *
0x180087273  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087278  lea     rcx, [rbp+300h+var_1E0]; void *
0x18008727f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087284  lea     rcx, [rbp+300h+var_200]; void *
0x18008728b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087290  add     r12, 20h ; ' '
0x180087294  cmp     r12, r15
0x180087297  jnz     loc_1800871AA
0x18008729d  lea     rcx, [rbp+300h+var_1A0]; void *
0x1800872a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800872a9  add     rbx, 78h ; 'x'
0x1800872ad  cmp     rbx, r13
0x1800872b0  jnz     loc_18008717F
0x1800872b6  mov     r15, [rbp+300h+packageFullNames]
0x1800872ba  mov     r13, [rbp+300h+var_358]
0x1800872be  mov     r12, [rbp+300h+var_278]
0x1800872c5  mov     rbx, [r12]
0x1800872c9  cmp     rbx, r12
0x1800872cc  jz      loc_18008739C
0x1800872d2  xorps   xmm0, xmm0
0x1800872d5  movups  [rbp+300h+var_348], xmm0
0x1800872d9  mov     [rbp+300h+var_338], 0
0x1800872e1  mov     [rbp+300h+var_330], 0
0x1800872e9  xor     r8d, r8d
0x1800872ec  lea     rdx, String1
0x1800872f3  lea     rcx, [rbp+300h+var_348]
0x1800872f7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800872fc  lea     r9, [rbx+10h]
0x180087300  lea     r8, [rbx+10h]
0x180087304  lea     rdx, [rbp+300h+var_348]
0x180087308  lea     rcx, [rbp+300h+var_200]
0x18008730f  call    ??0vfs_mapping@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@1@Z; vfs_mapping::vfs_mapping(std::wstring,std::wstring const &,std::wstring const &)
0x180087314  nop
0x180087315  mov     rdi, qword ptr [rbp+300h+var_370+8]
0x180087319  cmp     rdi, [rbp+300h+var_360]
0x18008731d  jz      short loc_18008735C
0x18008731f  mov     [rbp+300h+var_358], rdi
0x180087323  lea     rdx, [rbp+300h+var_200]
0x18008732a  mov     rcx, rdi
0x18008732d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087332  nop
0x180087333  lea     rcx, [rdi+20h]
0x180087337  lea     rdx, [rbp+300h+var_1E0]
0x18008733e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087343  nop
0x180087344  lea     rcx, [rdi+40h]
0x180087348  lea     rdx, [rbp+300h+var_1C0]
0x18008734f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087354  nop
0x180087355  add     qword ptr [rbp+300h+var_370+8], 60h ; '`'
0x18008735a  jmp     short loc_180087370
0x18008735c  lea     r8, [rbp+300h+var_200]
0x180087363  mov     rdx, rdi
0x180087366  lea     rcx, [rbp+300h+var_370]
0x18008736a  call    ??$_Emplace_reallocate@AEBVvfs_mapping@@@?$vector@Vvfs_mapping@@V?$allocator@Vvfs_mapping@@@std@@@std@@AEAAPEAVvfs_mapping@@QEAV2@AEBV2@@Z; std::vector<vfs_mapping>::_Emplace_reallocate<vfs_mapping const &>(vfs_mapping * const,vfs_mapping const &)
0x18008736f  nop
0x180087370  lea     rcx, [rbp+300h+var_1C0]; void *
0x180087377  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008737c  lea     rcx, [rbp+300h+var_1E0]; void *
0x180087383  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087388  lea     rcx, [rbp+300h+var_200]; void *
0x18008738f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180087394  mov     rbx, [rbx]
0x180087397  jmp     loc_1800872C9
0x18008739c  mov     rdx, r14
0x18008739f  lea     rcx, [rbp+300h+var_328]
0x1800873a3  call    ?construct_vreg_mappings@client@vreg@@YA?AV?$vector@Uvreg_mapping@@V?$allocator@Uvreg_mapping@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAX@Z; vreg::client::construct_vreg_mappings(std::wstring const &,void *)
0x1800873a8  nop
0x1800873a9  mov     ecx, 68h ; 'h'; Size
0x1800873ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800873b3  mov     rdi, rax
0x1800873b6  mov     [rbp+300h+var_358], rax
0x1800873ba  xorps   xmm0, xmm0
  ... truncated ...
```
