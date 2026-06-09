# StorageReserveHelper::Internal::RecursiveScanDirectory(ushort const *,_STORAGE_RESERVE_ID,StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)

- ea: `0x1800361d4`
- end: `0x180036925`
- name: `?RecursiveScanDirectory@Internal@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@PEAU_STORAGE_RESERVE_HARDLINK_STATS@12@@Z`
- size: `1873`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *this, const unsigned __int16 *, _DWORD *, struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800361d4`
- `0x1800507c8`

## callees

- `0x1800245c0`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002f920`
- `0x1800361d4`
- `0x180036938`
- `0x18003a730`
- `0x18003b0f4`
- `0x18003b310`
- `0x18003f3fc`
- `0x18004fbb8`
- `0x18004fbe8`
- `0x18004fc18`
- `0x1800505d4`
- `0x180050b68`
- `0x180050cac`
- `0x180050d70`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003685d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003685d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036872`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800366dc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800366dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800362b4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800362b4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036885`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036885`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180036846`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180036846`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x1800367eb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x1800367eb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180036768`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180036768`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003658d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003658d`

## pseudocode

```c
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
  enum _STORAGE_RESERVE_ID *v41; // r8
  unsigned int v42; // r9d
  HANDLE FirstFileNameW; // r14
  signed int i; // edx
  enum _STORAGE_RESERVE_ID v45; // r8d
  unsigned int v46; // r9d
  BOOL bIgnoreCase; // [rsp+20h] [rbp-59h]
  HANDLE hFindFile; // [rsp+30h] [rbp-49h] BYREF
  LPWIN32_FIND_DATAW lpFindFileData; // [rsp+38h] [rbp-41h] BYREF
  DWORD FileAttributesW; // [rsp+40h] [rbp-39h]
  unsigned __int16 v51[2]; // [rsp+44h] [rbp-35h] BYREF
  unsigned __int16 v52[4]; // [rsp+48h] [rbp-31h] BYREF
  void *Block; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-21h] BYREF
  __int64 v55; // [rsp+60h] [rbp-19h]
  __int64 v56; // [rsp+68h] [rbp-11h]
  DWORD StringLength; // [rsp+70h] [rbp-9h] BYREF
  StorageReserveHelper::Internal *v58; // [rsp+78h] [rbp-1h] BYREF
  int cchCount1[2]; // [rsp+80h] [rbp+7h]
  __int64 v60; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  hFindFile = (HANDLE)-1LL;
  lpFileName = 0;
  v55 = 0;
  v56 = 0;
  v58 = 0;
  *(_QWORD *)cchCount1 = 0;
  v60 = 0;
  *(_DWORD *)v51 = 0;
  if ( !this )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
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
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
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
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
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
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
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
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
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
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
  *(_QWORD *)cchCount1 = -1;
  v60 = -1;
  v15 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, __int64, StorageReserveHelper::Internal **))v14)(
          this,
          1,
          &v58);
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
    v21 = StorageReserveHelper::Internal::SetAreaID(v58, (const unsigned __int16 *)2, v16, v17);
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
  v55 = -1;
  v56 = -1;
  v23 = L"*";
  if ( !v20 )
    v23 = &qword_180061CC0;
  v24 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, const wchar_t *, __int64, LPCWSTR *))v22)(
          v58,
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
      v55 = -1;
      v56 = -1;
      v29 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, WCHAR *, __int64, LPCWSTR *))v28)(
              v58,
              v10->cFileName,
              1,
              &lpFileName);
      v27 = 0;
      if ( v29 >= 0 )
      {
        if ( (Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpFileName),
              Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v58),
              v55 != *(_QWORD *)cchCount1)
          && ((Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpFileName),
               Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v58),
               v55 != *(_QWORD *)cchCount1 + 1LL)
           || (Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpFileName),
               *(_WORD *)&v25[2 * v55 - 2] != 92))
          || (Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v58),
              Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v58),
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
                            v51,
                            v33);
            v35 = (StorageReserveHelper::Internal *)lpFileName;
            if ( !FileLinkCnt )
            {
              ++a3[2];
              v37 = 0;
              goto LABEL_58;
            }
            if ( *(_DWORD *)v51 == 1 )
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
              StorageReserveHelper::Internal::SetAreaID(
                (StorageReserveHelper::Internal *)lpFileName,
                0,
                (enum _STORAGE_RESERVE_ID)v41,
                v42);
              v20 = FileAttributesW;
            }
            else
            {
              *(_DWORD *)v52 = 0;
              while ( 1 )
              {
                for ( i = StringLength; i > 0 && v12[i - 1] != 92; --i )
                  ;
                v12[i] = 0;
                if ( (int)StorageReserveHelper::QueryStorageReserveID((StorageReserveHelper *)v12, v52, v41) < 0 )
                  break;
                if ( *(_DWORD *)v52 != 2 )
                {
                  ++a3[5];
                  goto LABEL_76;
                }
                StringLength = 260;
                if ( !FindNextFileNameW(FirstFileNameW, &StringLength, v12) )
                {
                  v27 = 2;
                  goto LABEL_76;
                }
              }
              ++a3[4];
LABEL_76:
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
                v45,
                v46);
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
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
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
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&v58);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    return v18;
  }
}

```

