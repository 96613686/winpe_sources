# CloudDataRestoreOobe::DownloadUserRestoreData(HSTRING__ *,HSTRING__ *)

- ea: `0x180018270`
- end: `0x180018528`
- name: `?DownloadUserRestoreData@CloudDataRestoreOobe@@UEAAJPEAUHSTRING__@@0@Z`
- size: `696`
- prototype: `int(CloudDataRestoreOobe *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000851c`
- `0x18000ac18`
- `0x18000b098`
- `0x180014200`
- `0x180014250`
- `0x18001430c`
- `0x180015328`
- `0x180015544`
- `0x18001562c`
- `0x180015654`
- `0x180015728`
- `0x180016a00`
- `0x1800172e0`
- `0x1800176dc`
- `0x180018270`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800182d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800182d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018309`

## string_xrefs

- `0x1800182af`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x18001849d`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`
- `0x180018515`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CloudDataRestoreOobe::DownloadUserRestoreData(CloudDataRestoreOobe *this, HSTRING a2, HSTRING a3)
{
  int v5; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  struct winrt::impl::hstring_header *v7; // rdx
  const unsigned __int16 *v8; // rdx
  struct winrt::impl::hstring_header *v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  winrt::impl *v12; // rbx
  unsigned int v13; // eax
  enum AsyncStatus v14; // edx
  unsigned int v15; // eax
  int v16; // ebx
  int v17; // eax
  const char *v18; // r9
  __int64 result; // rax
  winrt::impl *v20; // [rsp+20h] [rbp-A8h] BYREF
  int v21[2]; // [rsp+28h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+30h] [rbp-98h] BYREF
  struct winrt::impl::hstring_header **v23; // [rsp+38h] [rbp-90h] BYREF
  __int128 v24; // [rsp+40h] [rbp-88h]
  winrt::impl *v25[2]; // [rsp+50h] [rbp-78h] BYREF
  struct winrt::impl::hstring_header *v26; // [rsp+60h] [rbp-68h] BYREF
  winrt::impl *v27; // [rsp+80h] [rbp-48h] BYREF
  _BYTE v28[40]; // [rsp+A0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  struct winrt::impl::hstring_header *v30; // [rsp+E8h] [rbp+20h] BYREF

  v5 = SHRegSetDWORD(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudRestore\\EarlyDownload",
         L"Status",
         0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
      (const char *)(unsigned int)v5,
      (int)v20);
  winrt::param::hstring::hstring((winrt::param::hstring *)v28, &sourceString);
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  try
  {
    winrt::hstring::hstring((winrt::hstring *)v25, StringRawBuffer);
    *(_QWORD *)v21 = winrt::impl::duplicate_hstring(v25[0], v7);
    v27 = *(winrt::impl **)v21;
    v8 = WindowsGetStringRawBuffer(a2, 0);
    winrt::hstring::hstring((winrt::hstring *)&v20, v8);
    v30 = winrt::impl::duplicate_hstring(v20, v9);
    v26 = v30;
    v23 = &v26;
    *(_QWORD *)&v24 = &v27;
    *((_QWORD *)&v24 + 1) = v28;
    v25[1] = (winrt::impl *)&qword_1800A7138;
    _InterlockedIncrement64(&qword_1800A7138);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory> )
    {
      _lambda_300cd46623e1c475620ceb7ce06cd705_::operator()(
        &v23,
        &v22,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory>);
      _InterlockedDecrement64(&qword_1800A7138);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800A7138);
      winrt::impl::factory_cache_entry<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory>::call<_lambda_300cd46623e1c475620ceb7ce06cd705_ &>(
        v10,
        &v22,
        &v23);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v20);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v21);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v25);
    *(_QWORD *)v21 = 0;
    LODWORD(v23) = 0;
    v24 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 48LL))(v22, v21);
    winrt::check_hresult(&v30, v11, &v23);
    v12 = *(winrt::impl **)v21;
    v20 = *(winrt::impl **)v21;
    v13 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationResult,winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationProgress>>::Status(&v20);
    if ( !v13 )
      v13 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncActionWithProgress<winrt::Windows::Internal::ProfileDataRoaming::DownloadProgress>>(&v20);
    winrt::impl::check_status_canceled((winrt::impl *)v13, v14);
    LODWORD(v23) = 0;
    v24 = 0;
    v15 = (*(__int64 (__fastcall **)(winrt::impl *))(*(_QWORD *)v12 + 80LL))(v12);
    winrt::check_hresult(&v30, v15, &v23);
    v16 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationResult,winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationProgress>>::Status(&v20);
    if ( v16 != 1 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
        (const char *)0x80004005LL,
        (int)v20);
    v17 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudRestore\\EarlyDownload",
            L"Status",
            (unsigned int)(v16 != 1) + 1);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
        (const char *)(unsigned int)v17,
        (int)v20);
    winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v20);
    winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v22);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v30) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x31,
                     (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
                     v18);
    return (unsigned int)v30;
  }
  return result;
}

```

