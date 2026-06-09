# StorageReserveHelper::Internal::RecursiveScanDirectory(ushort const *,_STORAGE_RESERVE_ID,StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)

- ea: `0x180036840`
- end: `0x180037007`
- name: `?RecursiveScanDirectory@Internal@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@PEAU_STORAGE_RESERVE_HARDLINK_STATS@12@@Z`
- size: `1991`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *, enum _STORAGE_RESERVE_ID, struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180036840`
- `0x1800537bc`

## callees

- `0x180026e5c`
- `0x180026ef8`
- `0x18002d6c0`
- `0x18002df48`
- `0x180030ad0`
- `0x180036768`
- `0x180036840`
- `0x18003701c`
- `0x18003bc70`
- `0x18003c634`
- `0x18003c870`
- `0x180040b9c`
- `0x180052fb8`
- `0x180052ff4`
- `0x180053024`
- `0x1800533a4`
- `0x180053bac`
- `0x180053cbc`
- `0x180053d94`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036d5a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036d5a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180036920`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180036920`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036f60`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036f60`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180036eee`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180036eee`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180036e7b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180036e7b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180036dec`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180036dec`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180036c05`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180036c05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageReserveHelper::Internal::RecursiveScanDirectory(
        StorageReserveHelper::Internal *this,
        const unsigned __int16 *a2,
        _DWORD *a3,
        struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *a4)
{
  unsigned int v6; // ebx
  int Dependencies; // eax
  signed int LastError; // eax
  LPWIN32_FIND_DATAW v10; // r13
  void *v11; // rbx
  WCHAR *v12; // r15
  void *v13; // r12
  int (*v14)(const unsigned __int16 *, unsigned int, unsigned __int16 **); // rdi
  int v15; // eax
  enum _STORAGE_RESERVE_ID v16; // r8d
  unsigned int v17; // r9d
  unsigned int v18; // edi
  bool v19; // zf
  int v20; // r14d
  int v21; // eax
  int (*v22)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **); // rdi
  const wchar_t *v23; // rdx
  int v24; // eax
  char *v25; // r9
  HANDLE v26; // r12
  unsigned int v27; // edi
  int (*v28)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **); // rdi
  int v29; // eax
  int v30; // r9d
  LPCWCH v31; // r10
  char IsEnabled; // al
  unsigned int *v33; // r8
  unsigned int v34; // r9d
  StorageReserveHelper::Internal *v35; // rcx
  unsigned __int8 FileLinkCnt; // al
  __int64 v37; // rdx
  DWORD v38; // eax
  const char *v39; // r9
  void *v40; // rbx
  enum _STORAGE_RESERVE_ID v41; // r8d
  unsigned int v42; // r9d
  HANDLE FirstFileNameW; // r14
  signed int i; // edx
  enum _STORAGE_RESERVE_ID *v45; // r8
  enum _STORAGE_RESERVE_ID v46; // r8d
  unsigned int v47; // r9d
  BOOL bIgnoreCase; // [rsp+20h] [rbp-59h]
  HANDLE hFindFile; // [rsp+30h] [rbp-49h] BYREF
  LPWIN32_FIND_DATAW lpFindFileData; // [rsp+38h] [rbp-41h] BYREF
  DWORD FileAttributesW; // [rsp+40h] [rbp-39h]
  unsigned __int16 v52[2]; // [rsp+44h] [rbp-35h] BYREF
  unsigned __int16 v53[4]; // [rsp+48h] [rbp-31h] BYREF
  void *Block; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-21h] BYREF
  __int64 v56; // [rsp+60h] [rbp-19h]
  __int64 v57; // [rsp+68h] [rbp-11h]
  DWORD StringLength; // [rsp+70h] [rbp-9h] BYREF
  StorageReserveHelper::Internal *v59; // [rsp+78h] [rbp-1h] BYREF
  int cchCount1[2]; // [rsp+80h] [rbp+7h]
  __int64 v61; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  hFindFile = (HANDLE)-1LL;
  lpFileName = 0;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  *(_QWORD *)cchCount1 = 0;
  v61 = 0;
  *(_DWORD *)v52 = 0;
  if ( !this )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return v6;
  }
  Dependencies = StorageReserveHelper::Internal::LoadDependencies(this);
  v6 = Dependencies;
  if ( Dependencies < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)(unsigned int)Dependencies,
      bIgnoreCase);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return v6;
  }
  FileAttributesW = GetFileAttributesW((LPCWSTR)this);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return v6;
  }
  lpFindFileData = 0;
  if ( !Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&lpFindFileData) )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    Windows::AutoGenericHandleBase<unsigned char *,0,Windows::AutoNewArrayPtr<unsigned char>>::Close(&lpFindFileData);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return v6;
  }
  v10 = lpFindFileData;
  memset_0(lpFindFileData, 0, sizeof(struct _WIN32_FIND_DATAW));
  v11 = 0;
  Block = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl) )
  {
    if ( !Windows::AutoNewArrayPtr<unsigned short>::AllocateArray(&Block) )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
      if ( Block )
        operator delete(Block);
      Windows::AutoGenericHandleBase<unsigned char *,0,Windows::AutoNewArrayPtr<unsigned char>>::Close(&lpFindFileData);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
      return v6;
    }
    v11 = Block;
    v12 = (WCHAR *)Block;
    v13 = Block;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  v14 = StorageReserveHelper::Internal::pfnPathAllocCanonicalize;
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
  *(_QWORD *)cchCount1 = -1;
  v61 = -1;
  v15 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, __int64, StorageReserveHelper::Internal **))v14)(
          this,
          1,
          &v59);
  v18 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)(unsigned int)v15,
      bIgnoreCase);
    if ( v12 )
      operator delete(v11);
    goto LABEL_22;
  }
  v19 = (FileAttributesW & 0x10) == 0;
  v20 = FileAttributesW & 0x10;
  FileAttributesW = v20;
  if ( !v19 )
  {
    v21 = StorageReserveHelper::Internal::SetAreaID(v59, (const unsigned __int16 *)2, v16, v17);
    v18 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
      if ( v12 )
        operator delete(v11);
      goto LABEL_22;
    }
  }
  v22 = StorageReserveHelper::Internal::pfnPathAllocCombine;
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
  v56 = -1;
  v57 = -1;
  v23 = L"*";
  if ( !v20 )
    v23 = &qword_1800649D8;
  v24 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, const wchar_t *, __int64, LPCWSTR *))v22)(
          v59,
          v23,
          1,
          &lpFileName);
  v18 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)(unsigned int)v24,
      bIgnoreCase);
    if ( v12 )
      operator delete(v11);
    goto LABEL_22;
  }
  hFindFile = FindFirstFileW(lpFileName, v10);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v18 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x157,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
            v25);
    if ( v13 )
      operator delete(v11);
    goto LABEL_22;
  }
  v26 = hFindFile;
  v27 = 0;
  do
  {
    if ( v10->cFileName[0] != 46 || v10->cFileName[1] && (v10->cFileName[1] != 46 || v10->cFileName[2]) )
    {
      if ( !v20 )
        goto LABEL_49;
      v28 = StorageReserveHelper::Internal::pfnPathAllocCombine;
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
      v56 = -1;
      v57 = -1;
      v29 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, WCHAR *, __int64, LPCWSTR *))v28)(
              v59,
              v10->cFileName,
              1,
              &lpFileName);
      v27 = 0;
      if ( v29 >= 0 )
      {
        if ( (Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpFileName),
              Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v59),
              v56 != *(_QWORD *)cchCount1)
          && ((Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpFileName),
               Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v59),
               v56 != *(_QWORD *)cchCount1 + 1LL)
           || (Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpFileName),
               *(_WORD *)&v25[2 * v56 - 2] != 92))
          || (Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v59),
              Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v59),
              CompareStringOrdinal(lpFileName, cchCount1[0], v31, v30, 0) != 2) )
        {
LABEL_49:
          if ( (v10->dwFileAttributes & 0x10) != 0 )
          {
            if ( (v10->dwFileAttributes & 0x400) == 0
              || (unsigned __int8)((__int64 (__fastcall *)(_QWORD))StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(v10->dwReserved0) )
            {
              StorageReserveHelper::Internal::RecursiveScanDirectory(
                (StorageReserveHelper::Internal *)lpFileName,
                (const unsigned __int16 *)2,
                (enum _STORAGE_RESERVE_ID)a3,
                (struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)v25);
            }
          }
          else
          {
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl);
            v35 = (StorageReserveHelper::Internal *)lpFileName;
            if ( !IsEnabled )
              goto LABEL_57;
            StringLength = 0;
            FileLinkCnt = StorageReserveHelper::Internal::GetFileLinkCnt(
                            (StorageReserveHelper::Internal *)lpFileName,
                            v52,
                            v33);
            v35 = (StorageReserveHelper::Internal *)lpFileName;
            if ( !FileLinkCnt )
            {
              ++a3[2];
              v37 = 0;
              goto LABEL_58;
            }
            if ( *(_DWORD *)v52 == 1 )
            {
              ++a3[1];
LABEL_57:
              v37 = 2;
LABEL_58:
              StorageReserveHelper::Internal::SetAreaID(
                v35,
                (const unsigned __int16 *)v37,
                (enum _STORAGE_RESERVE_ID)v33,
                v34);
              continue;
            }
            ++a3[3];
            StringLength = 260;
            FirstFileNameW = FindFirstFileNameW((LPCWSTR)v35, 0, &StringLength, v12);
            if ( FirstFileNameW == (HANDLE)-1LL )
            {
              ++a3[4];
              StorageReserveHelper::Internal::SetAreaID((StorageReserveHelper::Internal *)lpFileName, 0, v41, v42);
              v20 = FileAttributesW;
            }
            else
            {
              *(_DWORD *)v53 = 0;
              while ( 1 )
              {
                for ( i = StringLength; i > 0 && v12[i - 1] != 92; --i )
                  ;
                v12[i] = 0;
                if ( IsWCOS() || IsXbox() )
                  break;
                if ( (int)StorageReserveHelper::Internal::QueryAreaID((StorageReserveHelper::Internal *)v12, v53, v45) < 0 )
                  goto LABEL_78;
                if ( *(_DWORD *)v53 != 2 )
                {
                  ++a3[5];
                  goto LABEL_79;
                }
                StringLength = 260;
                if ( !FindNextFileNameW(FirstFileNameW, &StringLength, v12) )
                {
                  v27 = 2;
                  goto LABEL_79;
                }
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEE,
                (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
                (const char *)0x80004001LL,
                bIgnoreCase);
LABEL_78:
              ++a3[4];
LABEL_79:
              if ( GetLastError() != 38 && GetLastError() && GetLastError() != 18 )
              {
                ++a3[4];
                v27 = 0;
              }
              FindClose(FirstFileNameW);
              if ( v27 )
                ++a3[6];
              StorageReserveHelper::Internal::SetAreaID(
                (StorageReserveHelper::Internal *)lpFileName,
                (const unsigned __int16 *)v27,
                v46,
                v47);
              v20 = FileAttributesW;
              v27 = 0;
            }
          }
        }
      }
    }
  }
  while ( FindNextFileW(v26, v10) );
  v38 = GetLastError();
  v40 = Block;
  if ( v38 == 18 )
  {
    if ( Block )
      operator delete(Block);
    Windows::AutoGenericHandleBase<unsigned char *,0,Windows::AutoNewArrayPtr<unsigned char>>::Close(&lpFindFileData);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return 0;
  }
  else
  {
    v18 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x216,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
            v39);
    if ( v40 )
      operator delete(v40);
