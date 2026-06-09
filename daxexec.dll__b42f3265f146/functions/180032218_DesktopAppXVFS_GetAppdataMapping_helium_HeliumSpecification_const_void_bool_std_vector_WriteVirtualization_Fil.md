# DesktopAppXVFS::GetAppdataMapping(helium::HeliumSpecification const &,void *,bool,std::vector<WriteVirtualization::FileSystemExclusion,std::allocator<WriteVirtualization::FileSystemExclusion>> const &)

- ea: `0x180032218`
- end: `0x180032b71`
- name: `?GetAppdataMapping@DesktopAppXVFS@@YA?AUMapping@1@AEBVHeliumSpecification@helium@@PEAX_NAEBV?$vector@UFileSystemExclusion@WriteVirtualization@@V?$allocator@UFileSystemExclusion@WriteVirtualization@@@std@@@std@@@Z`
- size: `2393`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, __int64 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030254`

## callees

- `0x180004f70`
- `0x180005340`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x1800165bc`
- `0x1800210fc`
- `0x18002574c`
- `0x180025e60`
- `0x180026540`
- `0x1800270fc`
- `0x1800281a0`
- `0x18002b54c`
- `0x18002bab4`
- `0x18002bd88`
- `0x18002c160`
- `0x18002d56c`
- `0x18002d978`
- `0x18002dc5c`
- `0x18002e5ec`
- `0x18002e804`
- `0x180032218`
- `0x1800334d8`
- `0x180035078`
- `0x1800354dc`
- `0x1800369b4`
- `0x180037040`
- `0x1800371c8`
- `0x18003e43c`
- `0x180097fb8`
- `0x18009815c`
- `0x1800aec9c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800322b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032abe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800322b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032abe`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003247b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003247b`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800322f3`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800322f3`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180032a9f`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180032a9f`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x1800323ef`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x18003244a`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x1800323ef`
- `api-ms-win-appmodel-state-l1-2-0!GetPublisherRootFolder` at `0x18003244a`

## string_xrefs