## disassembly

```asm
0x180018270  mov     [rsp+arg_0], rbx
0x180018275  push    rdi
0x180018276  sub     rsp, 0C0h
0x18001827d  mov     rbx, r8
0x180018280  mov     rdi, rdx
0x180018283  xor     r9d, r9d; unsigned int
0x180018286  lea     r8, aStatus; "Status"
0x18001828d  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180018294  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001829b  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800182a0  mov     rcx, [rsp+0C8h]; this
0x1800182a8  test    eax, eax
0x1800182aa  jns     short loc_1800182C0
0x1800182ac  mov     r9d, eax; char *
0x1800182af  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800182b6  mov     edx, 24h ; '$'; void *
0x1800182bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800182c0  lea     rdx, sourceString; unsigned __int16 *
0x1800182c7  lea     rcx, [rsp+0C8h+var_28]; this
0x1800182cf  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800182d4  xor     edx, edx; length
0x1800182d6  mov     rcx, rbx; string
0x1800182d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800182df  mov     rdx, rax; unsigned __int16 *
0x1800182e2  lea     rcx, [rsp+0C8h+var_78]; this
0x1800182e7  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800182ec  nop
0x1800182ed  mov     rcx, [rsp+0C8h+var_78]; this
0x1800182f2  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800182f7  mov     qword ptr [rsp+0C8h+var_A0], rax
0x1800182fc  mov     [rsp+0C8h+var_48], rax
0x180018304  xor     edx, edx; length
0x180018306  mov     rcx, rdi; string
0x180018309  call    cs:__imp_WindowsGetStringRawBuffer
0x18001830f  mov     rdx, rax; unsigned __int16 *
0x180018312  lea     rcx, [rsp+0C8h+var_A8]; this
0x180018317  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18001831c  nop
0x18001831d  mov     rcx, [rsp+0C8h+var_A8]; this
0x180018322  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180018327  mov     [rsp+0C8h+arg_18], rax
0x18001832f  mov     [rsp+0C8h+var_68], rax
0x180018334  lea     rax, [rsp+0C8h+var_68]
0x180018339  mov     [rsp+0C8h+var_90], rax
0x18001833e  lea     rax, [rsp+0C8h+var_48]
0x180018346  mov     qword ptr [rsp+0C8h+var_88], rax
0x18001834b  lea     rax, [rsp+0C8h+var_28]
0x180018353  mov     qword ptr [rsp+0C8h+var_88+8], rax
0x180018358  lea     rax, qword_1800A7138
0x18001835f  mov     [rsp+0C8h+var_70], rax
0x180018364  lock inc cs:qword_1800A7138
0x18001836c  cmp     cs:??$factory_cache_entry_v@UBackupRestoreDownloader@ProfileDataRoaming@Internal@Windows@winrt@@UIBackupRestoreDownloaderFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UBackupRestoreDownloader@ProfileDataRoaming@Internal@Windows@winrt@@UIBackupRestoreDownloaderFactory@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory>::winrt::factory_cache_entry<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory>
0x180018374  jz      short loc_180018397
0x180018376  lea     r8, ??$factory_cache_entry_v@UBackupRestoreDownloader@ProfileDataRoaming@Internal@Windows@winrt@@UIBackupRestoreDownloaderFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UBackupRestoreDownloader@ProfileDataRoaming@Internal@Windows@winrt@@UIBackupRestoreDownloaderFactory@2345@@12@A; factory_cache_entry<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory>::winrt::factory_cache_entry<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::ProfileDataRoaming::BackupRestoreDownloader,winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory>
0x18001837d  lea     rdx, [rsp+0C8h+var_98]
0x180018382  lea     rcx, [rsp+0C8h+var_90]
0x180018387  call    ??R_lambda_300cd46623e1c475620ceb7ce06cd705_@@QEBA@AEBUIBackupRestoreDownloaderFactory@ProfileDataRoaming@Internal@Windows@winrt@@@Z; _lambda_300cd46623e1c475620ceb7ce06cd705_::operator()(winrt::Windows::Internal::ProfileDataRoaming::IBackupRestoreDownloaderFactory const &)
0x18001838c  nop
0x18001838d  lock dec cs:qword_1800A7138
0x180018395  jmp     short loc_1800183AF
0x180018397  lock dec cs:qword_1800A7138
0x18001839f  lea     r8, [rsp+0C8h+var_90]
0x1800183a4  lea     rdx, [rsp+0C8h+var_98]
0x1800183a9  call    ??$call@AEAV_lambda_300cd46623e1c475620ceb7ce06cd705_@@@?$factory_cache_entry@UBackupRestoreDownloader@ProfileDataRoaming@Internal@Windows@winrt@@UIBackupRestoreDownloaderFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_300cd46623e1c475620ceb7ce06cd705_@@@Z
0x1800183ae  nop
0x1800183af  lea     rcx, [rsp+0C8h+arg_18]
0x1800183b7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800183bc  nop
0x1800183bd  lea     rcx, [rsp+0C8h+var_A8]
0x1800183c2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800183c7  nop
0x1800183c8  lea     rcx, [rsp+0C8h+var_A0]
0x1800183cd  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800183d2  nop
0x1800183d3  lea     rcx, [rsp+0C8h+var_78]
0x1800183d8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800183dd  mov     qword ptr [rsp+0C8h+var_A0], 0
0x1800183e6  mov     rcx, [rsp+0C8h+var_98]
0x1800183eb  mov     dword ptr [rsp+0C8h+var_90], 0
0x1800183f3  xorps   xmm0, xmm0
0x1800183f6  movdqu  [rsp+0C8h+var_88], xmm0
0x1800183fc  mov     rax, [rcx]
0x1800183ff  lea     rdx, [rsp+0C8h+var_A0]
0x180018404  mov     rax, [rax+30h]
0x180018408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001840d  lea     r8, [rsp+0C8h+var_90]
0x180018412  mov     edx, eax
0x180018414  lea     rcx, [rsp+0C8h+arg_18]
0x18001841c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018421  mov     rbx, qword ptr [rsp+0C8h+var_A0]
0x180018426  mov     [rsp+0C8h+var_A8], rbx; int
0x18001842b  lea     rcx, [rsp+0C8h+var_A8]
0x180018430  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperationWithProgress@UOperationResult@BackupRestoreCoordination@Cloud@Storage@Internal@Windows@winrt@@UOperationProgress@234567@@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationResult,winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationProgress>>::Status(void)
0x180018435  test    eax, eax
0x180018437  jnz     short loc_180018443
0x180018439  lea     rcx, [rsp+0C8h+var_A8]
0x18001843e  call    ??$wait_for_completed@U?$IAsyncActionWithProgress@UDownloadProgress@ProfileDataRoaming@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncActionWithProgress@UDownloadProgress@ProfileDataRoaming@Internal@Windows@winrt@@@Foundation@Windows@1@I@Z
0x180018443  mov     ecx, eax; this
0x180018445  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x18001844a  mov     dword ptr [rsp+0C8h+var_90], 0
0x180018452  xorps   xmm0, xmm0
0x180018455  movdqu  [rsp+0C8h+var_88], xmm0
0x18001845b  mov     rax, [rbx]
0x18001845e  mov     rcx, rbx
0x180018461  mov     rax, [rax+50h]
0x180018465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001846a  lea     r8, [rsp+0C8h+var_90]
0x18001846f  mov     edx, eax
0x180018471  lea     rcx, [rsp+0C8h+arg_18]
0x180018479  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001847e  lea     rcx, [rsp+0C8h+var_A8]
0x180018483  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperationWithProgress@UOperationResult@BackupRestoreCoordination@Cloud@Storage@Internal@Windows@winrt@@UOperationProgress@234567@@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationResult,winrt::Windows::Internal::Storage::Cloud::BackupRestoreCoordination::OperationProgress>>::Status(void)
0x180018488  mov     ebx, eax
0x18001848a  mov     rcx, [rsp+0C8h]; this
0x180018492  cmp     eax, 1
0x180018495  jz      short loc_1800184AE
0x180018497  mov     r9d, 80004005h; char *
0x18001849d  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800184a4  mov     edx, 2Ch ; ','; void *
0x1800184a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800184ae  xor     r9d, r9d
0x1800184b1  cmp     ebx, 1
0x1800184b4  setnz   r9b
0x1800184b8  inc     r9d; unsigned int
0x1800184bb  lea     r8, aStatus; "Status"
0x1800184c2  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800184c9  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800184d0  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800184d5  mov     rcx, [rsp+0C8h]; this
0x1800184dd  test    eax, eax
0x1800184df  js      short loc_180018512
0x1800184e1  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800184e6  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800184eb  nop
0x1800184ec  lea     rcx, [rsp+0C8h+var_98]; this
0x1800184f1  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x1800184f6  xor     eax, eax
0x1800184f8  jmp     short loc_180018501
0x1800184fa  mov     eax, dword ptr [rsp+0C8h+arg_18]
0x180018501  mov     rbx, [rsp+0C8h+arg_0]
0x180018509  add     rsp, 0C0h
0x180018510  pop     rdi
0x180018511  retn
0x180018512  mov     r9d, eax; char *
0x180018515  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x18001851c  mov     edx, 2Eh ; '.'; void *
0x180018521  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
