# _GetUserFolderPathFromSid(ushort const *,ushort const *,ushort * *)

- ea: `0x180009488`
- end: `0x18000989f`
- name: `?_GetUserFolderPathFromSid@@YAJPEBG0PEAPEAG@Z`
- size: `1047`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x180003fdc`
- `0x180004990`
- `0x180004c10`
- `0x180005b60`
- `0x180005b90`
- `0x180008910`
- `0x1800090f0`
- `0x180009488`
- `0x1800098a8`
- `0x180009900`
- `0x1800099a0`
- `0x180009bcc`
- `0x180009cb0`
- `0x18000a1f4`
- `0x18000dd18`
- `0x180011f3c`
- `0x180011fa8`
- `0x180012014`
- `0x1800123ac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800097bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800097bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009524`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000955c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009524`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000955c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095af`

## string_xrefs

- `0x1800094dd`: `minio\profapi\path.cpp`
- `0x18000952a`: `minio\profapi\path.cpp`

## pseudocode

```c
__int64 __fastcall _GetUserFolderPathFromSid(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  WCHAR *v8; // r15
  int v9; // eax
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // ecx
  int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // rbx
  int BasicProfileFolderPathAlloc; // eax
  unsigned int v17; // esi
  int v18; // eax
  unsigned __int16 *v19; // rax
  int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  int phkResultb; // [rsp+20h] [rbp-60h]
  int phkResultc; // [rsp+20h] [rbp-60h]
  HKEY hKeySrc; // [rsp+30h] [rbp-50h] BYREF
  LPCWCH lpString1; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h]
  __int64 v28; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v29; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+58h] [rbp-28h]
  __int64 v31; // [rsp+60h] [rbp-20h]
  LPCWSTR lpSubKey[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HKEY v34; // [rsp+D0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+58h] BYREF

  *a3 = 0;
  memset(lpSubKey, 0, sizeof(lpSubKey));
  v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%ws\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders",
         a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
    goto LABEL_35;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = (WCHAR *)lpSubKey[0];
  if ( RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 0xF003Fu, &hKey) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = RegOpenKeyExW(HKEY_USERS, v8, 0, 0x20019u, &hKey);
    if ( v9 )
    {
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      LODWORD(v34) = v9;
      ProfAPITelemetry::UserShellFolderKeyOpenFailed<long>(&v34);
      hKeySrc = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeySrc,
        0);
      v10 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders\\Backup",
              0,
              0x20019u,
              &hKeySrc);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v12 = (unsigned __int16)v10 | 0x80070000;
        else
          v12 = v10;
        LODWORD(v34) = v12;
        ProfAPITelemetry::UserShellFolderBackupKeyOpenFailed<long>(&v34);
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x83,
               (unsigned int)"minio\\profapi\\path.cpp",
               (const char *)v11,
               phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
        goto LABEL_12;
      }
      v13 = _RecoverUserShellFolderKeys((char *)v8, a1, hKeySrc);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"minio\\profapi\\path.cpp",
          (const char *)(unsigned int)v13,
          phkResulta);
      v34 = hKeySrc;
      hKeySrc = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
        &hKeySrc,
        &hKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
        &hKey,
        &v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
    }
  }
  lpString1 = 0;
  v27 = 0;
  v28 = 0;
  LODWORD(v34) = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
                   (__int64)&lpString1,
                   hKey,
                   a2,
                   0);
  if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x8B,
              (unsigned int)"minio\\profapi\\path.cpp",
              (const char *)(unsigned int)v34,
              (__int64)"Failed to query %ws value under User Shell Folders key",
              (const char *)a2) < 0 )
  {
    ProfAPITelemetry::UserShellFolderKeyQueryValueFailed<long &>(&v34);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
    v27 = -1;
    v28 = -1;
    v14 = _RecoverUserShellFolderValue(hKey, a2, a1, (unsigned __int16 **)&lpString1);
    v7 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"minio\\profapi\\path.cpp",
        (const char *)(unsigned int)v14,
        phkResultb);
