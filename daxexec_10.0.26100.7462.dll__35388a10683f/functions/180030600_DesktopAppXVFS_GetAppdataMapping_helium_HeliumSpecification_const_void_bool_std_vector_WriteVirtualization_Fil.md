# DesktopAppXVFS::GetAppdataMapping(helium::HeliumSpecification const &,void *,bool,std::vector<WriteVirtualization::FileSystemExclusion,std::allocator<WriteVirtualization::FileSystemExclusion>> const &)

- ea: `0x180030600`
- end: `0x180030fb3`
- name: `?GetAppdataMapping@DesktopAppXVFS@@YA?AUMapping@1@AEBVHeliumSpecification@helium@@PEAX_NAEBV?$vector@UFileSystemExclusion@WriteVirtualization@@V?$allocator@UFileSystemExclusion@WriteVirtualization@@@std@@@std@@@Z`
- size: `2483`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f468`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x1800149a4`
- `0x18002031c`
- `0x180025620`
- `0x180025d4c`
- `0x18002685c`
- `0x1800279fc`
- `0x18002ac88`
- `0x18002b240`
- `0x18002b510`
- `0x18002b8e0`
- `0x18002ca40`
- `0x18002ceec`
- `0x18002d454`
- `0x18002d9e0`
- `0x18002dc04`
- `0x180030600`
- `0x180031928`
- `0x180033538`
- `0x1800339ac`
- `0x1800345b8`
- `0x1800350b0`
- `0x1800356d0`
- `0x18003c83c`
- `0x180096668`
- `0x1800967b0`
- `0x1800ad7bc`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003088a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003088a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003069f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003069f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030efe`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180030879`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180030879`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x1800307c4`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x18003081f`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x1800307c4`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x18003081f`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180030ee4`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180030ee4`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800306da`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800306da`

## string_xrefs

- `0x180030f9c`: `onecore\base\appmodel\execmodel\desktopappx\lib\NormalizedExclusionPathList.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall DesktopAppXVFS::GetAppdataMapping(
        __int64 a1,
        __int64 a2,
        char *a3,
        char a4,
        const KNOWNFOLDERID **a5)
{
  int v7; // r15d
  char *v8; // rsi
  __int64 v9; // r14
  int v10; // r15d
  __int64 StateFolderString; // rax
  __int64 v12; // r8
  const char *v13; // r9
  int v14; // r15d
  LPCWSTR *v15; // rdx
  const char *v16; // r9
  unsigned __int64 v17; // rdx
  LPCWSTR *v18; // rax
  char v19; // bl
  const WCHAR *v20; // rcx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  signed int v23; // ecx
  __int64 v24; // rdx
  char v25; // al
  LPCWSTR *v26; // rax
  unsigned int v27; // r15d
  __int128 v28; // xmm7
  __int64 v29; // xmm6_8
  char *v30; // rbx
  __int64 v31; // rax
  int v32; // eax
  int v33; // edx
  int v34; // r8d
  const KNOWNFOLDERID *v35; // rbx
  const KNOWNFOLDERID *v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  _QWORD *v39; // r12
  _QWORD *v40; // rbx
  const WCHAR **v41; // rdi
  const WCHAR *v42; // rcx
  int DirectoryTree; // eax
  _QWORD *v44; // rax
  __int64 *i; // rdi
  __int64 *v46; // rcx
  __int64 v47; // rbx
  __int64 **v48; // rax
  __int64 k; // rax
  _QWORD *v50; // r12
  bool IsAncestorOf; // al
  const unsigned __int16 *v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int128 v55; // rax
  int v56; // r15d
  __int64 v57; // rcx
  std::filesystem *v58; // rcx
  const unsigned __int16 *j; // rax
  const unsigned __int16 *v60; // rdx
  __int64 v61; // rcx
  const unsigned __int16 *v62; // r8
  const unsigned __int16 *v63; // r8
  __int64 v64; // xmm6_8
  int v65; // r15d
  const WCHAR *v66; // rcx
  int v67; // eax
  __int64 *m; // rcx
  int v70; // [rsp+28h] [rbp-E0h]
  char v71; // [rsp+38h] [rbp-D0h] BYREF
  int v72; // [rsp+3Ch] [rbp-CCh]
  __int64 v73; // [rsp+40h] [rbp-C8h]
  HANDLE hObject; // [rsp+48h] [rbp-C0h] BYREF
  char *v75; // [rsp+50h] [rbp-B8h] BYREF
  wil::details::in1diag3 *v76[2]; // [rsp+58h] [rbp-B0h] BYREF
  char *v77; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v78; // [rsp+70h] [rbp-98h] BYREF
  __int64 v79; // [rsp+80h] [rbp-88h]
  __int128 v80; // [rsp+88h] [rbp-80h]
  __int128 v81; // [rsp+98h] [rbp-70h]
  __int64 v82; // [rsp+A8h] [rbp-60h]
  __int64 v83; // [rsp+B8h] [rbp-50h]
  LPCWSTR lpFileName[2]; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v85; // [rsp+D8h] [rbp-30h]
  __int128 v86; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v87; // [rsp+F8h] [rbp-10h]
  __int128 v88; // [rsp+108h] [rbp+0h] BYREF
  __m128i v89; // [rsp+118h] [rbp+10h]
  _OWORD v90[2]; // [rsp+128h] [rbp+20h] BYREF
  std::filesystem *v91[2]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v92; // [rsp+158h] [rbp+50h]
  __int128 Src; // [rsp+168h] [rbp+60h] BYREF
  __m128i si128; // [rsp+178h] [rbp+70h]
  __int128 v95; // [rsp+188h] [rbp+80h] BYREF
  __int128 v96; // [rsp+198h] [rbp+90h]
  _BYTE v97[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v98[48]; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  LOBYTE(v73) = a4;
  v82 = a1;
  v75 = a3;
  v7 = 0;
  v72 = 0;
  v8 = 0;
  v77 = 0;
  if ( !a3 )
  {
    wil::open_current_access_token(&hObject, 0x20008u);
    v7 = 4;
    v72 = 4;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v77,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v8 = v77;
    v75 = v77;
  }
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)a2 + 16LL))(a2, v90);
  v9 = OpenStateExplicit(v75);
  v83 = v9;
  std::wstring::~wstring(v90);
  GetKnownFolderForUser<1>((__int64)&Src, &FOLDERID_Profile, v75);
  AppendPath(&Src);
  v76[0] = (wil::details::in1diag3 *)&v88;
  v88 = Src;
  v89 = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v86 = 0;
  v87 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v86, L"AppData", 7);
  v70 = 0;
  DesktopAppXVFS::Mapping::Mapping(a1, &v86, &v88, 5);
  v10 = v7 | 1;
  v72 = v10;
  StateFolderString = GetStateFolderString(v90);
  std::vector<WriteVirtualization::NormalizedFileSystemPath>::emplace_back<std::wstring>(a1 + 64, StateFolderString);
  std::wstring::~wstring(v90);
  v71 = 0;
  LODWORD(hObject) = 0;
  GetPublisherRootFolder(v9, 0, &hObject);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      v13);
  std::wstring::wstring(lpFileName, (unsigned int)hObject, v12, v13);
  v14 = v10 | 8;
  v72 = v14;
  v15 = lpFileName;
  if ( v85.m128i_i64[1] > 7uLL )
    v15 = (LPCWSTR *)lpFileName[0];
  if ( !(unsigned int)GetPublisherRootFolder(v9, v15, &hObject) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      v16);
  v17 = (unsigned int)((_DWORD)hObject - 1);
  if ( v17 > v85.m128i_i64[0] )
  {
    std::wstring::append(lpFileName);
    v19 = 0;
  }
  else
  {
    v18 = lpFileName;
    if ( v85.m128i_i64[1] > 7uLL )
      v18 = (LPCWSTR *)lpFileName[0];
    v85.m128i_i64[0] = (unsigned int)((_DWORD)hObject - 1);
    v19 = 0;
    *((_WORD *)v18 + v17) = 0;
  }
  v20 = (const WCHAR *)lpFileName;
  if ( v85.m128i_i64[1] > 7uLL )
    v20 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v20);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) == 0 )
      goto LABEL_33;
    v25 = 1;
    goto LABEL_28;
  }
  LastError = GetLastError();
  v23 = LastError;
  if ( LastError <= 0x35 && (v24 = 0x2000000000800CLL, _bittest64(&v24, LastError))
    || LastError == 67
    || LastError == 1203 )
  {
    v25 = 0;
LABEL_28:
    if ( v25 )
    {
      v26 = lpFileName;
      if ( v85.m128i_i64[1] > 7uLL )
        v26 = (LPCWSTR *)lpFileName[0];
      v76[0] = (wil::details::in1diag3 *)v26;
      v76[1] = (wil::details::in1diag3 *)v85.m128i_i64[0];
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v88, v76);
      std::filesystem::path::lexically_normal(&v88, v90);
      std::wstring::~wstring(&v88);
      v14 |= 0x12u;
      v72 = v14;
      if ( WriteVirtualization::NormalizedFileSystemPath::IsAncestorOf(
             (WriteVirtualization::NormalizedFileSystemPath *)(a1 + 32),
             (const struct WriteVirtualization::NormalizedFileSystemPath *)v90) )
      {
        v19 = 1;
      }
    }
    goto LABEL_33;
  }
  if ( (int)LastError > 0 )
    v23 = (unsigned __int16)LastError | 0x80070000;
  v25 = 0;
  if ( v23 >= 0 )
    goto LABEL_28;
