# HandleDirectXDatabaseDownloadCallback(ushort const *)

- ea: `0x140007ad8`
- end: `0x1400080f6`
- name: `?HandleDirectXDatabaseDownloadCallback@@YAJPEBG@Z`
- size: `1566`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f2a4`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140005204`
- `0x1400052fc`
- `0x140005cac`
- `0x140005f60`
- `0x1400061d4`
- `0x140006c80`
- `0x140007ad8`
- `0x1400083ac`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000ad00`
- `0x14000ae8c`
- `0x14000b5fc`
- `0x14000b93c`
- `0x14000cc54`
- `0x14000d384`
- `0x14000d940`
- `0x14000dda4`
- `0x14000df28`
- `0x140010ac0`
- `0x1400120b0`
- `0x1400122f8`
- `0x140014be4`
- `0x1400151f8`
- `0x1400181d8`
- `0x140018274`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140007d99`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140007d99`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140007c15`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140007c15`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140007dd3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140007e77`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140007f3f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000808e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140007dd3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140007e77`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140007f3f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000808e`

## string_xrefs

- `0x140007f9a`: `UninstallDxDbFOD`
- `0x140007b3f`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007bc1`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007c26`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007d55`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007da8`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007e4f`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007ed1`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140007f18`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x140008000`: `onecore\windows\directx\database\updater\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall HandleDirectXDatabaseDownloadCallback(const unsigned __int16 *a1)
{
  int JsonFile; // eax
  unsigned int LastError; // ebx
  const unsigned __int16 *v4; // rbx
  int v5; // eax
  __int64 v6; // rdx
  const char *v7; // r9
  int v8; // eax
  bool v9; // r8
  char v10; // di
  const char *v11; // r9
  __int64 v12; // rdx
  bool v13; // r8
  bool v14; // bl
  char v15; // al
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // r8
  int v18; // eax
  int v19; // esi
  bool v20; // r8
  bool v21; // zf
  char v22; // al
  const unsigned __int16 *v23; // rcx
  int v24; // eax
  bool v25; // r8
  int v26; // eax
  int v27; // edi
  bool v28; // r8
  char v29; // al
  const unsigned __int16 *v30; // rdx
  bool v31; // r8
  const unsigned __int16 *v32; // rdx
  __int64 v33; // rdx
  const wchar_t *v35; // [rsp+20h] [rbp-E0h]
  bool v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+50h] [rbp-B0h]
  WCHAR *v41; // [rsp+58h] [rbp-A8h]
  WCHAR *v42; // [rsp+60h] [rbp-A0h]
  bool v43; // [rsp+68h] [rbp-98h]
  WCHAR *v44; // [rsp+70h] [rbp-90h]
  char v45; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v46[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v47[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v48[42]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v49[42]; // [rsp+210h] [rbp+110h] BYREF
  WCHAR v50[264]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+570h] [rbp+470h] BYREF
  WCHAR TempFileName[264]; // [rsp+780h] [rbp+680h] BYREF
  WCHAR PathName[264]; // [rsp+990h] [rbp+890h] BYREF
  WCHAR Buffer[264]; // [rsp+BA0h] [rbp+AA0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+DD8h] [rbp+CD8h]

  std::wstring::wstring(v46);
  std::wstring::wstring(v47);
  JsonFile = ReadJsonFile(0, v46, 0, v47);
  LastError = JsonFile;
  if ( JsonFile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)JsonFile,
      (int)v35);
    goto LABEL_59;
  }
  v4 = (const unsigned __int16 *)v46;
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v46) )
    v4 = v46[0];
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v48,
    "DbDownloadCallbackActivity");
  v48[0] = &DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::`vftable';
  DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::StartActivity(
    (DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *)v48,
    v4);
  v37 = 0;
  v5 = BitsHelper::HandleJobCallback((BitsHelper *)&v37, a1);
  LastError = v5;
  if ( v5 == 1 )
    goto LABEL_58;
  if ( v5 < 0 )
  {
    v6 = 193;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)v5,
      (int)v35);
