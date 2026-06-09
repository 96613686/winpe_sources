# CloudDataRestoreOobe::CreateUserPath(HSTRING__ *,CloudExperienceHostAPI::RestoreAssetTypeOobe,HSTRING__ * *)

- ea: `0x180017f60`
- end: `0x18001825e`
- name: `?CreateUserPath@CloudDataRestoreOobe@@UEAAJPEAUHSTRING__@@W4RestoreAssetTypeOobe@CloudExperienceHostAPI@@PEAPEAU2@@Z`
- size: `766`
- prototype: `int __high(HSTRING, enum CloudExperienceHostAPI::RestoreAssetTypeOobe, HSTRING *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004eb4`
- `0x18000851c`
- `0x180009814`
- `0x18000ac54`
- `0x180014200`
- `0x18001430c`
- `0x180015544`
- `0x1800162b8`
- `0x180016e8c`
- `0x180016ee0`
- `0x180017140`
- `0x18001763c`
- `0x180017c4c`
- `0x180017dd4`
- `0x180017f60`
- `0x180018530`
- `0x1800187b0`
- `0x180019374`
- `0x180019608`
- `0x1800196b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800180cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800180cf`

## string_xrefs

- `0x180018221`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001820d`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x180018236`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x18001824b`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x18001812b`: `FilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CloudDataRestoreOobe::CreateUserPath(__int64 a1, HSTRING a2, unsigned __int64 a3, HSTRING *a4)
{
  __int64 cotaskmem_string; // rax
  const unsigned __int16 *v7; // rdx
  int DirectoryDeepNoThrow; // eax
  __int64 FolderFromPathAsync; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // r8
  __int64 v14; // rax
  const unsigned __int16 *v15; // rdi
  __int64 v16; // rdx
  const unsigned __int16 **v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  HRESULT String; // eax
  const char *v21; // r9
  __int64 result; // rax
  const char *v23; // r9
  int v24; // r8d
  int v25; // [rsp+20h] [rbp-A8h]
  char *v26; // [rsp+28h] [rbp-A0h]
  _BYTE v27[8]; // [rsp+30h] [rbp-98h] BYREF
  PCWSTR StringRawBuffer; // [rsp+38h] [rbp-90h] BYREF
  unsigned __int16 *v29; // [rsp+40h] [rbp-88h] BYREF
  wil *v30; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v32[8]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v33[8]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v34[32]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v35[64]; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  int v37; // [rsp+E0h] [rbp+18h] BYREF
  PCNZWCH sourceString; // [rsp+E8h] [rbp+20h] BYREF

  try
  {
    *a4 = 0;
    v29 = 0;
    if ( (_DWORD)a3 )
    {
      if ( (_DWORD)a3 != 1 )
      {
        v23 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
        LODWORD(v26) = v24;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x44,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
          v23,
          (int)"Unexpected restoreAssetType [%d]",
          v26);
      }
      cotaskmem_string = wil::make_cotaskmem_string((wil *)v27, L"LockScreen", a3);
    }
    else
    {
      cotaskmem_string = wil::make_cotaskmem_string((wil *)v27, L"Wallpaper", a3);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v29,
      cotaskmem_string);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v27);
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
      &v30,
      L"%LocalAppData%\\Microsoft\\Windows\\CloudStoreAssets");
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((const WCHAR *)v30, v7);
    if ( DirectoryDeepNoThrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)DirectoryDeepNoThrow,
        v25);
    winrt::param::hstring::hstring((winrt::param::hstring *)v34, (const unsigned __int16 *const)v30);
    FolderFromPathAsync = winrt::Windows::Storage::StorageFolder::GetFolderFromPathAsync((const struct winrt::param::hstring *)v27);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(
      FolderFromPathAsync,
      v33);
    winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v27);
    v37 = 3;
    v10 = v29;
    winrt::param::hstring::hstring((winrt::param::hstring *)v35, v29);
    v11 = winrt::impl::consume_Windows_Storage_IStorageFolder<winrt::Windows::Storage::IStorageFolder>::CreateFolderAsync(
            v33,
            &StringRawBuffer,
            v35,
            &v37);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(
      v11,
      v32);
    winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&StringRawBuffer);
    v12 = *(_QWORD *)winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFolder>::Path(
                       v32,
                       v27);
    if ( v12 )
      v13 = *(const WCHAR **)(v12 + 16);
    else
      v13 = &::sourceString;
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &sourceString,
      L"%ws\\",
      v13);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v27);
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v14 = wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &,unsigned short const *>(
            &v31,
            &sourceString,
            &StringRawBuffer);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &sourceString,
      v14);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
    v15 = sourceString;
    v31 = v10;
    v17 = (const unsigned __int16 **)wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const (&)[56],unsigned short *>(
                                       &StringRawBuffer,
                                       v16,
                                       &v31);
    v18 = SHRegSetString(HKEY_CURRENT_USER, *v17, L"FilePath", v15);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
        (const char *)(unsigned int)v18,
        v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringRawBuffer);
    if ( sourceString )
    {
      v19 = -1;
      do
        ++v19;
      while ( sourceString[v19] );
      String = WindowsCreateString(sourceString, v19, a4);
      if ( String < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
          (const char *)(unsigned int)String,
          v25);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
    winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v32);
    winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v33);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5C,
                           (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x180017f60  mov     [rsp+arg_0], rbx
0x180017f65  push    rsi
0x180017f66  push    rdi
0x180017f67  push    r14
0x180017f69  sub     rsp, 0B0h
0x180017f70  mov     rsi, r9
0x180017f73  mov     rdi, rdx
0x180017f76  xor     r14d, r14d
0x180017f79  mov     [r9], r14
0x180017f7c  mov     [rsp+0C8h+var_88], r14
0x180017f81  test    r8d, r8d
0x180017f84  jz      short loc_180017FA3
0x180017f86  cmp     r8d, 1
0x180017f8a  jnz     loc_1800181E7
0x180017f90  lea     rdx, aLockscreen; "LockScreen"
0x180017f97  lea     rcx, [rsp+0C8h+var_98]; this
0x180017f9c  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x180017fa1  jmp     short loc_180017FB4
0x180017fa3  lea     rdx, aWallpaper; "Wallpaper"
0x180017faa  lea     rcx, [rsp+0C8h+var_98]; this
0x180017faf  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x180017fb4  mov     rdx, rax
0x180017fb7  lea     rcx, [rsp+0C8h+var_88]
0x180017fbc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180017fc1  lea     rcx, [rsp+0C8h+var_98]
0x180017fc6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017fcb  lea     rdx, aLocalappdataMi; "%LocalAppData%\\Microsoft\\Windows\\Clo"...
0x180017fd2  lea     rcx, [rsp+0C8h+var_80]
0x180017fd7  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180017fdc  nop
0x180017fdd  mov     rcx, [rsp+0C8h+var_80]; this
0x180017fe2  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x180017fe7  mov     rcx, [rsp+0C8h]; this
0x180017fef  test    eax, eax
0x180017ff1  js      loc_18001821E
0x180017ff7  mov     rdx, [rsp+0C8h+var_80]; unsigned __int16 *
0x180017ffc  lea     rcx, [rsp+0C8h+var_60]; this
0x180018001  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180018006  lea     rdx, [rsp+0C8h+var_60]
0x18001800b  lea     rcx, [rsp+0C8h+var_98]; struct winrt::param::hstring *
0x180018010  call    ?GetFolderFromPathAsync@StorageFolder@Storage@Windows@winrt@@SA@AEBUhstring@param@4@@Z; winrt::Windows::Storage::StorageFolder::GetFolderFromPathAsync(winrt::param::hstring const &)
0x180018015  nop
0x180018016  lea     rdx, [rsp+0C8h+var_68]
0x18001801b  mov     rcx, rax
0x18001801e  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFolder@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFolder@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(void)
0x180018023  nop
0x180018024  lea     rcx, [rsp+0C8h+var_98]; this
0x180018029  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18001802e  mov     [rsp+0C8h+arg_10], 3
0x180018039  mov     rbx, [rsp+0C8h+var_88]
0x18001803e  mov     rdx, rbx; unsigned __int16 *
0x180018041  lea     rcx, [rsp+0C8h+var_40]; this
0x180018049  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001804e  lea     r9, [rsp+0C8h+arg_10]
0x180018056  lea     r8, [rsp+0C8h+var_40]
0x18001805e  lea     rdx, [rsp+0C8h+var_90]
0x180018063  lea     rcx, [rsp+0C8h+var_68]
0x180018068  call    ?CreateFolderAsync@?$consume_Windows_Storage_IStorageFolder@UIStorageFolder@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBW4CreationCollisionOption@Storage@Windows@3@@Z; winrt::impl::consume_Windows_Storage_IStorageFolder<winrt::Windows::Storage::IStorageFolder>::CreateFolderAsync(winrt::param::hstring const &,winrt::Windows::Storage::CreationCollisionOption const &)
0x18001806d  nop
0x18001806e  lea     rdx, [rsp+0C8h+var_70]
0x180018073  mov     rcx, rax
0x180018076  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFolder@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFolder@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFolder>,winrt::Windows::Storage::StorageFolder>::get(void)
0x18001807b  nop
0x18001807c  lea     rcx, [rsp+0C8h+var_90]; this
0x180018081  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x180018086  lea     rdx, [rsp+0C8h+var_98]
0x18001808b  lea     rcx, [rsp+0C8h+var_70]
0x180018090  call    ?Path@?$consume_Windows_Storage_IStorageItem@UIStorageFolder@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFolder>::Path(void)
0x180018095  nop
0x180018096  mov     rax, [rax]
0x180018099  test    rax, rax
0x18001809c  jz      short loc_1800180A4
0x18001809e  mov     r8, [rax+10h]
0x1800180a2  jmp     short loc_1800180AB
0x1800180a4  lea     r8, sourceString
0x1800180ab  lea     rdx, aWs; "%ws\\"
0x1800180b2  lea     rcx, [rsp+0C8h+sourceString]
0x1800180ba  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800180bf  nop
0x1800180c0  lea     rcx, [rsp+0C8h+var_98]
0x1800180c5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800180ca  xor     edx, edx; length
0x1800180cc  mov     rcx, rdi; string
0x1800180cf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800180d5  mov     [rsp+0C8h+var_90], rax
0x1800180da  lea     r8, [rsp+0C8h+var_90]
0x1800180df  lea     rdx, [rsp+0C8h+sourceString]
0x1800180e7  lea     rcx, [rsp+0C8h+var_78]
0x1800180ec  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV12@PEBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAV10@$$QEAPEBG@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * &&)
0x1800180f1  mov     rdx, rax
0x1800180f4  lea     rcx, [rsp+0C8h+sourceString]
0x1800180fc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180018101  lea     rcx, [rsp+0C8h+var_78]
0x180018106  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001810b  mov     rdi, [rsp+0C8h+sourceString]
0x180018113  mov     [rsp+0C8h+var_78], rbx
0x180018118  lea     r8, [rsp+0C8h+var_78]
0x18001811d  lea     rcx, [rsp+0C8h+var_90]
0x180018122  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0DI@$$CBGPEAG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0DI@$$CBG$$QEAPEAG@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const (&)[56],ushort *>(ushort const (&)[56],ushort * &&)
0x180018127  nop
0x180018128  mov     r9, rdi; unsigned __int16 *
0x18001812b  lea     r8, aFilepath; "FilePath"
0x180018132  mov     rdx, [rax]; unsigned __int16 *
0x180018135  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001813c  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180018141  mov     rcx, [rsp+0C8h]; this
0x180018149  test    eax, eax
0x18001814b  js      loc_180018233
0x180018151  lea     rcx, [rsp+0C8h+var_90]
0x180018156  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001815b  mov     rcx, [rsp+0C8h+sourceString]; sourceString
0x180018163  test    rcx, rcx
0x180018166  jz      short loc_18001818F
0x180018168  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001816c  inc     rdx; length
0x18001816f  cmp     [rcx+rdx*2], r14w
0x180018174  jnz     short loc_18001816C
0x180018176  mov     r8, rsi; string
0x180018179  call    cs:__imp_WindowsCreateString
0x18001817f  mov     rcx, [rsp+0C8h]; this
0x180018187  test    eax, eax
0x180018189  js      loc_180018248
0x18001818f  lea     rcx, [rsp+0C8h+sourceString]
0x180018197  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001819c  nop
0x18001819d  lea     rcx, [rsp+0C8h+var_70]; this
0x1800181a2  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800181a7  nop
0x1800181a8  lea     rcx, [rsp+0C8h+var_68]; this
0x1800181ad  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800181b2  nop
0x1800181b3  lea     rcx, [rsp+0C8h+var_80]
0x1800181b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800181bd  nop
0x1800181be  lea     rcx, [rsp+0C8h+var_88]
0x1800181c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800181c8  xor     eax, eax
0x1800181ca  jmp     short loc_1800181D3
0x1800181cc  mov     eax, [rsp+0C8h+arg_10]
0x1800181d3  mov     rbx, [rsp+0C8h+arg_0]
0x1800181db  add     rsp, 0B0h
0x1800181e2  pop     r14
0x1800181e4  pop     rdi
0x1800181e5  pop     rsi
0x1800181e6  retn
0x1800181e7  mov     ecx, 8000FFFFh
0x1800181ec  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800181f1  mov     r9d, eax; char *
0x1800181f4  mov     rcx, [rsp+0C8h]; this
0x1800181fc  mov     dword ptr [rsp+0C8h+var_A0], r8d; char *
0x180018201  lea     rax, aUnexpectedRest; "Unexpected restoreAssetType [%d]"
0x180018208  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x18001820d  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x180018214  lea     edx, [r14+44h]; void *
0x180018218  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001821e  mov     r9d, eax; char *
0x180018221  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018228  mov     edx, 9Ah; void *
0x18001822d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018233  mov     r9d, eax; char *
0x180018236  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x18001823d  mov     edx, 53h ; 'S'; void *
0x180018242  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018248  mov     r9d, eax; char *
0x18001824b  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x180018252  mov     edx, 57h ; 'W'; void *
0x180018257  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