LABEL_33:
  if ( (v14 & 2) != 0 )
  {
    v14 &= ~2u;
    v72 = v14;
    std::wstring::~wstring(v90);
  }
  if ( v19 )
  {
    v88 = *(_OWORD *)lpFileName;
    v89 = v85;
    v85.m128i_i64[0] = 0;
    v85.m128i_i64[1] = 7;
    LOWORD(lpFileName[0]) = 0;
    std::filesystem::path::lexically_normal(&v88, v90);
    std::wstring::~wstring(&v88);
    WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::NormalizedFileSystemPath>::Add(a1 + 96, v90);
    std::wstring::~wstring(v90);
  }
  v27 = v14 & 0xFFFFFFF7;
  v72 = v27;
  std::wstring::~wstring(lpFileName);
  *(_QWORD *)&v78 = &v75;
  *((_QWORD *)&v78 + 1) = a1;
  LOBYTE(v79) = v73;
  v28 = v78;
  v29 = v79;
  v30 = v75;
  v31 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)a2 + 16LL))(a2, v90);
  *(_OWORD *)lpFileName = v28;
  v85.m128i_i64[0] = v29;
  DesktopAppXVFS::VfsProviderDetails::ForEachHardcodedAppDataRedirectionExclusion__lambda_3470f7b7ea4b1075859e78e14c3d47a5___(
    v31,
    v30,
    lpFileName);
  std::wstring::~wstring(v90);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2) )
  {
    lpFileName[0] = (LPCWSTR)&v75;
    lpFileName[1] = (LPCWSTR)&v78;
    v85.m128i_i64[0] = (__int64)&v71;
    v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    WriteVirtualization::ExclusionListsInRegistry::Details::ForEachExclusionForPackage_WriteVirtualization::FileSystemExclusion__lambda_771e4c9fe534d61b5a84e07ef6b66b39___(
      (unsigned int)lpFileName,
      v33,
      v34,
      v32,
      (__int64)lpFileName);
  }
  v35 = *a5;
  v36 = a5[1];
  while ( v35 != v36 )
  {
    GetKnownFolderForUser<1>((__int64)v90, v35, v75);
    v37 = std::wstring::wstring(&v88, &v35[1]);
    v38 = DesktopAppXVFS::VfsProviderDetails::AppDataRedirectionExclusion::AppDataRedirectionExclusion(v97, v90, v37);
    lambda_3470f7b7ea4b1075859e78e14c3d47a5_::operator()(&v78, v38);
    std::wstring::~wstring(v98);
    std::wstring::~wstring(v97);
    v71 = 1;
    std::wstring::~wstring(v90);
    v35 += 3;
  }
  if ( (_BYTE)v73 && *(_QWORD *)(a1 + 104) )
  {
    hObject = *(HANDLE *)(a1 + 64);
    LoggedonUserImpersonation::Impersonate(lpFileName, v75);
    v39 = (_QWORD *)(a1 + 96);
    v40 = **(_QWORD ***)(a1 + 96);
    while ( v40 != (_QWORD *)*v39 )
    {
      v41 = (const WCHAR **)(v40 + 4);
      v42 = (const WCHAR *)(v40 + 4);
      if ( v40[7] > 7u )
        v42 = *v41;
      DirectoryTree = CreateDirectoryTree(v42, 0);
      if ( DirectoryTree == -2147024713 )
      {
        v44 = v40;
        i = (__int64 *)v40[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (__int64 *)v40[1]; !*((_BYTE *)i + 25) && v44 == (_QWORD *)i[2]; i = (__int64 *)i[1] )
            v44 = i;
        }
        else
        {
          v46 = (__int64 *)*i;
          if ( !*(_BYTE *)(*i + 25) )
          {
            do
            {
              i = v46;
              v46 = (__int64 *)*v46;
            }
            while ( !*((_BYTE *)v46 + 25) );
          }
        }
        v47 = std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>::_Extract(
                v39,
                v40);
        std::wstring::~wstring((void *)(v47 + 32));
        operator delete((void *)v47, 0x40u);
        v40 = i;
      }
      else
      {
        if ( DirectoryTree < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2ED,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
            (const char *)(unsigned int)DirectoryTree,
            v70);
        if ( v71 )
        {
          v50 = (_QWORD *)(a1 + 32);
          v76[0] = retaddr;
          IsAncestorOf = WriteVirtualization::NormalizedFileSystemPath::IsAncestorOf(
                           (WriteVirtualization::NormalizedFileSystemPath *)(a1 + 32),
                           (const struct WriteVirtualization::NormalizedFileSystemPath *)(v40 + 4));
          v52 = 0;
          if ( !IsAncestorOf )
            wil::details::in1diag3::Throw_Hr(
              v76[0],
              (void *)0xA7,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\NormalizedExclusionPathList.hpp",
              (const char *)0x80070057LL,
              v70);
          if ( v40[7] > 7u )
            v41 = (const WCHAR **)*v41;
          v53 = -1;
          do
            ++v53;
          while ( *((_WORD *)v41 + v53) );
          if ( *(_QWORD *)(a1 + 56) > 7u )
            v50 = (_QWORD *)*v50;
          v54 = -1;
          do
            ++v54;
          while ( *((_WORD *)v50 + v54) );
          if ( v53 == v54 )
          {
            *(_OWORD *)v91 = 0;
            *(_QWORD *)&v55 = 0;
            *(_QWORD *)&v92 = 0;
            *((_QWORD *)&v55 + 1) = 7;
            *((_QWORD *)&v92 + 1) = 7;
            LOWORD(v91[0]) = 0;
            v56 = v27 | 0x20;
            v72 = v56;
          }
          else
          {
            v57 = v54 + 1;
            *(_QWORD *)&v80 = (char *)v41 + 2 * v57;
            *((_QWORD *)&v80 + 1) = v53 - v57;
            *(_OWORD *)v76 = v80;
            std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v86, v76);
            *(_OWORD *)v91 = v86;
            v92 = v87;
            *(_QWORD *)&v87 = 0;
            *((_QWORD *)&v87 + 1) = 7;
            LOWORD(v86) = 0;
            v56 = v27 | 0x60;
            v72 = v56;
            std::wstring::~wstring(&v86);
            v55 = v92;
          }
          v58 = (std::filesystem *)v91;
          if ( *((_QWORD *)&v55 + 1) > 7u )
            v58 = v91[0];
          for ( j = std::filesystem::_Find_root_name_end(v58, (const unsigned __int16 *const)v58 + v55, v52);
                j != v60 && (*j == 92 || *j == 47);
                ++j )
          {
            ;
          }
          if ( j != v60 )
          {
            do
            {
              v62 = v60 - 1;
              if ( *(v60 - 1) == 92 )
                break;
              if ( *v62 == 47 )
                break;
              --v60;
            }
            while ( j != v62 );
            if ( j != v60 )
            {
              do
              {
                v63 = v60 - 1;
                if ( *(v60 - 1) != 92 && *v63 != 47 )
                  break;
                --v60;
              }
              while ( j != v63 );
            }
          }
          *(_QWORD *)&v81 = v61;
          *((_QWORD *)&v81 + 1) = ((__int64)v60 - v61) >> 1;
          *(_OWORD *)v76 = v81;
          std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v86, v76);
          v90[0] = v86;
          v64 = v87;
          v90[1] = v87;
          *(_QWORD *)&v87 = 0;
          *((_QWORD *)&v87 + 1) = 7;
          LOWORD(v86) = 0;
          v27 = v56 | 0x380;
          v72 = v27;
          std::wstring::~wstring(&v86);
          if ( v64 )
          {
            std::wstring::wstring(&v86, v90);
            std::filesystem::path::lexically_normal(&v86, &v88);
            std::wstring::~wstring(&v86);
            v76[0] = (wil::details::in1diag3 *)&v88;
            std::wstring::wstring(&v86, hObject);
            v65 = v27 | 0x800;
            v72 = v65;
            std::filesystem::path::operator/=(&v86, (std::filesystem *)&v88);
            v95 = v86;
            v96 = v87;
            *(_QWORD *)&v87 = 0;
            *((_QWORD *)&v87 + 1) = 7;
            LOWORD(v86) = 0;
            v27 = v65 & 0xFFFFF3FF | 0x400;
            v72 = v27;
            std::wstring::~wstring(&v86);
            std::wstring::~wstring(&v88);
            v66 = (const WCHAR *)&v95;
            if ( *((_QWORD *)&v96 + 1) > 7u )
              v66 = (const WCHAR *)v95;
            v67 = CreateDirectoryTree(v66, 0);
            if ( v67 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2FC,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
                (const char *)(unsigned int)v67,
                v70);
            std::wstring::~wstring(&v95);
          }
          std::wstring::~wstring(v90);
          std::wstring::~wstring(v91);
          v39 = (_QWORD *)(a1 + 96);
        }
      }
      v48 = (__int64 **)v40[2];
      if ( *((_BYTE *)v48 + 25) )
      {
        for ( k = v40[1]; !*(_BYTE *)(k + 25) && v40 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
          v40 = (_QWORD *)k;
        v40 = (_QWORD *)k;
      }
      else
      {
        v40 = (_QWORD *)v40[2];
        for ( m = *v48; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v40 = m;
      }
    }
    ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)lpFileName);
  }
  std::wstring::~wstring(&Src);
  if ( v9 )
    CloseState(v9);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return a1;
}