LABEL_9:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity((DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *)v48);
    goto LABEL_59;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC4,
                  (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
                  v7);
    goto LABEL_9;
  }
  memset_0(PathName, 0, 0x208u);
  v35 = (const wchar_t *)L"apppatch";
  v5 = StringCchPrintfW(PathName, 0x104u, L"%ws\\%ws", Buffer);
  LastError = v5;
  if ( v5 < 0 )
  {
    v6 = 199;
    goto LABEL_8;
  }
  memset_0(TempFileName, 0, 0x208u);
  memset_0(ExistingFileName, 0, 0x208u);
  v35 = L"DirectXApps.sdb";
  v5 = StringCchPrintfW(ExistingFileName, 0x104u, L"%ws\\%ws", PathName);
  LastError = v5;
  if ( v5 < 0 )
  {
    v6 = 203;
    goto LABEL_8;
  }
  memset_0(v50, 0, 0x208u);
  v35 = L"DirectXApps.lzma";
  v5 = StringCchPrintfW(v50, 0x104u, L"%ws\\%ws", PathName);
  LastError = v5;
  if ( v5 < 0 )
  {
    v6 = 205;
    goto LABEL_8;
  }
  v44 = v50;
  v45 = 1;
  v8 = DoesFileExist(ExistingFileName);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)v8,
      (int)L"DirectXApps.lzma");
LABEL_20:
    DxDbFileCompression::DeleteFileImpl(v50, 0, v9);
    goto LABEL_9;
  }
  v10 = 0;
  if ( !v8 )
  {
    if ( !GetTempFileNameW(PathName, L"dx", 0, TempFileName) )
    {
      v12 = 219;
LABEL_24:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
                    v11);
      goto LABEL_20;
    }
    v10 = 1;
    if ( !MoveFileExW(ExistingFileName, TempFileName, 1u) )
    {
      DxDbFileCompression::DeleteFileImpl(TempFileName, 0, v13);
      v12 = 224;
      goto LABEL_24;
    }
  }
  v41 = TempFileName;
  v42 = ExistingFileName;
  v14 = v10 != 0;
  v43 = v14;
  v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v47);
  v17 = (const unsigned __int16 *)v47;
  if ( v15 )
    v17 = v47[0];
  v18 = DxDbFileCompression::DecompressDatabaseFile((DxDbFileCompression *)v50, ExistingFileName, v17, v16);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)v18,
      (int)L"DirectXApps.lzma");
    v21 = v10 == 0;