## disassembly

```asm
0x1800361d4  mov     [rsp-8+arg_8], rbx
0x1800361d9  push    rbp
0x1800361da  push    rsi
0x1800361db  push    rdi
0x1800361dc  push    r12
0x1800361de  push    r13
0x1800361e0  push    r14
0x1800361e2  push    r15
0x1800361e4  lea     rbp, [rsp-27h]
0x1800361e9  sub     rsp, 0A0h
0x1800361f0  mov     rax, cs:__security_cookie
0x1800361f7  xor     rax, rsp
0x1800361fa  mov     [rbp+57h+var_40], rax
0x1800361fe  mov     rsi, r8
0x180036201  mov     r14, rcx
0x180036204  mov     [rbp+57h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18003620c  xor     edi, edi
0x18003620e  mov     [rbp+57h+lpFileName], rdi
0x180036212  mov     [rbp+57h+var_70], rdi
0x180036216  mov     [rbp+57h+var_68], rdi
0x18003621a  mov     [rbp+57h+var_58], rdi
0x18003621e  mov     qword ptr [rbp+57h+cchCount1], rdi
0x180036222  mov     [rbp+57h+var_48], rdi
0x180036226  mov     dword ptr [rbp+57h+var_8C], edi
0x180036229  test    rcx, rcx
0x18003622c  jnz     short loc_18003626F
0x18003622e  mov     rcx, [rbp+5Fh]; this
0x180036232  mov     ebx, 80070057h
0x180036237  mov     r9d, ebx; char *
0x18003623a  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036241  mov     edx, 12Bh; void *
0x180036246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003624b  lea     rcx, [rbp+57h+var_58]
0x18003624f  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036254  lea     rcx, [rbp+57h+lpFileName]
0x180036258  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003625d  nop
0x18003625e  lea     rcx, [rbp+57h+hFindFile]
0x180036262  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036267  nop
0x180036268  mov     eax, ebx
0x18003626a  jmp     loc_1800368FE
0x18003626f  call    ?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ; StorageReserveHelper::Internal::LoadDependencies(void)
0x180036274  mov     ebx, eax
0x180036276  test    eax, eax
0x180036278  jns     short loc_1800362B1
0x18003627a  mov     rcx, [rbp+5Fh]; this
0x18003627e  mov     r9d, eax; char *
0x180036281  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036288  mov     edx, 12Dh; void *
0x18003628d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036292  lea     rcx, [rbp+57h+var_58]
0x180036296  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003629b  lea     rcx, [rbp+57h+lpFileName]
0x18003629f  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800362a4  nop
0x1800362a5  lea     rcx, [rbp+57h+hFindFile]
0x1800362a9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800362ae  nop
0x1800362af  jmp     short loc_180036268
0x1800362b1  mov     rcx, r14; lpFileName
0x1800362b4  call    cs:__imp_GetFileAttributesW
0x1800362ba  mov     [rbp+57h+var_90], eax
0x1800362bd  cmp     eax, 0FFFFFFFFh
0x1800362c0  jnz     short loc_1800362F9
0x1800362c2  call    cs:__imp_GetLastError
0x1800362c8  mov     ebx, eax
0x1800362ca  test    eax, eax
0x1800362cc  jle     short loc_1800362D7
0x1800362ce  movzx   ebx, ax
0x1800362d1  or      ebx, 80070000h
0x1800362d7  lea     rcx, [rbp+57h+var_58]
0x1800362db  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800362e0  lea     rcx, [rbp+57h+lpFileName]
0x1800362e4  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800362e9  nop
0x1800362ea  lea     rcx, [rbp+57h+hFindFile]
0x1800362ee  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800362f3  nop
0x1800362f4  jmp     loc_180036268
0x1800362f9  mov     [rbp+57h+lpFindFileData], rdi
0x1800362fd  lea     rcx, [rbp+57h+lpFindFileData]
0x180036301  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x180036306  test    rax, rax
0x180036309  jnz     short loc_180036353
0x18003630b  mov     rcx, [rbp+5Fh]; this
0x18003630f  mov     ebx, 8007000Eh
0x180036314  mov     r9d, ebx; char *
0x180036317  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18003631e  mov     edx, 139h; void *
0x180036323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036328  lea     rcx, [rbp+57h+lpFindFileData]
0x18003632c  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036331  lea     rcx, [rbp+57h+var_58]
0x180036335  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003633a  lea     rcx, [rbp+57h+lpFileName]
0x18003633e  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036343  nop
0x180036344  lea     rcx, [rbp+57h+hFindFile]
0x180036348  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003634d  nop
0x18003634e  jmp     loc_180036268
0x180036353  mov     r13, [rbp+57h+lpFindFileData]
0x180036357  xor     edx, edx; Val
0x180036359  mov     r8d, 250h; Size
0x18003635f  mov     rcx, r13; void *
0x180036362  call    memset_0
0x180036367  mov     rbx, rdi
0x18003636a  mov     [rbp+57h+Block], rbx
0x18003636e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix> `wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl(void)'::`2'::impl
0x180036375  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(void)
0x18003637a  test    al, al
0x18003637c  jz      short loc_1800363EE
0x18003637e  lea     rcx, [rbp+57h+Block]
0x180036382  call    ?AllocateArray@?$AutoNewArrayPtr@G@Windows@@QEAAPEAG_K@Z; Windows::AutoNewArrayPtr<ushort>::AllocateArray(unsigned __int64)
0x180036387  test    rax, rax
0x18003638a  jnz     short loc_1800363E2
0x18003638c  mov     rcx, [rbp+5Fh]; this
0x180036390  mov     ebx, 8007000Eh
0x180036395  mov     r9d, ebx; char *
0x180036398  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18003639f  mov     edx, 143h; void *
0x1800363a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800363a9  mov     rcx, [rbp+57h+Block]; Block
0x1800363ad  test    rcx, rcx
0x1800363b0  jz      short loc_1800363B7
0x1800363b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800363b7  lea     rcx, [rbp+57h+lpFindFileData]
0x1800363bb  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x1800363c0  lea     rcx, [rbp+57h+var_58]
0x1800363c4  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800363c9  lea     rcx, [rbp+57h+lpFileName]
0x1800363cd  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800363d2  nop
0x1800363d3  lea     rcx, [rbp+57h+hFindFile]
0x1800363d7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800363dc  nop
0x1800363dd  jmp     loc_180036268
0x1800363e2  mov     rbx, [rbp+57h+Block]
0x1800363e6  mov     r15, rbx
0x1800363e9  mov     r12, rbx
0x1800363ec  jmp     short loc_1800363F4
0x1800363ee  mov     r15, rdi
0x1800363f1  mov     r12, rdi
0x1800363f4  mov     rdi, cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x1800363fb  lea     rcx, [rbp+57h+var_58]
0x1800363ff  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036404  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036408  mov     qword ptr [rbp+57h+cchCount1], rax
0x18003640c  mov     [rbp+57h+var_48], rax
0x180036410  lea     r8, [rbp+57h+var_58]
0x180036414  lea     edx, [rax+2]
0x180036417  mov     rcx, r14
0x18003641a  mov     rax, rdi
0x18003641d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036422  mov     edi, eax
0x180036424  test    eax, eax
0x180036426  jns     short loc_18003647A
0x180036428  mov     rcx, [rbp+5Fh]; this
0x18003642c  mov     r9d, eax; char *
0x18003642f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036436  mov     edx, 147h; void *
0x18003643b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036440  test    r15, r15
0x180036443  jz      short loc_18003644D
0x180036445  mov     rcx, rbx; Block
0x180036448  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003644d  lea     rcx, [rbp+57h+lpFindFileData]
0x180036451  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036456  lea     rcx, [rbp+57h+var_58]
0x18003645a  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003645f  lea     rcx, [rbp+57h+lpFileName]
0x180036463  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036468  nop
0x180036469  lea     rcx, [rbp+57h+hFindFile]
0x18003646d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036472  nop
0x180036473  mov     eax, edi
0x180036475  jmp     loc_1800368FE
0x18003647a  mov     r14d, [rbp+57h+var_90]
0x18003647e  and     r14d, 10h
0x180036482  mov     [rbp+57h+var_90], r14d
0x180036486  jz      short loc_1800364E9
0x180036488  mov     edx, 2; unsigned __int16 *
0x18003648d  mov     rcx, [rbp+57h+var_58]; this
0x180036491  call    ?SetAreaID@Internal@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@K@Z; StorageReserveHelper::Internal::SetAreaID(ushort const *,_STORAGE_RESERVE_ID,ulong)
0x180036496  mov     edi, eax
0x180036498  test    eax, eax
0x18003649a  jns     short loc_1800364E9
0x18003649c  mov     rcx, [rbp+5Fh]; this
0x1800364a0  mov     r9d, eax; char *
0x1800364a3  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800364aa  mov     edx, 151h; void *
0x1800364af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800364b4  test    r15, r15
0x1800364b7  jz      short loc_1800364C1
0x1800364b9  mov     rcx, rbx; Block
0x1800364bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800364c1  lea     rcx, [rbp+57h+lpFindFileData]
0x1800364c5  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x1800364ca  lea     rcx, [rbp+57h+var_58]
0x1800364ce  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800364d3  lea     rcx, [rbp+57h+lpFileName]
0x1800364d7  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800364dc  nop
0x1800364dd  lea     rcx, [rbp+57h+hFindFile]
0x1800364e1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800364e6  nop
0x1800364e7  jmp     short loc_180036473
0x1800364e9  mov     rdi, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x1800364f0  lea     rcx, [rbp+57h+lpFileName]
0x1800364f4  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800364f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800364fd  mov     [rbp+57h+var_70], rax
0x180036501  mov     [rbp+57h+var_68], rax
0x180036505  lea     rax, qword_180061CC0
0x18003650c  lea     rdx, asc_18006C364; "*"
0x180036513  test    r14d, r14d
0x180036516  cmovz   rdx, rax
0x18003651a  lea     r9, [rbp+57h+lpFileName]
0x18003651e  mov     r8d, 1
0x180036524  mov     rcx, [rbp+57h+var_58]
0x180036528  mov     rax, rdi
0x18003652b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036530  mov     edi, eax
0x180036532  test    eax, eax
0x180036534  jns     short loc_180036586
0x180036536  mov     rcx, [rbp+5Fh]; this
0x18003653a  mov     r9d, eax; char *
0x18003653d  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180036544  mov     edx, 154h; void *
0x180036549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003654e  test    r15, r15
0x180036551  jz      short loc_18003655B
0x180036553  mov     rcx, rbx; Block
0x180036556  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003655b  lea     rcx, [rbp+57h+lpFindFileData]
0x18003655f  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x180036564  lea     rcx, [rbp+57h+var_58]
0x180036568  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003656d  lea     rcx, [rbp+57h+lpFileName]
0x180036571  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036576  nop
0x180036577  lea     rcx, [rbp+57h+hFindFile]
0x18003657b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036580  nop
0x180036581  jmp     loc_180036473
0x180036586  mov     rdx, r13; lpFindFileData
0x180036589  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18003658d  call    cs:__imp_FindFirstFileW
0x180036593  mov     [rbp+57h+hFindFile], rax
0x180036597  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003659b  jnz     short loc_1800365EC
0x18003659d  mov     rcx, [rbp+5Fh]; this
0x1800365a1  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800365a8  mov     edx, 157h; void *
0x1800365ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800365b2  mov     edi, eax
0x1800365b4  test    r12, r12
0x1800365b7  jz      short loc_1800365C1
0x1800365b9  mov     rcx, rbx; Block
0x1800365bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800365c1  lea     rcx, [rbp+57h+lpFindFileData]
0x1800365c5  call    ?Close@?$AutoGenericHandleBase@PEAE$0A@V?$AutoNewArrayPtr@E@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<uchar *,0,Windows::AutoNewArrayPtr<uchar>>::Close(void)
0x1800365ca  lea     rcx, [rbp+57h+var_58]
0x1800365ce  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800365d3  lea     rcx, [rbp+57h+lpFileName]
0x1800365d7  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800365dc  nop
0x1800365dd  lea     rcx, [rbp+57h+hFindFile]
0x1800365e1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800365e6  nop
0x1800365e7  jmp     loc_180036473
0x1800365ec  mov     r12, [rbp+57h+hFindFile]
0x1800365f0  xor     edi, edi
0x1800365f2  cmp     word ptr [r13+2Ch], 2Eh ; '.'
0x1800365f8  jnz     short loc_180036618
0x1800365fa  cmp     [r13+2Eh], di
0x1800365ff  jz      loc_180036762
0x180036605  cmp     word ptr [r13+2Eh], 2Eh ; '.'
0x18003660b  jnz     short loc_180036618
0x18003660d  cmp     [r13+30h], di
0x180036612  jz      loc_180036762
0x180036618  test    r14d, r14d
0x18003661b  jz      loc_1800366E7
0x180036621  mov     rdi, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x180036628  lea     rcx, [rbp+57h+lpFileName]
0x18003662c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180036631  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036635  mov     [rbp+57h+var_70], rax
0x180036639  mov     [rbp+57h+var_68], rax
0x18003663d  lea     r9, [rbp+57h+lpFileName]
0x180036641  lea     r8d, [rax+2]
0x180036645  lea     rdx, [r13+2Ch]
0x180036649  mov     rcx, [rbp+57h+var_58]
0x18003664d  mov     rax, rdi
0x180036650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036655  xor     edi, edi
0x180036657  test    eax, eax
0x180036659  js      loc_180036762
  ... truncated ...
```