LABEL_19:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_35;
    }
  }
  v15 = (unsigned __int16 *)lpString1;
  if ( (unsigned int)IsFullPath(lpString1) )
  {
    lpString1 = 0;
    v28 = 0;
    v27 = 0;
    *a3 = v15;
LABEL_32:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
    if ( hKey )
      RegCloseKey(hKey);
    v7 = 0;
    goto LABEL_35;
  }
  v29 = 0;
  v30 = 0;
  v31 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v29);
  v30 = -1;
  v31 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(5, a1, &v29);
  v17 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc >= 0 )
  {
    if ( CompareStringOrdinal(v15, 13, L"%USERPROFILE%", 13, 1) == 2 )
    {
      v18 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
              &v29,
              L"\\%ws",
              v15 + 14);
      v7 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"minio\\profapi\\path.cpp",
          (const char *)(unsigned int)v18,
          phkResultc);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v29);
        goto LABEL_19;
      }
      v19 = v29;
      v29 = 0;
      v31 = 0;
      v30 = 0;
      *a3 = v19;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v29);
      goto LABEL_32;
    }
    v7 = -2147024735;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)0x800700A1LL,
      phkResultc);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v29);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      phkResultb);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v29);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
    if ( hKey )
      RegCloseKey(hKey);
    v7 = v17;
  }