LABEL_31:
    if ( !v21 )
      MoveFileExW(TempFileName, ExistingFileName, 1u);
    DxDbFileCompression::DeleteFileImpl(v50, 0, v20);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity((DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *)v48);
    LastError = v19;
    goto LABEL_59;
  }
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v46);
  v23 = (const unsigned __int16 *)v46;
  if ( v22 )
    v23 = v46[0];
  v24 = VerifyDirectXDatabaseVersion(v23);
  v19 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)v24,
      (int)L"DirectXApps.lzma");
    v21 = !v14;
    goto LABEL_31;
  }
  if ( v10 )
  {
    DxDbFileCompression::DeleteFileImpl(TempFileName, 0, v25);
    v14 = 0;
    v43 = 0;
  }
  v26 = AcknowledgeSettingsPayload();
  v27 = v26;
  if ( v26 >= 0 )
  {
    v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v46);
    v30 = (const unsigned __int16 *)v46;
    if ( v29 )
      v30 = v46[0];
    DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::Stop(
      (DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *)v48,
      v30);
    if ( !IsWindowsServer() )
    {
      wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v49,
        "UninstallDxDbFOD");
      v49[0] = &DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::`vftable';
      DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::StartActivity((DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *)v49);
      v36 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v27 = DxDbDismHelper::UninstallFOD((DxDbDismHelper *)&v38, v32, &v36);
      if ( v27 < 0 )
      {
        v33 = 270;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
          (const char *)(unsigned int)v27,
          (int)L"DirectXApps.lzma");
        DxDbDismHelper::~DxDbDismHelper((DxDbDismHelper *)&v38);
        DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::~UninstallDxDbFOD((DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *)v49);
        goto LABEL_42;
      }
      if ( !v36 )
      {
        v27 = WriteLastRunInfo(1, 2);
        if ( v27 < 0 )
        {
          v33 = 273;
          goto LABEL_50;
        }
      }
      wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v49);
      DxDbDismHelper::~DxDbDismHelper((DxDbDismHelper *)&v38);
      DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::~UninstallDxDbFOD((DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *)v49);
    }
    if ( v14 )
      MoveFileExW(TempFileName, ExistingFileName, 1u);
    DxDbFileCompression::DeleteFileImpl(v50, 0, v31);
LABEL_58:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity((DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *)v48);
    LastError = 0;
    goto LABEL_59;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFD,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
    (const char *)(unsigned int)v26,
    (int)L"DirectXApps.lzma");
LABEL_42:
  if ( v14 )
    MoveFileExW(TempFileName, ExistingFileName, 1u);
  DxDbFileCompression::DeleteFileImpl(v50, 0, v28);
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
  DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity((DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *)v48);
  LastError = v27;
LABEL_59:
  std::wstring::_Tidy_deallocate(v47);
  std::wstring::_Tidy_deallocate(v46);
  return LastError;
}

```

## disassembly