LABEL_22:
    Windows::AutoGenericHandleBase<unsigned char *,0,Windows::AutoNewArrayPtr<unsigned char>>::Close(&lpFindFileData);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v59);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return v18;
  }
}

```

## disassembly

```asm
0x180036840  mov     [rsp-8+arg_8], rbx
0x180036845  push    rbp
0x180036846  push    rsi
0x180036847  push    rdi
0x180036848  push    r12
0x18003684a  push    r13
0x18003684c  push    r14
0x18003684e  push    r15
0x180036850  lea     rbp, [rsp-27h]
0x180036855  sub     rsp, 0A0h
0x18003685c  mov     rax, cs:__security_cookie
0x180036863  xor     rax, rsp
0x180036866  mov     [rbp+57h+var_40], rax
0x18003686a  mov     rsi, r8
0x18003686d  mov     r14, rcx
0x180036870  mov     [rbp+57h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x180036878  xor     edi, edi
0x18003687a  mov     [rbp+57h+lpFileName], rdi
0x18003687e  mov     [rbp+57h+var_70], rdi
0x180036882  mov     [rbp+57h+var_68], rdi
0x180036886  mov     [rbp+57h+var_58], rdi
0x18003688a  mov     qword ptr [rbp+57h+cchCount1], rdi
0x18003688e  mov     [rbp+57h+var_48], rdi
0x180036892  mov     dword ptr [rbp+57h+var_8C], edi
0x180036895  test    rcx, rcx
0x180036898  jnz     short loc_1800368DB
0x18003689a  mov     rcx, [rbp+5Fh]; this
0x18003689e  mov     ebx, 80070057h
0x1800368a3  mov     r9d, ebx; char *
0x1800368a6  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800368ad  mov     edx, 12Bh; void *
0x1800368b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800368b7  lea     rcx, [rbp+57h+var_58]
0x1800368bb  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800368c0  lea     rcx, [rbp+57h+lpFileName]
0x1800368c4  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800368c9  nop
0x1800368ca  lea     rcx, [rbp+57h+hFindFile]
0x1800368ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800368d3  nop
0x1800368d4  mov     eax, ebx
0x1800368d6  jmp     loc_180036FDF
0x1800368db  call    ?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ; StorageReserveHelper::Internal::LoadDependencies(void)
0x1800368e0  mov     ebx, eax
0x1800368e2  test    eax, eax
0x1800368e4  jns     short loc_18003691D
0x1800368e6  mov     rcx, [rbp+5Fh]; this
0x1800368ea  mov     r9d, eax; char *
0x1800368ed  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800368f4  mov     edx, 12Dh; void *
0x1800368f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800368fe  lea     rcx, [rbp+57h+var_58]
0x180036902  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036907  lea     rcx, [rbp+57h+lpFileName]
0x18003690b  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036910  nop
0x180036911  lea     rcx, [rbp+57h+hFindFile]
0x180036915  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003691a  nop
0x18003691b  jmp     short loc_1800368D4
0x18003691d  mov     rcx, r14; lpFileName
0x180036920  call    cs:__imp_GetFileAttributesW
0x180036927  nop     dword ptr [rax+rax+00h]
0x18003692c  mov     [rbp+57h+var_90], eax
0x18003692f  cmp     eax, 0FFFFFFFFh
0x180036932  jnz     short loc_180036971
0x180036934  call    cs:__imp_GetLastError
0x18003693b  nop     dword ptr [rax+rax+00h]
0x180036940  mov     ebx, eax
0x180036942  test    eax, eax
0x180036944  jle     short loc_18003694F
0x180036946  movzx   ebx, ax
0x180036949  or      ebx, 80070000h
0x18003694f  lea     rcx, [rbp+57h+var_58]
0x180036953  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036958  lea     rcx, [rbp+57h+lpFileName]
0x18003695c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036961  nop
0x180036962  lea     rcx, [rbp+57h+hFindFile]
0x180036966  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003696b  nop
0x18003696c  jmp     loc_1800368D4
0x180036971  mov     [rbp+57h+lpFindFileData], rdi
0x180036975  lea     rcx, [rbp+57h+lpFindFileData]
0x180036979  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x18003697e  test    rax, rax
0x180036981  jnz     short loc_1800369CB
0x180036983  mov     rcx, [rbp+5Fh]; this
0x180036987  mov     ebx, 8007000Eh
0x18003698c  mov     r9d, ebx; char *
0x18003698f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036996  mov     edx, 139h; void *
0x18003699b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369a0  lea     rcx, [rbp+57h+lpFindFileData]
0x1800369a4  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x1800369a9  lea     rcx, [rbp+57h+var_58]
0x1800369ad  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800369b2  lea     rcx, [rbp+57h+lpFileName]
0x1800369b6  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800369bb  nop
0x1800369bc  lea     rcx, [rbp+57h+hFindFile]
0x1800369c0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800369c5  nop
0x1800369c6  jmp     loc_1800368D4
0x1800369cb  mov     r13, [rbp+57h+lpFindFileData]
0x1800369cf  xor     edx, edx; Val
0x1800369d1  mov     r8d, 250h; Size
0x1800369d7  mov     rcx, r13; void *
0x1800369da  call    memset_0
0x1800369df  mov     rbx, rdi
0x1800369e2  mov     [rbp+57h+Block], rbx
0x1800369e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix> `wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl(void)'::`2'::impl
0x1800369ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(void)
0x1800369f2  test    al, al
0x1800369f4  jz      short loc_180036A66
0x1800369f6  lea     rcx, [rbp+57h+Block]
0x1800369fa  call    ?AllocateArray@?$AutoNewArrayPtr@G@Windows@@QEAAPEAG_K@Z; Windows::AutoNewArrayPtr<ushort>::AllocateArray(unsigned __int64)
0x1800369ff  test    rax, rax
0x180036a02  jnz     short loc_180036A5A
0x180036a04  mov     rcx, [rbp+5Fh]; this
0x180036a08  mov     ebx, 8007000Eh
0x180036a0d  mov     r9d, ebx; char *
0x180036a10  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036a17  mov     edx, 143h; void *
0x180036a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a21  mov     rcx, [rbp+57h+Block]; Block
0x180036a25  test    rcx, rcx
0x180036a28  jz      short loc_180036A2F
0x180036a2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036a2f  lea     rcx, [rbp+57h+lpFindFileData]
0x180036a33  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036a38  lea     rcx, [rbp+57h+var_58]
0x180036a3c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036a41  lea     rcx, [rbp+57h+lpFileName]
0x180036a45  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036a4a  nop
0x180036a4b  lea     rcx, [rbp+57h+hFindFile]
0x180036a4f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036a54  nop
0x180036a55  jmp     loc_1800368D4
0x180036a5a  mov     rbx, [rbp+57h+Block]
0x180036a5e  mov     r15, rbx
0x180036a61  mov     r12, rbx
0x180036a64  jmp     short loc_180036A6C
0x180036a66  mov     r15, rdi
0x180036a69  mov     r12, rdi
0x180036a6c  mov     rdi, cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x180036a73  lea     rcx, [rbp+57h+var_58]
0x180036a77  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036a7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036a80  mov     qword ptr [rbp+57h+cchCount1], rax
0x180036a84  mov     [rbp+57h+var_48], rax
0x180036a88  lea     r8, [rbp+57h+var_58]
0x180036a8c  lea     edx, [rax+2]
0x180036a8f  mov     rcx, r14
0x180036a92  mov     rax, rdi
0x180036a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a9a  mov     edi, eax
0x180036a9c  test    eax, eax
0x180036a9e  jns     short loc_180036AF2
0x180036aa0  mov     rcx, [rbp+5Fh]; this
0x180036aa4  mov     r9d, eax; char *
0x180036aa7  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036aae  mov     edx, 147h; void *
0x180036ab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036ab8  test    r15, r15
0x180036abb  jz      short loc_180036AC5
0x180036abd  mov     rcx, rbx; Block
0x180036ac0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036ac5  lea     rcx, [rbp+57h+lpFindFileData]
0x180036ac9  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036ace  lea     rcx, [rbp+57h+var_58]
0x180036ad2  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036ad7  lea     rcx, [rbp+57h+lpFileName]
0x180036adb  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036ae0  nop
0x180036ae1  lea     rcx, [rbp+57h+hFindFile]
0x180036ae5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036aea  nop
0x180036aeb  mov     eax, edi
0x180036aed  jmp     loc_180036FDF
0x180036af2  mov     r14d, [rbp+57h+var_90]
0x180036af6  and     r14d, 10h
0x180036afa  mov     [rbp+57h+var_90], r14d
0x180036afe  jz      short loc_180036B61
0x180036b00  mov     edx, 2; unsigned __int16 *
0x180036b05  mov     rcx, [rbp+57h+var_58]; this
0x180036b09  call    ?SetAreaID@Internal@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@K@Z; StorageReserveHelper::Internal::SetAreaID(ushort const *,_STORAGE_RESERVE_ID,ulong)
0x180036b0e  mov     edi, eax
0x180036b10  test    eax, eax
0x180036b12  jns     short loc_180036B61
0x180036b14  mov     rcx, [rbp+5Fh]; this
0x180036b18  mov     r9d, eax; char *
0x180036b1b  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036b22  mov     edx, 151h; void *
0x180036b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b2c  test    r15, r15
0x180036b2f  jz      short loc_180036B39
0x180036b31  mov     rcx, rbx; Block
0x180036b34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036b39  lea     rcx, [rbp+57h+lpFindFileData]
0x180036b3d  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036b42  lea     rcx, [rbp+57h+var_58]
0x180036b46  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036b4b  lea     rcx, [rbp+57h+lpFileName]
0x180036b4f  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036b54  nop
0x180036b55  lea     rcx, [rbp+57h+hFindFile]
0x180036b59  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036b5e  nop
0x180036b5f  jmp     short loc_180036AEB
0x180036b61  mov     rdi, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x180036b68  lea     rcx, [rbp+57h+lpFileName]
0x180036b6c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036b71  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036b75  mov     [rbp+57h+var_70], rax
0x180036b79  mov     [rbp+57h+var_68], rax
0x180036b7d  lea     rax, qword_1800649D8
0x180036b84  lea     rdx, asc_18006F3F0; "*"
0x180036b8b  test    r14d, r14d
0x180036b8e  cmovz   rdx, rax
0x180036b92  lea     r9, [rbp+57h+lpFileName]
0x180036b96  mov     r8d, 1
0x180036b9c  mov     rcx, [rbp+57h+var_58]
0x180036ba0  mov     rax, rdi
0x180036ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ba8  mov     edi, eax
0x180036baa  test    eax, eax
0x180036bac  jns     short loc_180036BFE
0x180036bae  mov     rcx, [rbp+5Fh]; this
0x180036bb2  mov     r9d, eax; char *
0x180036bb5  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036bbc  mov     edx, 154h; void *
0x180036bc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036bc6  test    r15, r15
0x180036bc9  jz      short loc_180036BD3
0x180036bcb  mov     rcx, rbx; Block
0x180036bce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036bd3  lea     rcx, [rbp+57h+lpFindFileData]
0x180036bd7  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036bdc  lea     rcx, [rbp+57h+var_58]
0x180036be0  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036be5  lea     rcx, [rbp+57h+lpFileName]
0x180036be9  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036bee  nop
0x180036bef  lea     rcx, [rbp+57h+hFindFile]
0x180036bf3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036bf8  nop
0x180036bf9  jmp     loc_180036AEB
0x180036bfe  mov     rdx, r13; lpFindFileData
0x180036c01  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180036c05  call    cs:__imp_FindFirstFileW
0x180036c0c  nop     dword ptr [rax+rax+00h]
0x180036c11  mov     [rbp+57h+hFindFile], rax
0x180036c15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036c19  jnz     short loc_180036C6A
0x180036c1b  mov     rcx, [rbp+5Fh]; this
0x180036c1f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036c26  mov     edx, 157h; void *
0x180036c2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036c30  mov     edi, eax
0x180036c32  test    r12, r12
0x180036c35  jz      short loc_180036C3F
0x180036c37  mov     rcx, rbx; Block
0x180036c3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036c3f  lea     rcx, [rbp+57h+lpFindFileData]
0x180036c43  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036c48  lea     rcx, [rbp+57h+var_58]
0x180036c4c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036c51  lea     rcx, [rbp+57h+lpFileName]
0x180036c55  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036c5a  nop
0x180036c5b  lea     rcx, [rbp+57h+hFindFile]
0x180036c5f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036c64  nop
0x180036c65  jmp     loc_180036AEB
0x180036c6a  mov     r12, [rbp+57h+hFindFile]
0x180036c6e  xor     edi, edi
0x180036c70  cmp     word ptr [r13+2Ch], 2Eh ; '.'
0x180036c76  jnz     short loc_180036C96
0x180036c78  cmp     [r13+2Eh], di
0x180036c7d  jz      loc_180036DE6
0x180036c83  cmp     word ptr [r13+2Eh], 2Eh ; '.'
0x180036c89  jnz     short loc_180036C96
0x180036c8b  cmp     [r13+30h], di
0x180036c90  jz      loc_180036DE6
0x180036c96  test    r14d, r14d
0x180036c99  jz      loc_180036D6B
0x180036c9f  mov     rdi, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x180036ca6  lea     rcx, [rbp+57h+lpFileName]
0x180036caa  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036caf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036cb3  mov     [rbp+57h+var_70], rax
0x180036cb7  mov     [rbp+57h+var_68], rax
0x180036cbb  lea     r9, [rbp+57h+lpFileName]
0x180036cbf  lea     r8d, [rax+2]
0x180036cc3  lea     rdx, [r13+2Ch]
0x180036cc7  mov     rcx, [rbp+57h+var_58]
0x180036ccb  mov     rax, rdi
0x180036cce  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