- `0x180032b5c`: `onecore\base\appmodel\execmodel\desktopappx\lib\NormalizedExclusionPathList.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DesktopAppXVFS::GetAppdataMapping(__int64 a1, __int64 a2, __int64 a3, char a4, __int64 *a5)
{
  int v8; // r14d
  _QWORD *v9; // rax
  __int64 v10; // rsi
  int v11; // r14d
  __int64 StateFolderString; // rax
  __int64 v13; // r8
  const char *v14; // r9
  int v15; // r14d
  LPCWSTR *v16; // rdx
  const char *v17; // r9
  const WCHAR *v18; // rcx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  signed int v21; // ecx
  __int64 v22; // rdx
  char v23; // al
  char v24; // bl
  unsigned int v25; // r14d
  char v26; // di
  __int128 v27; // xmm6
  __int64 v28; // xmm7_8
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r9
  int v32; // eax
  int v33; // edx
  int v34; // r8d
  __int64 v35; // rbx
  __int64 v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 **v39; // r15
  __int64 *v40; // rdi
  const WCHAR **v41; // rbx
  const WCHAR *v42; // rcx
  int DirectoryTree; // eax
  __int64 *i; // rbx
  __int64 *v45; // rax
  __int64 *v46; // rcx
  __int64 v47; // rdi
  _QWORD *v48; // r15
  __int64 v49; // rdx
  __int64 v50; // rcx
  const unsigned __int16 *v51; // r8
  unsigned __int64 v52; // rdx
  int v53; // r14d
  __int64 v54; // rcx
  std::filesystem *v55; // rcx
  const unsigned __int16 *j; // rax
  const unsigned __int16 *v57; // rdx
  __int64 v58; // rcx
  const unsigned __int16 *v59; // r8
  const unsigned __int16 *v60; // r8
  __int64 v61; // xmm6_8
  __int64 v62; // rax
  const WCHAR *v63; // rcx
  int v64; // eax
  __int64 **v65; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  int v69; // [rsp+28h] [rbp-E0h]
  char v70; // [rsp+38h] [rbp-D0h] BYREF
  int v71; // [rsp+3Ch] [rbp-CCh]
  __int64 v72; // [rsp+40h] [rbp-C8h]
  HANDLE hObject; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v74[2]; // [rsp+50h] [rbp-B8h] BYREF
  char *v75; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE v76[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v77; // [rsp+78h] [rbp-90h]
  _QWORD v78[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v79[5]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v80; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v81; // [rsp+D0h] [rbp-38h]
  LPCWSTR lpFileName[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v83; // [rsp+F8h] [rbp-10h]
  std::filesystem *v84[2]; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 *v85[2]; // [rsp+118h] [rbp+10h]
  __int128 v86; // [rsp+128h] [rbp+20h] BYREF
  __int128 v87; // [rsp+138h] [rbp+30h]
  WCHAR String1[8]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v89; // [rsp+158h] [rbp+50h]
  _BYTE v90[32]; // [rsp+168h] [rbp+60h] BYREF
  __int128 Src; // [rsp+188h] [rbp+80h] BYREF
  __int128 v92; // [rsp+198h] [rbp+90h]
  _BYTE v93[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v94[48]; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  LOBYTE(v72) = a4;
  v79[2] = a1;
  v74[0] = a3;
  v8 = 0;
  v71 = 0;
  v75 = 0;
  if ( !a3 )
  {
    wil::open_current_access_token(&hObject, 131080);
    v8 = 4;
    v71 = 4;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v75,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v74[0] = v75;
  }
  v9 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 16LL))(a2, v90);
  if ( v9[3] > 7u )
    v9 = (_QWORD *)*v9;
  v10 = OpenStateExplicit(v74[0], v9);
  v79[4] = v10;
  std::wstring::~wstring(v90);
  GetKnownFolderForUser<1>(&Src, &FOLDERID_Profile, v74[0]);
  AppendPath(&Src);
  hObject = &v86;
  v86 = Src;
  v87 = v92;
  *(_QWORD *)&v92 = 0;
  *((_QWORD *)&v92 + 1) = 7;
  LOWORD(Src) = 0;
  v80 = 0;
  v81 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v80, L"AppData", 7);
  DesktopAppXVFS::Mapping::Mapping(a1, &v80, &v86, 5, 0);
  v11 = v8 | 1;
  v71 = v11;
  StateFolderString = GetStateFolderString(v90);
  std::vector<WriteVirtualization::NormalizedFileSystemPath>::emplace_back<std::wstring>(a1 + 64, StateFolderString);
  std::wstring::~wstring(v90);
  v70 = 0;
  LODWORD(hObject) = 0;
  GetPublisherRootFolder(v10, 0, &hObject);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      v14);
  std::wstring::wstring(lpFileName, (unsigned int)hObject, v13, v14);
  v15 = v11 | 8;
  v71 = v15;
  v16 = lpFileName;
  if ( *((_QWORD *)&v83 + 1) > 7u )
    v16 = (LPCWSTR *)lpFileName[0];
  if ( !(unsigned int)GetPublisherRootFolder(v10, v16, &hObject) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      v17);
  std::wstring::resize(lpFileName);
  v18 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v83 + 1) > 7u )
    v18 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v18);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v21 = LastError;
    if ( LastError <= 0x35 )
    {
      v22 = 0x2000000000800CLL;
      if ( _bittest64(&v22, LastError) )
        goto LABEL_21;
    }
    if ( LastError == 67 || LastError == 1203 )
      goto LABEL_21;
    if ( (int)LastError > 0 )
      v21 = (unsigned __int16)LastError | 0x80070000;
    v23 = 0;
    if ( v21 < 0 )
      goto LABEL_21;
  }
  else
  {
    if ( (FileAttributesW & 0x10) == 0 )
    {
LABEL_21:
      v24 = 0;
      goto LABEL_22;
    }
    v23 = 1;
  }
  if ( !v23 )
    goto LABEL_21;
  WriteVirtualization::NormalizedFileSystemPath::NormalizedFileSystemPath(String1, lpFileName);
  v15 |= 2u;
  v71 = v15;
  if ( !WriteVirtualization::NormalizedFileSystemPath::IsAncestorOf((LPCWCH)(a1 + 32), String1) )
    goto LABEL_21;
  v24 = 1;
LABEL_22:
  if ( (v15 & 2) != 0 )
  {
    v15 &= ~2u;
    v71 = v15;
    std::wstring::~wstring(String1);
  }
  if ( v24 )
  {
    v86 = *(_OWORD *)lpFileName;
    v87 = v83;
    *(_QWORD *)&v83 = 0;
    *((_QWORD *)&v83 + 1) = 7;
    LOWORD(lpFileName[0]) = 0;
    std::filesystem::path::lexically_normal(&v86, String1);
    std::wstring::~wstring(&v86);
    WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::NormalizedFileSystemPath>::Add(
      a1 + 96,
      String1);
    std::wstring::~wstring(String1);
  }
  v25 = v15 & 0xFFFFFFF7;
  v71 = v25;
  std::wstring::~wstring(lpFileName);
  v76[0] = v74;
  v76[1] = (HANDLE)a1;
  LOBYTE(v77) = a4;
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2);
  v27 = *(_OWORD *)v76;
  v28 = v77;
  v29 = v74[0];
  v30 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 16LL))(a2, v90);
  *(_OWORD *)lpFileName = v27;
  *(_QWORD *)&v83 = v28;
  LOBYTE(v31) = v26;
  DesktopAppXVFS::VfsProviderDetails::ForEachHardcodedAppDataRedirectionExclusion__lambda_3470f7b7ea4b1075859e78e14c3d47a5___(
    v30,
    v29,
    lpFileName,
    v31);
  std::wstring::~wstring(v90);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2) )
  {
    lpFileName[0] = (LPCWSTR)v74;
    lpFileName[1] = (LPCWSTR)v76;
    *(_QWORD *)&v83 = &v70;
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
    GetKnownFolderForUser<1>(String1, v35, v74[0]);
    v37 = std::wstring::wstring(v90, v35 + 16);
    v38 = DesktopAppXVFS::VfsProviderDetails::AppDataRedirectionExclusion::AppDataRedirectionExclusion(
            v93,
            String1,
            v37);
    lambda_3470f7b7ea4b1075859e78e14c3d47a5_::operator()(v76, v38);
    std::wstring::~wstring(v94);
    std::wstring::~wstring(v93);
    v70 = 1;
    std::wstring::~wstring(String1);
    v35 += 48;
  }
  if ( (_BYTE)v72 && *(_QWORD *)(a1 + 104) )
  {
    hObject = *(HANDLE *)(a1 + 64);
    LoggedonUserImpersonation::Impersonate(lpFileName, v74[0]);
    v39 = (__int64 **)(a1 + 96);
    v40 = **(__int64 ***)(a1 + 96);
    while ( v40 != *v39 )
    {
      v41 = (const WCHAR **)(v40 + 4);
      v42 = (const WCHAR *)(v40 + 4);
      if ( (unsigned __int64)v40[7] > 7 )
        v42 = *v41;
      DirectoryTree = CreateDirectoryTree(v42, 0);
      if ( DirectoryTree == -2147024713 )
      {
        i = (__int64 *)v40[2];
        if ( *((_BYTE *)i + 25) )
        {
          v45 = v40;
          for ( i = (__int64 *)v40[1]; !*((_BYTE *)i + 25) && v45 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v45 = i;
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
            (void *)0x301,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
            (const char *)(unsigned int)DirectoryTree,
            v69);
        if ( v70 )
        {
          v48 = (_QWORD *)(a1 + 32);
          if ( !WriteVirtualization::NormalizedFileSystemPath::IsAncestorOf((LPCWCH)(a1 + 32), (LPCWCH)v40 + 16) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA7,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\NormalizedExclusionPathList.hpp",
              (const char *)0x80070057LL,
              v69);
          if ( (unsigned __int64)v40[7] > 7 )
            v41 = (const WCHAR **)*v41;
          v49 = -1;
          do
            ++v49;
          while ( *((_WORD *)v41 + v49) );
          if ( *(_QWORD *)(a1 + 56) > 7u )
            v48 = (_QWORD *)*v48;
          v50 = -1;
          do
            ++v50;
          while ( *((_WORD *)v48 + v50) );
          if ( v49 == v50 )
          {
            *(_OWORD *)v84 = 0;
            v51 = 0;
            v85[0] = 0;
            v52 = 7;
            v85[1] = (unsigned __int16 *)7;
            LOWORD(v84[0]) = 0;
            v53 = v25 | 0x10;
            v71 = v53;
          }
          else
          {
            v54 = v50 + 1;
            v78[0] = (char *)v41 + 2 * v54;
            v78[1] = v49 - v54;
            std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v80, v78);
            *(_OWORD *)v84 = v80;
            *(_OWORD *)v85 = v81;
            *(_QWORD *)&v81 = 0;
            *((_QWORD *)&v81 + 1) = 7;
            LOWORD(v80) = 0;
            v53 = v25 | 0x30;
            v71 = v53;
            std::wstring::~wstring(&v80);
            v52 = (unsigned __int64)v85[1];
            v51 = v85[0];
          }
          v55 = (std::filesystem *)v84;
          if ( v52 > 7 )
            v55 = v84[0];
          for ( j = std::filesystem::_Find_root_name_end(v55, (const unsigned __int16 *const)v55 + (_QWORD)v51, v51);
                j != v57 && (*j == 92 || *j == 47);
                ++j )
          {
            ;
          }
          if ( j != v57 )
          {
            do
            {
              v59 = v57 - 1;
              if ( *(v57 - 1) == 92 )
                break;
              if ( *v59 == 47 )
                break;
              --v57;
            }
            while ( j != v59 );
            if ( j != v57 )
            {
              do
              {
                v60 = v57 - 1;
                if ( *(v57 - 1) != 92 && *v60 != 47 )
                  break;
                --v57;
              }
              while ( j != v60 );
            }
          }
          v79[0] = v58;
          v79[1] = ((__int64)v57 - v58) >> 1;
          std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v80, v79);
          *(_OWORD *)String1 = v80;
          v61 = v81;
          v89 = v81;
          *(_QWORD *)&v81 = 0;
          *((_QWORD *)&v81 + 1) = 7;
          LOWORD(v80) = 0;
          v25 = v53 | 0x1C0;
          v71 = v25;
          std::wstring::~wstring(&v80);
          if ( v61 )
          {
            std::wstring::wstring(v90, String1);
            std::filesystem::path::lexically_normal(v90, &v86);
            std::wstring::~wstring(v90);
            v74[1] = &v86;
            v62 = std::filesystem::operator/(v90, hObject, (std::filesystem *)&v86);
            v80 = 0;
            v81 = 0u;
            v80 = *(_OWORD *)v62;
            v81 = *(_OWORD *)(v62 + 16);
            *(_QWORD *)(v62 + 16) = 0;
            *(_QWORD *)(v62 + 24) = 7;
            *(_WORD *)v62 = 0;
            v25 |= 0x200u;
            v71 = v25;
            std::wstring::~wstring(v90);
            std::wstring::~wstring(&v86);
            v63 = (const WCHAR *)&v80;
            if ( *((_QWORD *)&v81 + 1) > 7u )
              v63 = (const WCHAR *)v80;
            v64 = CreateDirectoryTree(v63, 0);
            if ( v64 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x310,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
                (const char *)(unsigned int)v64,
                v69);
            std::wstring::~wstring(&v80);
          }
          std::wstring::~wstring(String1);
          std::wstring::~wstring(v84);
          v39 = (__int64 **)(a1 + 96);
        }
      }
      v65 = (__int64 **)v40[2];
      if ( *((_BYTE *)v65 + 25) )
      {
        for ( k = (__int64 *)v40[1]; !*((_BYTE *)k + 25) && v40 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v40 = k;
        v40 = k;
      }
      else
      {
        v40 = (__int64 *)v40[2];
        for ( m = *v65; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v40 = m;
      }
    }
    ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)lpFileName);
  }
  std::wstring::~wstring(&Src);
  if ( v10 )
    CloseState(v10);
  if ( (unsigned __int64)(v75 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v75);
  return a1;
}

```