```asm
0x140007ad8  mov     [rsp-8+arg_8], rbx
0x140007add  mov     [rsp-8+arg_10], rsi
0x140007ae2  push    rbp
0x140007ae3  push    rdi
0x140007ae4  push    r15
0x140007ae6  lea     rbp, [rsp-0CC0h]
0x140007aee  sub     rsp, 0DC0h
0x140007af5  mov     rax, cs:__security_cookie
0x140007afc  xor     rax, rsp
0x140007aff  mov     [rbp+0CD0h+var_20], rax
0x140007b06  mov     rdi, rcx
0x140007b09  lea     rcx, [rbp+0CD0h+var_D50]
0x140007b0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140007b12  nop
0x140007b13  lea     rcx, [rbp+0CD0h+var_D30]
0x140007b17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140007b1c  nop
0x140007b1d  lea     r9, [rbp+0CD0h+var_D30]
0x140007b21  xor     r8d, r8d
0x140007b24  lea     rdx, [rbp+0CD0h+var_D50]
0x140007b28  xor     ecx, ecx
0x140007b2a  call    ?ReadJsonFile@@YAJ_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; ReadJsonFile(bool,std::wstring *,std::wstring *,std::wstring *)
0x140007b2f  mov     ebx, eax
0x140007b31  test    eax, eax
0x140007b33  jns     short loc_140007B55
0x140007b35  mov     rcx, [rbp+0CD8h]; this
0x140007b3c  mov     r9d, eax; char *
0x140007b3f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007b46  mov     edx, 0B6h; void *
0x140007b4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007b50  jmp     loc_1400080BA
0x140007b55  lea     rcx, [rbp+0CD0h+var_D50]
0x140007b59  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x140007b5e  lea     rbx, [rbp+0CD0h+var_D50]
0x140007b62  test    al, al
0x140007b64  cmovnz  rbx, [rbp+0CD0h+var_D50]
0x140007b69  lea     rdx, aDbdownloadcall; "DbDownloadCallbackActivity"
0x140007b70  lea     rcx, [rbp+0CD0h+var_D10]
0x140007b74  call    ??0?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140007b79  lea     rax, ??_7DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::`vftable'
0x140007b80  mov     [rbp+0CD0h+var_D10], rax
0x140007b84  mov     rdx, rbx; unsigned __int16 *
0x140007b87  lea     rcx, [rbp+0CD0h+var_D10]; this
0x140007b8b  call    ?StartActivity@DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG@Z; DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::StartActivity(ushort const *)
0x140007b90  nop
0x140007b91  mov     [rsp+0DD0h+var_D98], 0
0x140007b9a  mov     rdx, rdi; lpsz
0x140007b9d  lea     rcx, [rsp+0DD0h+var_D98]; this
0x140007ba2  call    ?HandleJobCallback@BitsHelper@@QEAAJPEBG@Z; BitsHelper::HandleJobCallback(ushort const *)
0x140007ba7  mov     ebx, eax
0x140007ba9  mov     r15d, 1
0x140007baf  cmp     eax, r15d
0x140007bb2  jz      loc_1400080A4
0x140007bb8  test    eax, eax
0x140007bba  jns     short loc_140007BF1
0x140007bbc  mov     edx, 0C1h; void *
0x140007bc1  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007bc8  mov     r9d, eax; char *
0x140007bcb  mov     rcx, [rbp+0CD8h]; this
0x140007bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007bd7  nop
0x140007bd8  lea     rcx, [rsp+0DD0h+var_D98]
0x140007bdd  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140007be2  nop
0x140007be3  lea     rcx, [rbp+0CD0h+var_D10]; this
0x140007be7  call    ??1DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity(void)
0x140007bec  jmp     loc_1400080BA
0x140007bf1  mov     edi, 208h
0x140007bf6  mov     r8d, edi; Size
0x140007bf9  xor     edx, edx; Val
0x140007bfb  lea     rcx, [rbp+0CD0h+Buffer]; void *
0x140007c02  call    memset_0
0x140007c07  mov     esi, 104h
0x140007c0c  mov     edx, esi; uSize
0x140007c0e  lea     rcx, [rbp+0CD0h+Buffer]; lpBuffer
0x140007c15  call    cs:__imp_GetWindowsDirectoryW
0x140007c1b  test    eax, eax
0x140007c1d  jnz     short loc_140007C39
0x140007c1f  mov     rcx, [rbp+0CD8h]; this
0x140007c26  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007c2d  lea     edx, [rsi-40h]; void *
0x140007c30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007c35  mov     ebx, eax
0x140007c37  jmp     short loc_140007BD8
0x140007c39  mov     r8, rdi; Size
0x140007c3c  xor     edx, edx; Val
0x140007c3e  lea     rcx, [rbp+0CD0h+PathName]; void *
0x140007c45  call    memset_0
0x140007c4a  lea     rax, aApppatch; "apppatch"
0x140007c51  mov     qword ptr [rsp+0DD0h+var_DB0], rax
0x140007c56  lea     r9, [rbp+0CD0h+Buffer]
0x140007c5d  lea     r8, aWsWs; "%ws\\%ws"
0x140007c64  mov     rdx, rsi; unsigned __int64
0x140007c67  lea     rcx, [rbp+0CD0h+PathName]; unsigned __int16 *
0x140007c6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007c73  mov     ebx, eax
0x140007c75  test    eax, eax
0x140007c77  jns     short loc_140007C83
0x140007c79  mov     edx, 0C7h
0x140007c7e  jmp     loc_140007BC1
0x140007c83  mov     r8, rdi; Size
0x140007c86  xor     edx, edx; Val
0x140007c88  lea     rcx, [rbp+0CD0h+TempFileName]; void *
0x140007c8f  call    memset_0
0x140007c94  mov     r8, rdi; Size
0x140007c97  xor     edx, edx; Val
0x140007c99  lea     rcx, [rbp+0CD0h+ExistingFileName]; void *
0x140007ca0  call    memset_0
0x140007ca5  lea     rax, aDirectxappsSdb; "DirectXApps.sdb"
0x140007cac  mov     qword ptr [rsp+0DD0h+var_DB0], rax
0x140007cb1  lea     r9, [rbp+0CD0h+PathName]
0x140007cb8  lea     r8, aWsWs; "%ws\\%ws"
0x140007cbf  mov     rdx, rsi; unsigned __int64
0x140007cc2  lea     rcx, [rbp+0CD0h+ExistingFileName]; unsigned __int16 *
0x140007cc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007cce  mov     ebx, eax
0x140007cd0  test    eax, eax
0x140007cd2  jns     short loc_140007CDE
0x140007cd4  mov     edx, 0CBh
0x140007cd9  jmp     loc_140007BC1
0x140007cde  mov     r8, rdi; Size
0x140007ce1  xor     edx, edx; Val
0x140007ce3  lea     rcx, [rbp+0CD0h+var_A70]; void *
0x140007cea  call    memset_0
0x140007cef  lea     rax, aDirectxappsLzm; "DirectXApps.lzma"
0x140007cf6  mov     qword ptr [rsp+0DD0h+var_DB0], rax; int
0x140007cfb  lea     r9, [rbp+0CD0h+PathName]
0x140007d02  lea     r8, aWsWs; "%ws\\%ws"
0x140007d09  mov     rdx, rsi; unsigned __int64
0x140007d0c  lea     rcx, [rbp+0CD0h+var_A70]; unsigned __int16 *
0x140007d13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007d18  mov     ebx, eax
0x140007d1a  test    eax, eax
0x140007d1c  jns     short loc_140007D28
0x140007d1e  mov     edx, 0CDh
0x140007d23  jmp     loc_140007BC1
0x140007d28  lea     rax, [rbp+0CD0h+var_A70]
0x140007d2f  mov     [rsp+0DD0h+var_D60], rax
0x140007d34  mov     [rsp+0DD0h+var_D58], r15b
0x140007d39  lea     rcx, [rbp+0CD0h+ExistingFileName]; lpFileName
0x140007d40  call    ?DoesFileExist@@YAJPEBG@Z; DoesFileExist(ushort const *)
0x140007d45  mov     ebx, eax
0x140007d47  test    eax, eax
0x140007d49  jns     short loc_140007D7A
0x140007d4b  mov     rcx, [rbp+0CD8h]; this
0x140007d52  mov     r9d, eax; char *
0x140007d55  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007d5c  mov     edx, 0D6h; void *
0x140007d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007d66  nop
0x140007d67  xor     edx, edx; unsigned __int16 *
0x140007d69  lea     rcx, [rbp+0CD0h+var_A70]; lpExistingFileName
0x140007d70  call    ?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z; DxDbFileCompression::DeleteFileImpl(ushort const *,bool)
0x140007d75  jmp     loc_140007BD8
0x140007d7a  xor     dil, dil
0x140007d7d  test    eax, eax
0x140007d7f  jnz     short loc_140007DF2
0x140007d81  lea     r9, [rbp+0CD0h+TempFileName]; lpTempFileName
0x140007d88  xor     r8d, r8d; uUnique
0x140007d8b  lea     rdx, PrefixString; "dx"
0x140007d92  lea     rcx, [rbp+0CD0h+PathName]; lpPathName
0x140007d99  call    cs:__imp_GetTempFileNameW
0x140007d9f  test    eax, eax
0x140007da1  jnz     short loc_140007DBF
0x140007da3  mov     edx, 0DBh; void *
0x140007da8  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007daf  mov     rcx, [rbp+0CD8h]; this
0x140007db6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007dbb  mov     ebx, eax
0x140007dbd  jmp     short loc_140007D67
0x140007dbf  mov     dil, r15b
0x140007dc2  mov     r8d, r15d; dwFlags
0x140007dc5  lea     rdx, [rbp+0CD0h+TempFileName]; lpNewFileName
0x140007dcc  lea     rcx, [rbp+0CD0h+ExistingFileName]; lpExistingFileName
0x140007dd3  call    cs:__imp_MoveFileExW
0x140007dd9  test    eax, eax
0x140007ddb  jnz     short loc_140007DF2
0x140007ddd  xor     edx, edx; unsigned __int16 *
0x140007ddf  lea     rcx, [rbp+0CD0h+TempFileName]; lpExistingFileName
0x140007de6  call    ?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z; DxDbFileCompression::DeleteFileImpl(ushort const *,bool)
0x140007deb  mov     edx, 0E0h
0x140007df0  jmp     short loc_140007DA8
0x140007df2  lea     rax, [rbp+0CD0h+TempFileName]
0x140007df9  mov     [rsp+0DD0h+var_D78], rax
0x140007dfe  lea     rax, [rbp+0CD0h+ExistingFileName]
0x140007e05  mov     [rsp+0DD0h+var_D70], rax
0x140007e0a  mov     al, dil
0x140007e0d  neg     al
0x140007e0f  sbb     bl, bl
0x140007e11  and     bl, r15b
0x140007e14  mov     [rsp+0DD0h+var_D68], bl
0x140007e18  lea     rcx, [rbp+0CD0h+var_D30]
0x140007e1c  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x140007e21  lea     r8, [rbp+0CD0h+var_D30]
0x140007e25  test    al, al
0x140007e27  cmovnz  r8, [rbp+0CD0h+var_D30]; unsigned __int16 *
0x140007e2c  lea     rdx, [rbp+0CD0h+ExistingFileName]; unsigned __int16 *
0x140007e33  lea     rcx, [rbp+0CD0h+var_A70]; this
0x140007e3a  call    ?DecompressDatabaseFile@DxDbFileCompression@@YAJPEBG00@Z; DxDbFileCompression::DecompressDatabaseFile(ushort const *,ushort const *,ushort const *)
0x140007e3f  mov     esi, eax
0x140007e41  test    eax, eax
0x140007e43  jns     short loc_140007EA8
0x140007e45  mov     rcx, [rbp+0CD8h]; this
0x140007e4c  mov     r9d, eax; char *
0x140007e4f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007e56  mov     edx, 0EFh; void *
0x140007e5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007e60  nop
0x140007e61  test    dil, dil
0x140007e64  jz      short loc_140007E7E
0x140007e66  mov     r8d, r15d; dwFlags
0x140007e69  lea     rdx, [rbp+0CD0h+ExistingFileName]; lpNewFileName
0x140007e70  lea     rcx, [rbp+0CD0h+TempFileName]; lpExistingFileName
0x140007e77  call    cs:__imp_MoveFileExW
0x140007e7d  nop
0x140007e7e  xor     edx, edx; unsigned __int16 *
0x140007e80  lea     rcx, [rbp+0CD0h+var_A70]; lpExistingFileName
0x140007e87  call    ?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z; DxDbFileCompression::DeleteFileImpl(ushort const *,bool)
0x140007e8c  nop
0x140007e8d  lea     rcx, [rsp+0DD0h+var_D98]
0x140007e92  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140007e97  nop
0x140007e98  lea     rcx, [rbp+0CD0h+var_D10]; this
0x140007e9c  call    ??1DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity(void)
0x140007ea1  mov     ebx, esi
0x140007ea3  jmp     loc_1400080BA
0x140007ea8  lea     rcx, [rbp+0CD0h+var_D50]
0x140007eac  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x140007eb1  lea     rcx, [rbp+0CD0h+var_D50]
0x140007eb5  test    al, al
0x140007eb7  cmovnz  rcx, [rbp+0CD0h+var_D50]; unsigned __int16 *
0x140007ebc  call    ?VerifyDirectXDatabaseVersion@@YAJPEBG@Z; VerifyDirectXDatabaseVersion(ushort const *)
0x140007ec1  mov     esi, eax
0x140007ec3  test    eax, eax
0x140007ec5  jns     short loc_140007EEA
0x140007ec7  mov     rcx, [rbp+0CD8h]; this
0x140007ece  mov     r9d, eax; char *
0x140007ed1  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007ed8  mov     edx, 0F2h; void *
0x140007edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007ee2  nop
0x140007ee3  test    bl, bl
0x140007ee5  jmp     loc_140007E64
0x140007eea  test    dil, dil
0x140007eed  jz      short loc_140007F03
0x140007eef  xor     edx, edx; unsigned __int16 *
0x140007ef1  lea     rcx, [rbp+0CD0h+TempFileName]; lpExistingFileName
0x140007ef8  call    ?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z; DxDbFileCompression::DeleteFileImpl(ushort const *,bool)
0x140007efd  xor     bl, bl
0x140007eff  mov     [rsp+0DD0h+var_D68], bl
0x140007f03  call    ?AcknowledgeSettingsPayload@@YAJXZ; AcknowledgeSettingsPayload(void)
0x140007f08  mov     edi, eax
0x140007f0a  test    eax, eax
0x140007f0c  jns     short loc_140007F70
0x140007f0e  mov     rcx, [rbp+0CD8h]; this
0x140007f15  mov     r9d, eax; char *
0x140007f18  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140007f1f  mov     edx, 0FDh; void *
0x140007f24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007f29  nop
0x140007f2a  test    bl, bl
0x140007f2c  jz      short loc_140007F46
0x140007f2e  mov     r8d, r15d; dwFlags
0x140007f31  lea     rdx, [rbp+0CD0h+ExistingFileName]; lpNewFileName
0x140007f38  lea     rcx, [rbp+0CD0h+TempFileName]; lpExistingFileName
0x140007f3f  call    cs:__imp_MoveFileExW
0x140007f45  nop
0x140007f46  xor     edx, edx; unsigned __int16 *
0x140007f48  lea     rcx, [rbp+0CD0h+var_A70]; lpExistingFileName
0x140007f4f  call    ?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z; DxDbFileCompression::DeleteFileImpl(ushort const *,bool)
0x140007f54  nop
0x140007f55  lea     rcx, [rsp+0DD0h+var_D98]
0x140007f5a  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140007f5f  nop
0x140007f60  lea     rcx, [rbp+0CD0h+var_D10]; this
0x140007f64  call    ??1DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ; DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity(void)
0x140007f69  mov     ebx, edi
0x140007f6b  jmp     loc_1400080BA
0x140007f70  lea     rcx, [rbp+0CD0h+var_D50]
0x140007f74  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x140007f79  lea     rdx, [rbp+0CD0h+var_D50]
0x140007f7d  test    al, al
0x140007f7f  cmovnz  rdx, [rbp+0CD0h+var_D50]; unsigned __int16 *
0x140007f84  lea     rcx, [rbp+0CD0h+var_D10]; this
0x140007f88  call    ?Stop@DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG@Z; DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::Stop(ushort const *)
0x140007f8d  call    ?IsWindowsServer@@YA_NXZ; IsWindowsServer(void)
0x140007f92  test    al, al
0x140007f94  jnz     loc_140008079
0x140007f9a  lea     rdx, aUninstalldxdbf; "UninstallDxDbFOD"
0x140007fa1  lea     rcx, [rbp+0CD0h+var_BC0]
0x140007fa8  call    ??0?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140007fad  lea     rax, ??_7UninstallDxDbFOD@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::`vftable'
0x140007fb4  mov     [rbp+0CD0h+var_BC0], rax
0x140007fbb  lea     rcx, [rbp+0CD0h+var_BC0]; this
0x140007fc2  call    ?StartActivity@UninstallDxDbFOD@DirectXDatabaseUpdaterTelemetry@@QEAAXXZ; DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::StartActivity(void)
0x140007fc7  nop
0x140007fc8  mov     [rsp+0DD0h+var_DA0], 0
0x140007fcd  mov     [rsp+0DD0h+var_D90], 0
0x140007fd5  mov     [rsp+0DD0h+var_D88], 0
0x140007fde  mov     [rsp+0DD0h+var_D80], 0
  ... truncated ...
```