```

## disassembly

```asm
0x180030600  mov     rax, rsp
0x180030603  mov     [rax+20h], rbx
0x180030607  push    rbp
0x180030608  push    rsi
0x180030609  push    rdi
0x18003060a  push    r12
0x18003060c  push    r13
0x18003060e  push    r14
0x180030610  push    r15
0x180030612  lea     rbp, [rax-158h]
0x180030619  sub     rsp, 220h
0x180030620  movaps  xmmword ptr [rax-48h], xmm6
0x180030624  movaps  xmmword ptr [rax-58h], xmm7
0x180030628  mov     rax, cs:__security_cookie
0x18003062f  xor     rax, rsp
0x180030632  mov     [rbp+150h+var_60], rax
0x180030639  mov     byte ptr [rsp+250h+var_218], r9b
0x18003063e  mov     rdi, rdx
0x180030641  mov     r13, rcx
0x180030644  mov     [rbp+150h+var_1B0], rcx
0x180030648  mov     [rsp+250h+var_208], r8
0x18003064d  mov     r12, [rbp+150h+arg_20]
0x180030654  xor     ebx, ebx
0x180030656  mov     r15d, ebx
0x180030659  mov     [rsp+250h+var_21C], ebx
0x18003065d  mov     esi, ebx
0x18003065f  mov     qword ptr [rsp+250h+var_1F0], rbx
0x180030664  test    r8, r8
0x180030667  jnz     short loc_1800306B5
0x180030669  mov     edx, 20008h
0x18003066e  lea     rcx, [rsp+250h+hObject]
0x180030673  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x180030678  lea     r15d, [rbx+4]
0x18003067c  mov     [rsp+250h+var_21C], r15d
0x180030681  lea     rdx, [rsp+250h+hObject]
0x180030686  lea     rcx, [rsp+250h+var_1F0]
0x18003068b  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180030690  mov     rcx, [rsp+250h+hObject]; hObject
0x180030695  lea     rax, [rcx-1]
0x180030699  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003069d  ja      short loc_1800306AB
0x18003069f  call    cs:__imp_CloseHandle
0x1800306a6  nop     dword ptr [rax+rax+00h]
0x1800306ab  mov     rsi, qword ptr [rsp+250h+var_1F0]
0x1800306b0  mov     [rsp+250h+var_208], rsi
0x1800306b5  mov     rax, [rdi]
0x1800306b8  lea     rdx, [rbp+150h+var_130]
0x1800306bc  mov     rcx, rdi
0x1800306bf  mov     rax, [rax+10h]
0x1800306c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306c8  cmp     qword ptr [rax+18h], 7
0x1800306cd  jbe     short loc_1800306D2
0x1800306cf  mov     rax, [rax]
0x1800306d2  mov     rdx, rax
0x1800306d5  mov     rcx, [rsp+250h+var_208]
0x1800306da  call    cs:__imp_OpenStateExplicit
0x1800306e1  nop     dword ptr [rax+rax+00h]
0x1800306e6  mov     r14, rax
0x1800306e9  mov     [rbp+150h+var_1A0], rax
0x1800306ed  lea     rcx, [rbp+150h+var_130]; void *
0x1800306f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800306f6  mov     r8, [rsp+250h+var_208]
0x1800306fb  lea     rdx, FOLDERID_Profile
0x180030702  lea     rcx, [rbp+150h+Src]
0x180030706  call    ??$GetKnownFolderForUser@$00@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEAX@Z; GetKnownFolderForUser<1>(_GUID const &,void *)
0x18003070b  nop
0x18003070c  lea     rdx, aAppdata; "AppData"
0x180030713  lea     rcx, [rbp+150h+Src]; Src
0x180030717  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x18003071c  lea     rax, [rbp+150h+var_150]
0x180030720  mov     [rsp+250h+var_208+8], rax
0x180030725  movups  xmm0, [rbp+150h+Src]
0x180030729  movups  [rbp+150h+var_150], xmm0
0x18003072d  movups  xmm1, [rbp+150h+var_E0]
0x180030731  movups  [rbp+150h+var_140], xmm1
0x180030735  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18003073d  movdqu  [rbp+150h+var_E0], xmm0
0x180030742  mov     word ptr [rbp+150h+Src], bx
0x180030746  xorps   xmm0, xmm0
0x180030749  movups  [rbp+150h+var_170], xmm0
0x18003074d  mov     qword ptr [rbp+150h+var_160], rbx
0x180030751  mov     qword ptr [rbp+150h+var_160+8], rbx
0x180030755  mov     r8d, 7
0x18003075b  lea     rdx, aAppdata; "AppData"
0x180030762  lea     rcx, [rbp+150h+var_170]
0x180030766  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003076b  nop
0x18003076c  mov     [rsp+250h+var_230], ebx
0x180030770  mov     r9d, 5
0x180030776  lea     r8, [rbp+150h+var_150]
0x18003077a  lea     rdx, [rbp+150h+var_170]
0x18003077e  mov     rcx, r13
0x180030781  call    ??0Mapping@DesktopAppXVFS@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4MappingFlags@1@I@Z; DesktopAppXVFS::Mapping::Mapping(std::wstring,std::wstring,DesktopAppXVFS::MappingFlags,uint)
0x180030786  or      r15d, 1
0x18003078a  mov     [rsp+250h+var_21C], r15d
0x18003078f  mov     rdx, r14
0x180030792  lea     rcx, [rbp+150h+var_130]; Src
0x180030796  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x18003079b  nop
0x18003079c  lea     rcx, [r13+40h]
0x1800307a0  mov     rdx, rax
0x1800307a3  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@VNormalizedFileSystemPath@WriteVirtualization@@V?$allocator@VNormalizedFileSystemPath@WriteVirtualization@@@std@@@std@@QEAA?A_T$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z
0x1800307a8  nop
0x1800307a9  lea     rcx, [rbp+150h+var_130]; void *
0x1800307ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800307b2  mov     [rsp+250h+var_220], bl
0x1800307b6  mov     dword ptr [rsp+250h+hObject], ebx
0x1800307ba  lea     r8, [rsp+250h+hObject]
0x1800307bf  xor     edx, edx
0x1800307c1  mov     rcx, r14
0x1800307c4  call    cs:__imp_GetPublisherRootFolder
0x1800307cb  nop     dword ptr [rax+rax+00h]
0x1800307d0  mov     rbx, [rbp+158h]
0x1800307d7  call    cs:__imp_GetLastError
0x1800307de  nop     dword ptr [rax+rax+00h]
0x1800307e3  cmp     eax, 7Ah ; 'z'
0x1800307e6  jnz     loc_180030F57
0x1800307ec  mov     edx, dword ptr [rsp+250h+hObject]
0x1800307f0  lea     rcx, [rbp+150h+lpFileName]
0x1800307f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800307f9  or      r15d, 8
0x1800307fd  mov     [rsp+250h+var_21C], r15d
0x180030802  lea     rdx, [rbp+150h+lpFileName]
0x180030806  cmp     qword ptr [rbp+150h+var_180+8], 7
0x18003080b  cmova   rdx, [rbp+150h+lpFileName]
0x180030810  mov     rbx, [rbp+158h]
0x180030817  lea     r8, [rsp+250h+hObject]
0x18003081c  mov     rcx, r14
0x18003081f  call    cs:__imp_GetPublisherRootFolder
0x180030826  nop     dword ptr [rax+rax+00h]
0x18003082b  test    eax, eax
0x18003082d  jz      loc_180030F6C
0x180030833  mov     edx, dword ptr [rsp+250h+hObject]
0x180030837  dec     edx
0x180030839  cmp     rdx, qword ptr [rbp+150h+var_180]
0x18003083d  ja      short loc_180030859
0x18003083f  lea     rax, [rbp+150h+lpFileName]
0x180030843  cmp     qword ptr [rbp+150h+var_180+8], 7
0x180030848  cmova   rax, [rbp+150h+lpFileName]
0x18003084d  mov     qword ptr [rbp+150h+var_180], rdx
0x180030851  xor     ebx, ebx
0x180030853  mov     [rax+rdx*2], bx
0x180030857  jmp     short loc_18003086B
0x180030859  xor     r8d, r8d
0x18003085c  sub     rdx, qword ptr [rbp+150h+var_180]
0x180030860  lea     rcx, [rbp+150h+lpFileName]; Src
0x180030864  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180030869  xor     ebx, ebx
0x18003086b  lea     rcx, [rbp+150h+lpFileName]
0x18003086f  cmp     qword ptr [rbp+150h+var_180+8], 7
0x180030874  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x180030879  call    cs:__imp_GetFileAttributesW
0x180030880  nop     dword ptr [rax+rax+00h]
0x180030885  cmp     eax, 0FFFFFFFFh
0x180030888  jnz     short loc_1800308D3
0x18003088a  call    cs:__imp_GetLastError
0x180030891  nop     dword ptr [rax+rax+00h]
0x180030896  mov     ecx, eax
0x180030898  cmp     eax, 35h ; '5'
0x18003089b  ja      short loc_1800308AD
0x18003089d  mov     rdx, 2000000000800Ch
0x1800308a7  bt      rdx, rcx
0x1800308ab  jb      short loc_1800308CF
0x1800308ad  cmp     ecx, 43h ; 'C'
0x1800308b0  jz      short loc_1800308CF
0x1800308b2  cmp     ecx, 4B3h
0x1800308b8  jz      short loc_1800308CF
0x1800308ba  test    ecx, ecx
0x1800308bc  jle     short loc_1800308C7
0x1800308be  movzx   ecx, cx
0x1800308c1  or      ecx, 80070000h
0x1800308c7  mov     al, bl
0x1800308c9  test    ecx, ecx
0x1800308cb  js      short loc_180030943
0x1800308cd  jmp     short loc_1800308D9
0x1800308cf  mov     al, bl
0x1800308d1  jmp     short loc_1800308D9
0x1800308d3  test    al, 10h
0x1800308d5  jz      short loc_180030943
0x1800308d7  mov     al, 1
0x1800308d9  test    al, al
0x1800308db  jz      short loc_180030943
0x1800308dd  lea     rax, [rbp+150h+lpFileName]
0x1800308e1  cmp     qword ptr [rbp+150h+var_180+8], 7
0x1800308e6  cmova   rax, [rbp+150h+lpFileName]
0x1800308eb  mov     [rsp+250h+var_208+8], rax
0x1800308f0  mov     rax, qword ptr [rbp+150h+var_180]
0x1800308f4  mov     [rsp+250h+var_1F8], rax
0x1800308f9  lea     rdx, [rsp+250h+var_208+8]
0x1800308fe  lea     rcx, [rbp+150h+var_150]
0x180030902  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180030907  or      r15d, 10h
0x18003090b  mov     [rsp+250h+var_21C], r15d
0x180030910  lea     rdx, [rbp+150h+var_130]
0x180030914  lea     rcx, [rbp+150h+var_150]
0x180030918  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x18003091d  nop
0x18003091e  lea     rcx, [rbp+150h+var_150]; void *
0x180030922  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030927  or      r15d, 2
0x18003092b  mov     [rsp+250h+var_21C], r15d
0x180030930  lea     rcx, [r13+20h]; this
0x180030934  lea     rdx, [rbp+150h+var_130]; struct WriteVirtualization::NormalizedFileSystemPath *
0x180030938  call    ?IsAncestorOf@NormalizedFileSystemPath@WriteVirtualization@@QEBA_NAEBV12@@Z; WriteVirtualization::NormalizedFileSystemPath::IsAncestorOf(WriteVirtualization::NormalizedFileSystemPath const &)
0x18003093d  test    al, al
0x18003093f  jz      short loc_180030943
0x180030941  mov     bl, 1
0x180030943  test    r15b, 2
0x180030947  jz      short loc_18003095B
0x180030949  and     r15d, 0FFFFFFFDh
0x18003094d  mov     [rsp+250h+var_21C], r15d
0x180030952  lea     rcx, [rbp+150h+var_130]; void *
0x180030956  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003095b  xor     eax, eax
0x18003095d  test    bl, bl
0x18003095f  jz      short loc_1800309B0
0x180030961  movups  xmm0, xmmword ptr [rbp+150h+lpFileName]
0x180030965  movups  [rbp+150h+var_150], xmm0
0x180030969  movups  xmm1, [rbp+150h+var_180]
0x18003096d  movups  [rbp+150h+var_140], xmm1
0x180030971  mov     qword ptr [rbp+150h+var_180], rax
0x180030975  mov     qword ptr [rbp+150h+var_180+8], 7
0x18003097d  mov     word ptr [rbp+150h+lpFileName], ax
0x180030981  lea     rdx, [rbp+150h+var_130]
0x180030985  lea     rcx, [rbp+150h+var_150]
0x180030989  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x18003098e  nop
0x18003098f  lea     rcx, [rbp+150h+var_150]; void *
0x180030993  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030998  nop
0x180030999  lea     rcx, [r13+60h]
0x18003099d  lea     rdx, [rbp+150h+var_130]
0x1800309a1  call    ?Add@?$NormalizedExclusionPathList@VNormalizedFileSystemPath@WriteVirtualization@@@WriteVirtualization@@QEAA_N$$QEAVNormalizedFileSystemPath@2@@Z; WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::NormalizedFileSystemPath>::Add(WriteVirtualization::NormalizedFileSystemPath &&)
0x1800309a6  nop
0x1800309a7  lea     rcx, [rbp+150h+var_130]; void *
0x1800309ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800309b0  and     r15d, 0FFFFFFF7h
0x1800309b4  mov     [rsp+250h+var_21C], r15d
0x1800309b9  lea     rcx, [rbp+150h+lpFileName]; void *
0x1800309bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800309c2  lea     rax, [rsp+250h+var_208]
0x1800309c7  mov     qword ptr [rsp+250h+var_1F0+8], rax
0x1800309cc  mov     [rsp+250h+var_1E0], r13
0x1800309d1  mov     al, byte ptr [rsp+250h+var_218]
0x1800309d5  mov     byte ptr [rsp+250h+var_1D8], al
0x1800309d9  movups  xmm7, [rsp+250h+var_1F0+8]
0x1800309de  movsd   xmm6, [rsp+250h+var_1D8]
0x1800309e4  mov     rbx, [rsp+250h+var_208]
0x1800309e9  mov     rax, [rdi]
0x1800309ec  lea     rdx, [rbp+150h+var_130]
0x1800309f0  mov     rcx, rdi
0x1800309f3  mov     rax, [rax+10h]
0x1800309f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309fc  nop
0x1800309fd  movaps  xmmword ptr [rbp+150h+lpFileName], xmm7
0x180030a01  movsd   qword ptr [rbp+150h+var_180], xmm6
0x180030a06  lea     r8, [rbp+150h+lpFileName]
0x180030a0a  mov     rdx, rbx
0x180030a0d  mov     rcx, rax
0x180030a10  call    DesktopAppXVFS__VfsProviderDetails__ForEachHardcodedAppDataRedirectionExclusion__lambda_3470f7b7ea4b1075859e78e14c3d47a5___
0x180030a15  nop
0x180030a16  lea     rcx, [rbp+150h+var_130]; void *
0x180030a1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030a1f  mov     rax, [rdi]
0x180030a22  mov     rcx, rdi
0x180030a25  mov     rax, [rax+20h]
0x180030a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a2e  test    al, al
0x180030a30  jnz     short loc_180030A6D
0x180030a32  lea     rax, [rsp+250h+var_208]
0x180030a37  mov     [rbp+150h+lpFileName], rax
0x180030a3b  lea     rax, [rsp+250h+var_1F0+8]
0x180030a40  mov     [rbp+150h+lpFileName+8], rax
0x180030a44  lea     rax, [rsp+250h+var_220]
0x180030a49  mov     qword ptr [rbp+150h+var_180], rax
0x180030a4d  mov     rax, [rdi]
0x180030a50  mov     rcx, rdi
0x180030a53  mov     rax, [rax+8]
0x180030a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a5c  lea     rcx, [rbp+150h+lpFileName]
0x180030a60  mov     qword ptr [rsp+250h+var_230], rcx
0x180030a65  mov     r9, rax
0x180030a68  call    WriteVirtualization__ExclusionListsInRegistry__Details__ForEachExclusionForPackage_WriteVirtualization__FileSystemExclusion__lambda_771e4c9fe534d61b5a84e07ef6b66b39___
0x180030a6d  mov     rbx, [r12]
0x180030a71  mov     rdi, [r12+8]
0x180030a76  jmp     short loc_180030AE3
0x180030a78  mov     r8, [rsp+250h+var_208]
0x180030a7d  mov     rdx, rbx
0x180030a80  lea     rcx, [rbp+150h+var_130]
0x180030a84  call    ??$GetKnownFolderForUser@$00@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEAX@Z; GetKnownFolderForUser<1>(_GUID const &,void *)
0x180030a89  nop
0x180030a8a  lea     rdx, [rbx+10h]
0x180030a8e  lea     rcx, [rbp+150h+var_150]
0x180030a92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030a97  mov     r8, rax
0x180030a9a  lea     rdx, [rbp+150h+var_130]
0x180030a9e  lea     rcx, [rbp+150h+var_B0]
0x180030aa5  call    ??0AppDataRedirectionExclusion@VfsProviderDetails@DesktopAppXVFS@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z; DesktopAppXVFS::VfsProviderDetails::AppDataRedirectionExclusion::AppDataRedirectionExclusion(std::wstring const &,std::wstring)
0x180030aaa  nop
0x180030aab  mov     rdx, rax
  ... truncated ...
```