LABEL_35:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x180009488  mov     [rsp-38h+arg_0], rbx
0x18000948d  push    rbp
0x18000948e  push    rsi
0x18000948f  push    rdi
0x180009490  push    r12
0x180009492  push    r13
0x180009494  push    r14
0x180009496  push    r15
0x180009498  mov     rbp, rsp
0x18000949b  sub     rsp, 80h
0x1800094a2  mov     r14, r8
0x1800094a5  mov     r12, rdx
0x1800094a8  mov     rsi, rcx
0x1800094ab  xor     r13d, r13d
0x1800094ae  mov     [r8], r13
0x1800094b1  mov     [rbp+lpSubKey], r13
0x1800094b5  mov     [rbp+var_10], r13
0x1800094b9  mov     [rbp+var_8], r13
0x1800094bd  mov     r8, rcx
0x1800094c0  lea     rdx, aWsSoftwareMicr; "%ws\\Software\\Microsoft\\Windows\\Curr"...
0x1800094c7  lea     rcx, [rbp+lpSubKey]
0x1800094cb  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800094d0  mov     ebx, eax
0x1800094d2  test    eax, eax
0x1800094d4  jns     short loc_1800094F2
0x1800094d6  mov     rcx, [rbp+38h]; this
0x1800094da  mov     r9d, eax; char *
0x1800094dd  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x1800094e4  lea     edx, [r13+60h]; void *
0x1800094e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094ed  jmp     loc_180009879
0x1800094f2  mov     [rbp+hKey], r13
0x1800094f6  xor     edx, edx
0x1800094f8  lea     rcx, [rbp+hKey]
0x1800094fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180009501  lea     rax, [rbp+hKey]
0x180009505  mov     [rsp+80h+phkResult], rax; phkResult
0x18000950a  mov     r9d, 0F003Fh; samDesired
0x180009510  xor     r8d, r8d; ulOptions
0x180009513  mov     r15, [rbp+lpSubKey]
0x180009517  mov     rdx, r15; lpSubKey
0x18000951a  mov     rbx, 0FFFFFFFF80000003h
0x180009521  mov     rcx, rbx; hKey
0x180009524  call    cs:__imp_RegOpenKeyExW
0x18000952a  lea     rdi, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180009531  test    eax, eax
0x180009533  jz      loc_180009666
0x180009539  xor     edx, edx
0x18000953b  lea     rcx, [rbp+hKey]
0x18000953f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180009544  lea     rax, [rbp+hKey]
0x180009548  mov     [rsp+80h+phkResult], rax; phkResult
0x18000954d  mov     r9d, 20019h; samDesired
0x180009553  xor     r8d, r8d; ulOptions
0x180009556  mov     rdx, r15; lpSubKey
0x180009559  mov     rcx, rbx; hKey
0x18000955c  call    cs:__imp_RegOpenKeyExW
0x180009562  test    eax, eax
0x180009564  jz      loc_180009666
0x18000956a  jle     short loc_180009574
0x18000956c  movzx   eax, ax
0x18000956f  or      eax, 80070000h
0x180009574  mov     dword ptr [rbp+arg_10], eax
0x180009577  lea     rcx, [rbp+arg_10]
0x18000957b  call    ??$UserShellFolderKeyOpenFailed@J@ProfAPITelemetry@@SAX$$QEAJ@Z; ProfAPITelemetry::UserShellFolderKeyOpenFailed<long>(long &&)
0x180009580  mov     [rbp+hKeySrc], r13
0x180009584  xor     edx, edx
0x180009586  lea     rcx, [rbp+hKeySrc]
0x18000958a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000958f  lea     rax, [rbp+hKeySrc]
0x180009593  mov     [rsp+80h+phkResult], rax; int
0x180009598  mov     r9d, 20019h; samDesired
0x18000959e  xor     r8d, r8d; ulOptions
0x1800095a1  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800095a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800095af  call    cs:__imp_RegOpenKeyExW
0x1800095b5  mov     ebx, eax
0x1800095b7  test    eax, eax
0x1800095b9  jz      short loc_180009606
0x1800095bb  test    eax, eax
0x1800095bd  jg      short loc_1800095C3
0x1800095bf  mov     ecx, eax
0x1800095c1  jmp     short loc_1800095CC
0x1800095c3  movzx   ecx, bx
0x1800095c6  or      ecx, 80070000h
0x1800095cc  mov     dword ptr [rbp+arg_10], ecx
0x1800095cf  lea     rcx, [rbp+arg_10]
0x1800095d3  call    ??$UserShellFolderBackupKeyOpenFailed@J@ProfAPITelemetry@@SAX$$QEAJ@Z; ProfAPITelemetry::UserShellFolderBackupKeyOpenFailed<long>(long &&)
0x1800095d8  mov     rcx, [rbp+38h]; this
0x1800095dc  mov     r9d, ebx; char *
0x1800095df  mov     r8, rdi; unsigned int
0x1800095e2  mov     edx, 83h; void *
0x1800095e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800095ec  mov     ebx, eax
0x1800095ee  lea     rcx, [rbp+hKeySrc]
0x1800095f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800095f7  nop
0x1800095f8  lea     rcx, [rbp+hKey]
0x1800095fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009601  jmp     loc_180009879
0x180009606  mov     r8, [rbp+hKeySrc]; hKeySrc
0x18000960a  mov     rdx, rsi; unsigned __int16 *
0x18000960d  mov     rcx, r15; char *
0x180009610  call    ?_RecoverUserShellFolderKeys@@YAJPEBG0PEAUHKEY__@@@Z; _RecoverUserShellFolderKeys(ushort const *,ushort const *,HKEY__ *)
0x180009615  mov     rcx, [rbp+38h]; this
0x180009619  test    eax, eax
0x18000961b  jns     short loc_18000962D
0x18000961d  mov     r9d, eax; char *
0x180009620  mov     r8, rdi; unsigned int
0x180009623  mov     edx, 84h; void *
0x180009628  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000962d  mov     rax, [rbp+hKeySrc]
0x180009631  mov     [rbp+arg_10], rax
0x180009635  mov     [rbp+hKeySrc], r13
0x180009639  lea     rdx, [rbp+hKey]
0x18000963d  lea     rcx, [rbp+hKeySrc]
0x180009641  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x180009646  lea     rdx, [rbp+arg_10]
0x18000964a  lea     rcx, [rbp+hKey]
0x18000964e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x180009653  lea     rcx, [rbp+arg_10]
0x180009657  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000965c  nop
0x18000965d  lea     rcx, [rbp+hKeySrc]
0x180009661  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009666  mov     [rbp+lpString1], r13
0x18000966a  mov     [rbp+var_40], r13
0x18000966e  mov     [rbp+var_38], r13
0x180009672  xor     r9d, r9d
0x180009675  mov     r8, r12
0x180009678  mov     rdx, [rbp+hKey]
0x18000967c  lea     rcx, [rbp+lpString1]
0x180009680  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180009685  mov     dword ptr [rbp+arg_10], eax
0x180009688  mov     rcx, [rbp+38h]; this
0x18000968c  mov     [rsp+80h+var_58], r12; char *
0x180009691  lea     rdx, aFailedToQueryW; "Failed to query %ws value under User Sh"...
0x180009698  mov     [rsp+80h+phkResult], rdx; int
0x18000969d  mov     r9d, eax; char *
0x1800096a0  mov     r8, rdi; unsigned int
0x1800096a3  mov     edx, 8Bh; void *
0x1800096a8  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800096ad  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800096b1  test    eax, eax
0x1800096b3  jns     short loc_18000970B
0x1800096b5  lea     rcx, [rbp+arg_10]
0x1800096b9  call    ??$UserShellFolderKeyQueryValueFailed@AEAJ@ProfAPITelemetry@@SAXAEAJ@Z; ProfAPITelemetry::UserShellFolderKeyQueryValueFailed<long &>(long &)
0x1800096be  lea     rcx, [rbp+lpString1]
0x1800096c2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800096c7  mov     [rbp+var_40], r15
0x1800096cb  mov     [rbp+var_38], r15
0x1800096cf  lea     r9, [rbp+lpString1]; unsigned __int16 **
0x1800096d3  mov     r8, rsi; unsigned __int16 *
0x1800096d6  mov     rdx, r12; lpValueName
0x1800096d9  mov     rcx, [rbp+hKey]; HKEY
0x1800096dd  call    ?_RecoverUserShellFolderValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; _RecoverUserShellFolderValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800096e2  mov     ebx, eax
0x1800096e4  test    eax, eax
0x1800096e6  jns     short loc_18000970B
0x1800096e8  mov     rcx, [rbp+38h]; this
0x1800096ec  mov     r9d, eax; char *
0x1800096ef  mov     r8, rdi; unsigned int
0x1800096f2  mov     edx, 8Eh; void *
0x1800096f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096fc  nop
0x1800096fd  lea     rcx, [rbp+lpString1]
0x180009701  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009706  jmp     loc_1800095F8
0x18000970b  mov     rbx, [rbp+lpString1]
0x18000970f  mov     rcx, rbx; unsigned __int16 *
0x180009712  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x180009717  test    eax, eax
0x180009719  jz      short loc_18000972F
0x18000971b  mov     [rbp+lpString1], r13
0x18000971f  mov     [rbp+var_38], r13
0x180009723  mov     [rbp+var_40], r13
0x180009727  mov     [r14], rbx
0x18000972a  jmp     loc_18000985D
0x18000972f  mov     [rbp+var_30], r13
0x180009733  mov     [rbp+var_28], r13
0x180009737  mov     [rbp+var_20], r13
0x18000973b  lea     rcx, [rbp+var_30]
0x18000973f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009744  mov     [rbp+var_28], r15
0x180009748  mov     [rbp+var_20], r15
0x18000974c  lea     r8, [rbp+var_30]
0x180009750  mov     rdx, rsi
0x180009753  mov     ecx, 5
0x180009758  call    GetBasicProfileFolderPathAlloc
0x18000975d  mov     esi, eax
0x18000975f  test    eax, eax
0x180009761  jns     short loc_1800097A1
0x180009763  mov     rcx, [rbp+38h]; this
0x180009767  mov     r9d, eax; char *
0x18000976a  mov     r8, rdi; unsigned int
0x18000976d  mov     edx, 98h; void *
0x180009772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009777  lea     rcx, [rbp+var_30]
0x18000977b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009780  nop
0x180009781  lea     rcx, [rbp+lpString1]
0x180009785  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000978a  nop
0x18000978b  mov     rcx, [rbp+hKey]; hKey
0x18000978f  test    rcx, rcx
0x180009792  jz      short loc_18000979A
0x180009794  call    cs:__imp_RegCloseKey
0x18000979a  mov     ebx, esi
0x18000979c  jmp     loc_180009879
0x1800097a1  mov     dword ptr [rsp+80h+phkResult], 1; int
0x1800097a9  mov     edx, 0Dh; cchCount1
0x1800097ae  mov     r9d, edx; cchCount2
0x1800097b1  lea     r8, aUserprofile_0; "%USERPROFILE%"
0x1800097b8  mov     rcx, rbx; lpString1
0x1800097bb  call    cs:__imp_CompareStringOrdinal
0x1800097c1  cmp     eax, 2
0x1800097c4  jz      short loc_180009804
0x1800097c6  mov     rcx, [rbp+38h]; this
0x1800097ca  mov     ebx, 800700A1h
0x1800097cf  mov     r9d, ebx; char *
0x1800097d2  mov     r8, rdi; unsigned int
0x1800097d5  mov     edx, 9Ah; void *
0x1800097da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097df  lea     rcx, [rbp+var_30]
0x1800097e3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800097e8  nop
0x1800097e9  lea     rcx, [rbp+lpString1]
0x1800097ed  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800097f2  nop
0x1800097f3  mov     rcx, [rbp+hKey]; hKey
0x1800097f7  test    rcx, rcx
0x1800097fa  jz      short loc_180009879
0x1800097fc  call    cs:__imp_RegCloseKey
0x180009802  jmp     short loc_180009879
0x180009804  lea     r8, [rbx+1Ch]
0x180009808  lea     rdx, aWs; "\\%ws"
0x18000980f  lea     rcx, [rbp+var_30]
0x180009813  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180009818  mov     ebx, eax
0x18000981a  test    eax, eax
0x18000981c  jns     short loc_180009840
0x18000981e  mov     rcx, [rbp+38h]; this
0x180009822  mov     r9d, eax; char *
0x180009825  mov     r8, rdi; unsigned int
0x180009828  mov     edx, 9Ch; void *
0x18000982d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009832  lea     rcx, [rbp+var_30]
0x180009836  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000983b  jmp     loc_1800096FD
0x180009840  mov     rax, [rbp+var_30]
0x180009844  mov     [rbp+var_30], r13
0x180009848  mov     [rbp+var_20], r13
0x18000984c  mov     [rbp+var_28], r13
0x180009850  mov     [r14], rax
0x180009853  lea     rcx, [rbp+var_30]
0x180009857  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000985c  nop
0x18000985d  lea     rcx, [rbp+lpString1]
0x180009861  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009866  nop
0x180009867  mov     rcx, [rbp+hKey]; hKey
0x18000986b  test    rcx, rcx
0x18000986e  jz      short loc_180009876
0x180009870  call    cs:__imp_RegCloseKey
0x180009876  mov     ebx, r13d
0x180009879  lea     rcx, [rbp+lpSubKey]
0x18000987d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009882  mov     eax, ebx
0x180009884  mov     rbx, [rsp+80h+arg_0]
0x18000988c  add     rsp, 80h
0x180009893  pop     r15
0x180009895  pop     r14
0x180009897  pop     r13
0x180009899  pop     r12
0x18000989b  pop     rdi
0x18000989c  pop     rsi
0x18000989d  pop     rbp
0x18000989e  retn
```