## disassembly

```asm
0x180032218  mov     rax, rsp
0x18003221b  mov     [rax+20h], rbx
0x18003221f  push    rbp
0x180032220  push    rsi
0x180032221  push    rdi
0x180032222  push    r12
0x180032224  push    r13
0x180032226  push    r14
0x180032228  push    r15
0x18003222a  lea     rbp, [rax-158h]
0x180032231  sub     rsp, 220h
0x180032238  movaps  xmmword ptr [rax-48h], xmm6
0x18003223c  movaps  xmmword ptr [rax-58h], xmm7
0x180032240  mov     rax, cs:__security_cookie
0x180032247  xor     rax, rsp
0x18003224a  mov     [rbp+150h+var_60], rax
0x180032251  mov     dil, r9b
0x180032254  mov     byte ptr [rsp+250h+var_218], r9b
0x180032259  mov     r15, rdx
0x18003225c  mov     r13, rcx
0x18003225f  mov     [rbp+150h+var_1B0], rcx
0x180032263  mov     [rsp+250h+var_208], r8
0x180032268  mov     r12, [rbp+150h+arg_20]
0x18003226f  xor     ebx, ebx
0x180032271  mov     r14d, ebx
0x180032274  mov     [rsp+250h+var_21C], ebx
0x180032278  mov     [rsp+250h+var_1F8], rbx
0x18003227d  test    r8, r8
0x180032280  jnz     short loc_1800322CE
0x180032282  mov     edx, 20008h
0x180032287  lea     rcx, [rsp+250h+hObject]
0x18003228c  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x180032291  lea     r14d, [rbx+4]
0x180032295  mov     [rsp+250h+var_21C], r14d
0x18003229a  lea     rdx, [rsp+250h+hObject]
0x18003229f  lea     rcx, [rsp+250h+var_1F8]
0x1800322a4  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800322a9  mov     rcx, [rsp+250h+hObject]; hObject
0x1800322ae  lea     rax, [rcx-1]
0x1800322b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800322b6  ja      short loc_1800322C4
0x1800322b8  call    cs:__imp_CloseHandle
0x1800322bf  nop     dword ptr [rax+rax+00h]
0x1800322c4  mov     rax, [rsp+250h+var_1F8]
0x1800322c9  mov     [rsp+250h+var_208], rax
0x1800322ce  mov     rax, [r15]
0x1800322d1  lea     rdx, [rbp+150h+var_F0]
0x1800322d5  mov     rcx, r15
0x1800322d8  mov     rax, [rax+10h]
0x1800322dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322e1  cmp     qword ptr [rax+18h], 7
0x1800322e6  jbe     short loc_1800322EB
0x1800322e8  mov     rax, [rax]
0x1800322eb  mov     rdx, rax
0x1800322ee  mov     rcx, [rsp+250h+var_208]
0x1800322f3  call    cs:__imp_OpenStateExplicit
0x1800322fa  nop     dword ptr [rax+rax+00h]
0x1800322ff  mov     rsi, rax
0x180032302  mov     [rbp+150h+var_1A0], rax
0x180032306  lea     rcx, [rbp+150h+var_F0]; void *
0x18003230a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003230f  mov     r8, [rsp+250h+var_208]
0x180032314  lea     rdx, FOLDERID_Profile
0x18003231b  lea     rcx, [rbp+150h+Src]
0x180032322  call    ??$GetKnownFolderForUser@$00@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEAX@Z; GetKnownFolderForUser<1>(_GUID const &,void *)
0x180032327  nop
0x180032328  lea     rdx, aAppdata; "AppData"
0x18003232f  lea     rcx, [rbp+150h+Src]; Src
0x180032336  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x18003233b  lea     rax, [rbp+150h+var_130]
0x18003233f  mov     [rsp+250h+hObject], rax
0x180032344  movups  xmm0, [rbp+150h+Src]
0x18003234b  movups  [rbp+150h+var_130], xmm0
0x18003234f  movups  xmm1, [rbp+150h+var_C0]
0x180032356  movups  [rbp+150h+var_120], xmm1
0x18003235a  mov     qword ptr [rbp+150h+var_C0], rbx
0x180032361  mov     ecx, 7
0x180032366  mov     qword ptr [rbp+150h+var_C0+8], rcx
0x18003236d  mov     word ptr [rbp+150h+Src], bx
0x180032374  xorps   xmm0, xmm0
0x180032377  movups  [rbp+150h+var_198], xmm0
0x18003237b  mov     qword ptr [rbp+150h+var_188], rbx
0x18003237f  mov     qword ptr [rbp+150h+var_188+8], rbx
0x180032383  mov     r8d, ecx
0x180032386  lea     rdx, aAppdata; "AppData"
0x18003238d  lea     rcx, [rbp+150h+var_198]
0x180032391  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032396  nop
0x180032397  mov     [rsp+250h+var_230], ebx
0x18003239b  mov     r9d, 5
0x1800323a1  lea     r8, [rbp+150h+var_130]
0x1800323a5  lea     rdx, [rbp+150h+var_198]
0x1800323a9  mov     rcx, r13
0x1800323ac  call    ??0Mapping@DesktopAppXVFS@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4MappingFlags@1@I@Z; DesktopAppXVFS::Mapping::Mapping(std::wstring,std::wstring,DesktopAppXVFS::MappingFlags,uint)
0x1800323b1  or      r14d, 1
0x1800323b5  mov     [rsp+250h+var_21C], r14d
0x1800323ba  mov     rdx, rsi
0x1800323bd  lea     rcx, [rbp+150h+var_F0]; Src
0x1800323c1  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x1800323c6  nop
0x1800323c7  lea     rcx, [r13+40h]
0x1800323cb  mov     rdx, rax
0x1800323ce  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@VNormalizedFileSystemPath@WriteVirtualization@@V?$allocator@VNormalizedFileSystemPath@WriteVirtualization@@@std@@@std@@QEAAAEAVNormalizedFileSystemPath@WriteVirtualization@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<WriteVirtualization::NormalizedFileSystemPath>::emplace_back<std::wstring>(std::wstring &&)
0x1800323d3  nop
0x1800323d4  lea     rcx, [rbp+150h+var_F0]; void *
0x1800323d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323dd  mov     [rsp+250h+var_220], bl
0x1800323e1  mov     dword ptr [rsp+250h+hObject], ebx
0x1800323e5  lea     r8, [rsp+250h+hObject]
0x1800323ea  xor     edx, edx
0x1800323ec  mov     rcx, rsi
0x1800323ef  call    cs:__imp_GetPublisherRootFolder
0x1800323f6  nop     dword ptr [rax+rax+00h]
0x1800323fb  mov     rbx, [rbp+158h]
0x180032402  call    cs:__imp_GetLastError
0x180032409  nop     dword ptr [rax+rax+00h]
0x18003240e  cmp     eax, 7Ah ; 'z'
0x180032411  jnz     loc_180032B17
0x180032417  mov     edx, dword ptr [rsp+250h+hObject]
0x18003241b  lea     rcx, [rbp+150h+lpFileName]
0x18003241f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180032424  or      r14d, 8
0x180032428  mov     [rsp+250h+var_21C], r14d
0x18003242d  lea     rdx, [rbp+150h+lpFileName]
0x180032431  cmp     qword ptr [rbp+150h+var_160+8], 7
0x180032436  cmova   rdx, [rbp+150h+lpFileName]
0x18003243b  mov     rbx, [rbp+158h]
0x180032442  lea     r8, [rsp+250h+hObject]
0x180032447  mov     rcx, rsi
0x18003244a  call    cs:__imp_GetPublisherRootFolder
0x180032451  nop     dword ptr [rax+rax+00h]
0x180032456  test    eax, eax
0x180032458  jz      loc_180032B2C
0x18003245e  mov     edx, dword ptr [rsp+250h+hObject]
0x180032462  dec     edx
0x180032464  lea     rcx, [rbp+150h+lpFileName]; Src
0x180032468  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18003246d  lea     rcx, [rbp+150h+lpFileName]
0x180032471  cmp     qword ptr [rbp+150h+var_160+8], 7
0x180032476  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x18003247b  call    cs:__imp_GetFileAttributesW
0x180032482  nop     dword ptr [rax+rax+00h]
0x180032487  cmp     eax, 0FFFFFFFFh
0x18003248a  jnz     loc_180032627
0x180032490  call    cs:__imp_GetLastError
0x180032497  nop     dword ptr [rax+rax+00h]
0x18003249c  mov     ecx, eax
0x18003249e  cmp     eax, 35h ; '5'
0x1800324a1  ja      short loc_1800324B3
0x1800324a3  mov     rdx, 2000000000800Ch
0x1800324ad  bt      rdx, rcx
0x1800324b1  jb      short loc_1800324D7
0x1800324b3  cmp     ecx, 43h ; 'C'
0x1800324b6  jz      short loc_1800324D7
0x1800324b8  cmp     ecx, 4B3h
0x1800324be  jz      short loc_1800324D7
0x1800324c0  test    ecx, ecx
0x1800324c2  jle     short loc_1800324CD
0x1800324c4  movzx   ecx, cx
0x1800324c7  or      ecx, 80070000h
0x1800324cd  xor     al, al
0x1800324cf  test    ecx, ecx
0x1800324d1  jns     loc_180032631
0x1800324d7  xor     bl, bl
0x1800324d9  test    r14b, 2
0x1800324dd  jz      short loc_1800324F1
0x1800324df  and     r14d, 0FFFFFFFDh
0x1800324e3  mov     [rsp+250h+var_21C], r14d
0x1800324e8  lea     rcx, [rbp+150h+String1]; void *
0x1800324ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800324f1  test    bl, bl
0x1800324f3  jz      short loc_18003254A
0x1800324f5  movups  xmm0, xmmword ptr [rbp+150h+lpFileName]
0x1800324f9  movups  [rbp+150h+var_130], xmm0
0x1800324fd  movups  xmm1, [rbp+150h+var_160]
0x180032501  movups  [rbp+150h+var_120], xmm1
0x180032505  mov     qword ptr [rbp+150h+var_160], 0
0x18003250d  mov     qword ptr [rbp+150h+var_160+8], 7
0x180032515  xor     eax, eax
0x180032517  mov     word ptr [rbp+150h+lpFileName], ax
0x18003251b  lea     rdx, [rbp+150h+String1]
0x18003251f  lea     rcx, [rbp+150h+var_130]
0x180032523  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x180032528  nop
0x180032529  lea     rcx, [rbp+150h+var_130]; void *
0x18003252d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032532  nop
0x180032533  lea     rcx, [r13+60h]
0x180032537  lea     rdx, [rbp+150h+String1]
0x18003253b  call    ?Add@?$NormalizedExclusionPathList@VNormalizedFileSystemPath@WriteVirtualization@@@WriteVirtualization@@QEAA_N$$QEAVNormalizedFileSystemPath@2@@Z; WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::NormalizedFileSystemPath>::Add(WriteVirtualization::NormalizedFileSystemPath &&)
0x180032540  nop
0x180032541  lea     rcx, [rbp+150h+String1]; void *
0x180032545  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003254a  and     r14d, 0FFFFFFF7h
0x18003254e  mov     [rsp+250h+var_21C], r14d
0x180032553  lea     rcx, [rbp+150h+lpFileName]; void *
0x180032557  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003255c  lea     rax, [rsp+250h+var_208]
0x180032561  mov     [rsp+250h+var_1F8+8], rax
0x180032566  mov     [rsp+250h+var_1E8], r13
0x18003256b  mov     byte ptr [rsp+250h+var_1E0], dil
0x180032570  mov     rax, [r15]
0x180032573  mov     rcx, r15
0x180032576  mov     rax, [rax+38h]
0x18003257a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003257f  mov     dil, al
0x180032582  movups  xmm6, xmmword ptr [rsp+250h+var_1F8+8]
0x180032587  movsd   xmm7, [rsp+250h+var_1E0]
0x18003258d  mov     rbx, [rsp+250h+var_208]
0x180032592  mov     rax, [r15]
0x180032595  lea     rdx, [rbp+150h+var_F0]
0x180032599  mov     rcx, r15
0x18003259c  mov     rax, [rax+10h]
0x1800325a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a5  nop
0x1800325a6  movaps  xmmword ptr [rbp+150h+lpFileName], xmm6
0x1800325aa  movsd   qword ptr [rbp+150h+var_160], xmm7
0x1800325af  mov     r9b, dil
0x1800325b2  lea     r8, [rbp+150h+lpFileName]
0x1800325b6  mov     rdx, rbx
0x1800325b9  mov     rcx, rax
0x1800325bc  call    DesktopAppXVFS__VfsProviderDetails__ForEachHardcodedAppDataRedirectionExclusion__lambda_3470f7b7ea4b1075859e78e14c3d47a5___
0x1800325c1  nop
0x1800325c2  lea     rcx, [rbp+150h+var_F0]; void *
0x1800325c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800325cb  mov     rax, [r15]
0x1800325ce  mov     rcx, r15
0x1800325d1  mov     rax, [rax+20h]
0x1800325d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325da  test    al, al
0x1800325dc  jnz     short loc_180032619
0x1800325de  lea     rax, [rsp+250h+var_208]
0x1800325e3  mov     [rbp+150h+lpFileName], rax
0x1800325e7  lea     rax, [rsp+250h+var_1F8+8]
0x1800325ec  mov     [rbp+150h+lpFileName+8], rax
0x1800325f0  lea     rax, [rsp+250h+var_220]
0x1800325f5  mov     qword ptr [rbp+150h+var_160], rax
0x1800325f9  mov     rax, [r15]
0x1800325fc  mov     rcx, r15
0x1800325ff  mov     rax, [rax+8]
0x180032603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032608  lea     rcx, [rbp+150h+lpFileName]
0x18003260c  mov     qword ptr [rsp+250h+var_230], rcx
0x180032611  mov     r9, rax
0x180032614  call    WriteVirtualization__ExclusionListsInRegistry__Details__ForEachExclusionForPackage_WriteVirtualization__FileSystemExclusion__lambda_771e4c9fe534d61b5a84e07ef6b66b39___
0x180032619  mov     rbx, [r12]
0x18003261d  mov     rdi, [r12+8]
0x180032622  jmp     loc_1800326D6
0x180032627  test    al, 10h
0x180032629  jz      loc_1800324D7
0x18003262f  mov     al, 1
0x180032631  test    al, al
0x180032633  jz      loc_1800324D7
0x180032639  lea     rdx, [rbp+150h+lpFileName]
0x18003263d  lea     rcx, [rbp+150h+String1]
0x180032641  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@NormalizedFileSystemPath@WriteVirtualization@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteVirtualization::NormalizedFileSystemPath::NormalizedFileSystemPath(std::wstring &)
0x180032646  or      r14d, 2
0x18003264a  mov     [rsp+250h+var_21C], r14d
0x18003264f  lea     rcx, [r13+20h]; lpString2
0x180032653  lea     rdx, [rbp+150h+String1]; lpString1
0x180032657  call    ?IsAncestorOf@NormalizedFileSystemPath@WriteVirtualization@@QEBA_NAEBV12@@Z; WriteVirtualization::NormalizedFileSystemPath::IsAncestorOf(WriteVirtualization::NormalizedFileSystemPath const &)
0x18003265c  test    al, al
0x18003265e  jz      loc_1800324D7
0x180032664  mov     bl, 1
0x180032666  jmp     loc_1800324D9
0x18003266b  mov     r8, [rsp+250h+var_208]
0x180032670  mov     rdx, rbx
0x180032673  lea     rcx, [rbp+150h+String1]
0x180032677  call    ??$GetKnownFolderForUser@$00@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEAX@Z; GetKnownFolderForUser<1>(_GUID const &,void *)
0x18003267c  nop
0x18003267d  lea     rdx, [rbx+10h]
0x180032681  lea     rcx, [rbp+150h+var_F0]
0x180032685  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003268a  mov     r8, rax
0x18003268d  lea     rdx, [rbp+150h+String1]
0x180032691  lea     rcx, [rbp+150h+var_B0]
0x180032698  call    ??0AppDataRedirectionExclusion@VfsProviderDetails@DesktopAppXVFS@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z; DesktopAppXVFS::VfsProviderDetails::AppDataRedirectionExclusion::AppDataRedirectionExclusion(std::wstring const &,std::wstring)
0x18003269d  nop
0x18003269e  mov     rdx, rax
0x1800326a1  lea     rcx, [rsp+250h+var_1F8+8]
0x1800326a6  call    _lambda_3470f7b7ea4b1075859e78e14c3d47a5___operator__
0x1800326ab  nop
0x1800326ac  lea     rcx, [rbp+150h+var_90]; void *
0x1800326b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800326b8  lea     rcx, [rbp+150h+var_B0]; void *
0x1800326bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800326c4  mov     [rsp+250h+var_220], 1
0x1800326c9  lea     rcx, [rbp+150h+String1]; void *
0x1800326cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800326d2  add     rbx, 30h ; '0'
0x1800326d6  cmp     rbx, rdi
0x1800326d9  jnz     short loc_18003266B
0x1800326db  xor     r12d, r12d
0x1800326de  cmp     byte ptr [rsp+250h+var_218], r12b
0x1800326e3  jz      loc_180032A8A
0x1800326e9  cmp     [r13+68h], r12
0x1800326ed  jz      loc_180032A8A
0x1800326f3  mov     rax, [r13+40h]
0x1800326f7  mov     [rsp+250h+hObject], rax
0x1800326fc  mov     rdx, [rsp+250h+var_208]
  ... truncated ...
```
