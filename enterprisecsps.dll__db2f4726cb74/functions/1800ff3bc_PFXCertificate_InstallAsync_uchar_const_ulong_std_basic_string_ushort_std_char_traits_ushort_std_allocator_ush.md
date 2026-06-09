# PFXCertificate::InstallAsync(uchar const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ImportPFXFlags)

- ea: `0x1800ff3bc`
- end: `0x1800ffb99`
- name: `?InstallAsync@PFXCertificate@@IEAAJPEBEKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1W4ImportPFXFlags@@@Z`
- size: `2013`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ff028`

## callees

- `0x180003504`
- `0x180005824`
- `0x180008de0`
- `0x180009cc4`
- `0x18000e718`
- `0x180015888`
- `0x180019fd8`
- `0x180025450`
- `0x18004568c`
- `0x180048624`
- `0x1800635a8`
- `0x180081b0c`
- `0x180083ca8`
- `0x180089860`
- `0x1800feac8`
- `0x1800ff3bc`
- `0x180100124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff6d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff6d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff98b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff817`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800ff91a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800ff91a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff834`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff834`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffad5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ff752`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ff7d2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ff752`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ff7d2`
- `RPCRT4!UuidToStringW` at `0x1800ff43d`
- `RPCRT4!UuidToStringW` at `0x1800ff43d`
- `RPCRT4!RpcStringFreeW` at `0x1800ffb60`
- `RPCRT4!RpcStringFreeW` at `0x1800ffb60`
- `RPCRT4!UuidCreate` at `0x1800ff410`
- `RPCRT4!UuidCreate` at `0x1800ff410`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ff616`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ff616`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ffa12`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ffa12`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeClientProcessId` at `0x1800ff9ad`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeClientProcessId` at `0x1800ff9ad`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1800ff6be`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1800ff6be`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x1800ff97b`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x1800ff97b`

## string_xrefs

- `0x1800ff74b`: `%windir%\system32\dmcertinst.exe `
- `0x1800ff7cb`: `%windir%\system32\dmcertinst.exe `

## pseudocode

```c
// Hidden C++ exception states: #wind=8
RPC_STATUS __fastcall PFXCertificate::InstallAsync(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        char a6)
{
  __int64 v7; // rdi
  RPC_STATUS result; // eax
  __int64 v11; // rcx
  unsigned int i; // ebx
  _BYTE *v13; // r8
  __int64 v14; // rcx
  __int64 j; // rbx
  char *v16; // r8
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  signed int CurrentUserSID; // esi
  const WCHAR *v20; // rcx
  signed int LastError; // eax
  __int64 v22; // r8
  const WCHAR *v23; // rcx
  HANDLE v24; // rbx
  signed int v25; // eax
  DWORD v26; // eax
  DWORD v27; // r15d
  WCHAR *v28; // rdi
  signed int v29; // eax
  HANDLE CurrentThread; // rax
  signed int v31; // eax
  int v32; // r8d
  int v33; // r9d
  WCHAR *v34; // r8
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // r8d
  int v39; // r9d
  int v40; // r8d
  int v41; // r9d
  LPWSTR lpDst[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v45; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+88h] [rbp-78h] BYREF
  LPCVOID v47; // [rsp+98h] [rbp-68h]
  ULONG ClientProcessId; // [rsp+A0h] [rbp-60h] BYREF
  RPC_WSTR StringUuid; // [rsp+A8h] [rbp-58h] BYREF
  const char *v50; // [rsp+B0h] [rbp-50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp-48h] BYREF
  const char *p_StringUuid; // [rsp+C0h] [rbp-40h] BYREF
  char v53; // [rsp+C8h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+D0h] [rbp-30h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+E8h] [rbp-18h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+170h] [rbp+70h] BYREF
  __m128i si128; // [rsp+180h] [rbp+80h]
  LPCWSTR lpName[4]; // [rsp+190h] [rbp+90h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v61; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v62; // [rsp+1E0h] [rbp+E0h]
  __int64 v63; // [rsp+1E8h] [rbp+E8h]
  UUID Uuid; // [rsp+1F0h] [rbp+F0h] BYREF

  v7 = a3;
  Uuid = 0;
  result = UuidCreate(&Uuid);
  if ( !result || result == 1824 )
  {
    StringUuid = 0;
    result = UuidToStringW(&Uuid, &StringUuid);
    if ( !result )
    {
      p_StringUuid = (const char *)&StringUuid;
      v53 = 1;
      *(_OWORD *)lpBuffer = 0;
      v47 = 0;
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpBuffer, 40);
      for ( i = 0; i < (unsigned int)v7; ++i )
      {
        v13 = (_BYTE *)(a2 + i);
        if ( lpBuffer[1] == v47 )
          std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(lpBuffer, lpBuffer[1], v13);
        else
          *(_BYTE *)lpBuffer[1]++ = *v13;
      }
      PFXCertificate::SerializeStringToBuffer(v11, lpBuffer, a4);
      for ( j = 0; j != 4; ++j )
      {
        v16 = &a6 + j;
        if ( lpBuffer[1] == v47 )
          std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(lpBuffer, lpBuffer[1], v16);
        else
          *(_BYTE *)lpBuffer[1]++ = *v16;
      }
      PFXCertificate::SerializeStringToBuffer(v14, lpBuffer, a5);
      PFXCertificate::SerializeStringToBuffer(v17, lpBuffer, a1 + 96);
      v18 = lpBuffer[0];
      *(_QWORD *)lpBuffer[0] = v7;
      v18[1] = 2LL * *(_QWORD *)(a4 + 16) + 2;
      v18[2] = 4;
      v18[3] = 2LL * *(_QWORD *)(a5 + 16) + 2;
      v18[4] = 2LL * *(_QWORD *)(a1 + 112) + 2;
      v61 = 0;
      v62 = 0;
      v63 = 7;
      LOWORD(v61) = 0;
      CurrentUserSID = PFXCertificate::GetCurrentUserSID(v18, &v61);
      if ( CurrentUserSID < 0 )
        goto LABEL_63;
      *(_OWORD *)StringSecurityDescriptor = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(StringSecurityDescriptor[0]) = 0;
      std::wstring::_Append<unsigned short>(StringSecurityDescriptor);
      std::wstring::_Append<unsigned short>(StringSecurityDescriptor);
      std::wstring::_Append<unsigned short>(StringSecurityDescriptor);
      memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      SecurityDescriptor.nLength = 24;
      v20 = (const WCHAR *)StringSecurityDescriptor;
      if ( si128.m128i_i64[1] > 7uLL )
        v20 = StringSecurityDescriptor[0];
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v20, 1u, &SecurityDescriptor.lpSecurityDescriptor, 0) )
      {
        LastError = GetLastError();
        CurrentUserSID = LastError;
        if ( LastError > 0 )
          CurrentUserSID = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_62;
      }
      std::wstring::wstring(lpName, L"\\\\.\\pipe\\");
      v22 = -1;
      do
        ++v22;
      while ( StringUuid[v22] );
      std::wstring::_Append<unsigned short>(lpName);
      v23 = (const WCHAR *)lpName;
      if ( lpName[3] > (LPCWSTR)7 )
        v23 = lpName[0];
      v24 = CreateNamedPipeW(
              v23,
              0x80002u,
              0xEu,
              1u,
              LODWORD(lpBuffer[1]) - LODWORD(lpBuffer[0]),
              0,
              0,
              &SecurityDescriptor);
      v45 = v24;
      if ( v24 == (HANDLE)-1LL )
      {
        v25 = GetLastError();
        CurrentUserSID = v25;
        if ( v25 > 0 )
          CurrentUserSID = (unsigned __int16)v25 | 0x80070000;
LABEL_61:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v45);
        std::wstring::_Tidy_deallocate(lpName);
LABEL_62:
        std::wstring::_Tidy_deallocate(StringSecurityDescriptor);
LABEL_63:
        std::wstring::_Tidy_deallocate(&v61);
        std::vector<unsigned char>::_Tidy(lpBuffer);
        RpcStringFreeW(&StringUuid);
        return CurrentUserSID;
      }
      std::wstring::wstring(lpCommandLine, L"-x -n ");
      std::wstring::_Append<unsigned short>(lpCommandLine);
      *(_OWORD *)lpDst = 0;
      v43 = 0;
      v26 = ExpandEnvironmentStringsW(L"%windir%\\system32\\dmcertinst.exe ", 0, 0);
      v27 = v26;
      if ( v26 )
      {
        if ( v26 <= (unsigned __int64)((signed __int64)(v43 - (unsigned __int64)lpDst[0]) >> 1) )
        {
          v28 = (WCHAR *)(2LL * v26);
          memset_0(lpDst[1], 0, (size_t)v28);
          lpDst[1] = v28;
        }
        else
        {
          std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpDst, v26);
        }
      }
      if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\dmcertinst.exe ", lpDst[0], v27) )
      {
        v29 = GetLastError();
        CurrentUserSID = v29;
        if ( v29 > 0 )
          CurrentUserSID = (unsigned __int16)v29 | 0x80070000;
        goto LABEL_58;
      }
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xBu, 1, &TokenHandle) )
      {
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        memset_0(&StartupInfo, 0, sizeof(StartupInfo));
        StartupInfo.cb = 104;
        StartupInfo.lpDesktop = L"WinSta0\\Default";
        if ( (unsigned int)dword_180155A70 > 5 )
        {
          v50 = "Launching dmcertinst.exe process as user";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_180155A70,
            (unsigned int)byte_18013BDE1,
            v32,
            v33,
            (__int64)&v50);
        }
        v34 = (WCHAR *)lpCommandLine;
        if ( lpCommandLine[3] > (LPWSTR)7 )
          v34 = lpCommandLine[0];
        if ( CreateProcessAsUserW(
               TokenHandle,
               lpDst[0],
               v34,
               0,
               0,
               0,
               0x1000000u,
               0,
               0,
               &StartupInfo,
               &ProcessInformation) )
        {
          if ( ConnectNamedPipe(v24, 0) || GetLastError() == 535 )
          {
            ClientProcessId = 0;
            if ( !GetNamedPipeClientProcessId(v24, &ClientProcessId)
              || ClientProcessId == ProcessInformation.dwProcessId )
            {
              if ( (unsigned int)dword_180155A70 > 5 )
              {
                p_StringUuid = "Passing Pfx data to the process.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&dword_180155A70,
                  (unsigned int)byte_18013BC25,
                  v38,
                  v39,
                  (__int64)&p_StringUuid);
              }
              NumberOfBytesWritten = 0;
              if ( WriteFile(v24, lpBuffer[0], LODWORD(lpBuffer[1]) - LODWORD(lpBuffer[0]), &NumberOfBytesWritten, 0) )
              {
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
LABEL_57:
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_58:
                if ( lpDst[0] )
                {
                  std::_Deallocate<16>(lpDst[0], 2 * ((signed __int64)(v43 - (unsigned __int64)lpDst[0]) >> 1));
                  *(_OWORD *)lpDst = 0;
                  v43 = 0;
                }
                std::wstring::_Tidy_deallocate(lpCommandLine);
                goto LABEL_61;
              }
              if ( (unsigned int)dword_180155A70 > 5 )
              {
                p_StringUuid = "Failed to pass pfx data to the process";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&dword_180155A70,
                  (unsigned int)&unk_18013BC68,
                  v40,
                  v41,
                  (__int64)&p_StringUuid);
              }
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            if ( lpDst[0] )
            {
              std::_Deallocate<16>(lpDst[0], 2 * ((signed __int64)(v43 - (unsigned __int64)lpDst[0]) >> 1));
              v43 = 0;
              *(_OWORD *)lpDst = 0;
            }
            std::wstring::_Tidy_deallocate(lpCommandLine);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v45);
            std::wstring::_Tidy_deallocate(lpName);
            std::wstring::_Tidy_deallocate(StringSecurityDescriptor);
            CurrentUserSID = -2147418113;
            goto LABEL_63;
          }
        }
        else if ( (unsigned int)dword_180155A70 > 5 )
        {
          LODWORD(v50) = GetLastError();
          p_StringUuid = "Launching dmcertinst.exe Failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)&dword_18013BE2C,
            v36,
            v37,
            (__int64)&p_StringUuid,
            (__int64)&v50);
        }
      }
      v31 = GetLastError();
      CurrentUserSID = v31;
      if ( v31 > 0 )
        CurrentUserSID = (unsigned __int16)v31 | 0x80070000;
      goto LABEL_57;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ff3bc  mov     [rsp-8+arg_8], rbx
0x1800ff3c1  push    rbp
0x1800ff3c2  push    rsi
0x1800ff3c3  push    rdi
0x1800ff3c4  push    r12
0x1800ff3c6  push    r13
0x1800ff3c8  push    r14
0x1800ff3ca  push    r15
0x1800ff3cc  lea     rbp, [rsp-110h]
0x1800ff3d4  sub     rsp, 210h
0x1800ff3db  mov     rax, cs:__security_cookie
0x1800ff3e2  xor     rax, rsp
0x1800ff3e5  mov     [rbp+140h+var_40], rax
0x1800ff3ec  mov     rsi, r9
0x1800ff3ef  mov     edi, r8d
0x1800ff3f2  mov     r14, rdx
0x1800ff3f5  mov     r15, rcx
0x1800ff3f8  mov     r13, [rbp+140h+arg_20]
0x1800ff3ff  xorps   xmm0, xmm0
0x1800ff402  movups  xmmword ptr [rbp+140h+Uuid.Data1], xmm0
0x1800ff409  lea     rcx, [rbp+140h+Uuid]; Uuid
0x1800ff410  call    cs:__imp_UuidCreate
0x1800ff417  nop     dword ptr [rax+rax+00h]
0x1800ff41c  xor     r12d, r12d
0x1800ff41f  test    eax, eax
0x1800ff421  jz      short loc_1800FF42E
0x1800ff423  cmp     eax, 720h
0x1800ff428  jnz     loc_1800FFB6E
0x1800ff42e  mov     [rbp+140h+StringUuid], r12
0x1800ff432  lea     rdx, [rbp+140h+StringUuid]; StringUuid
0x1800ff436  lea     rcx, [rbp+140h+Uuid]; Uuid
0x1800ff43d  call    cs:__imp_UuidToStringW
0x1800ff444  nop     dword ptr [rax+rax+00h]
0x1800ff449  test    eax, eax
0x1800ff44b  jnz     loc_1800FFB6E
0x1800ff451  lea     rax, [rbp+140h+StringUuid]
0x1800ff455  mov     [rbp+140h+var_180], rax
0x1800ff459  mov     [rbp+140h+var_178], 1
0x1800ff45d  xorps   xmm0, xmm0
0x1800ff460  movdqu  xmmword ptr [rbp+140h+lpBuffer], xmm0
0x1800ff465  mov     [rbp+140h+var_1A8], r12
0x1800ff469  mov     edx, 28h ; '('
0x1800ff46e  lea     rcx, [rbp+140h+lpBuffer]
0x1800ff472  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ff477  mov     ebx, r12d
0x1800ff47a  test    edi, edi
0x1800ff47c  jz      short loc_1800FF4A8
0x1800ff47e  mov     r8d, ebx
0x1800ff481  add     r8, r14
0x1800ff484  mov     rdx, [rbp+140h+lpBuffer+8]
0x1800ff488  cmp     rdx, [rbp+140h+var_1A8]
0x1800ff48c  jz      short loc_1800FF499
0x1800ff48e  mov     al, [r8]
0x1800ff491  mov     [rdx], al
0x1800ff493  inc     [rbp+140h+lpBuffer+8]
0x1800ff497  jmp     short loc_1800FF4A2
0x1800ff499  lea     rcx, [rbp+140h+lpBuffer]
0x1800ff49d  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x1800ff4a2  inc     ebx
0x1800ff4a4  cmp     ebx, edi
0x1800ff4a6  jb      short loc_1800FF47E
0x1800ff4a8  mov     r8, rsi
0x1800ff4ab  lea     rdx, [rbp+140h+lpBuffer]
0x1800ff4af  call    ?SerializeStringToBuffer@PFXCertificate@@AEAAJAEAV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; PFXCertificate::SerializeStringToBuffer(std::vector<uchar> &,std::wstring const &)
0x1800ff4b4  mov     rbx, r12
0x1800ff4b7  mov     r14d, 1
0x1800ff4bd  lea     r8, [rbp+140h+arg_28]
0x1800ff4c4  add     r8, rbx
0x1800ff4c7  mov     rdx, [rbp+140h+lpBuffer+8]
0x1800ff4cb  cmp     rdx, [rbp+140h+var_1A8]
0x1800ff4cf  jz      short loc_1800FF4DC
0x1800ff4d1  mov     al, [r8]
0x1800ff4d4  mov     [rdx], al
0x1800ff4d6  add     [rbp+140h+lpBuffer+8], r14
0x1800ff4da  jmp     short loc_1800FF4E5
0x1800ff4dc  lea     rcx, [rbp+140h+lpBuffer]
0x1800ff4e0  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x1800ff4e5  add     rbx, r14
0x1800ff4e8  cmp     rbx, 4
0x1800ff4ec  jnz     short loc_1800FF4BD
0x1800ff4ee  mov     r8, r13
0x1800ff4f1  lea     rdx, [rbp+140h+lpBuffer]
0x1800ff4f5  call    ?SerializeStringToBuffer@PFXCertificate@@AEAAJAEAV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; PFXCertificate::SerializeStringToBuffer(std::vector<uchar> &,std::wstring const &)
0x1800ff4fa  lea     r8, [r15+60h]
0x1800ff4fe  lea     rdx, [rbp+140h+lpBuffer]
0x1800ff502  call    ?SerializeStringToBuffer@PFXCertificate@@AEAAJAEAV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; PFXCertificate::SerializeStringToBuffer(std::vector<uchar> &,std::wstring const &)
0x1800ff507  mov     rcx, [rbp+140h+lpBuffer]
0x1800ff50b  mov     [rcx], rdi
0x1800ff50e  mov     rax, [rsi+10h]
0x1800ff512  lea     rax, ds:2[rax*2]
0x1800ff51a  mov     [rcx+8], rax
0x1800ff51e  mov     [rcx+10h], rbx
0x1800ff522  mov     rax, [r13+10h]
0x1800ff526  lea     rax, ds:2[rax*2]
0x1800ff52e  mov     [rcx+18h], rax
0x1800ff532  mov     rax, [r15+70h]
0x1800ff536  lea     rax, ds:2[rax*2]
0x1800ff53e  mov     [rcx+20h], rax
0x1800ff542  xorps   xmm0, xmm0
0x1800ff545  movups  [rbp+140h+var_70], xmm0
0x1800ff54c  mov     [rbp+140h+var_60], r12
0x1800ff553  lea     r13d, [rbx+3]
0x1800ff557  mov     [rbp+140h+var_58], r13
0x1800ff55e  mov     word ptr [rbp+140h+var_70], r12w
0x1800ff566  lea     rdx, [rbp+140h+var_70]
0x1800ff56d  call    ?GetCurrentUserSID@PFXCertificate@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PFXCertificate::GetCurrentUserSID(std::wstring &)
0x1800ff572  mov     esi, eax
0x1800ff574  test    eax, eax
0x1800ff576  js      loc_1800FFB45
0x1800ff57c  xorps   xmm0, xmm0
0x1800ff57f  movups  xmmword ptr [rbp+140h+StringSecurityDescriptor], xmm0
0x1800ff583  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ff58b  movdqu  [rbp+140h+var_C0], xmm1
0x1800ff593  mov     word ptr [rbp+140h+StringSecurityDescriptor], r12w
0x1800ff598  lea     ebx, [r13+11h]
0x1800ff59c  mov     r8d, ebx
0x1800ff59f  lea     rdx, aDPAFaSyAFr; "D:P(A;;FA;;;SY)(A;;FR;;;"
0x1800ff5a6  lea     rcx, [rbp+140h+StringSecurityDescriptor]; Src
0x1800ff5aa  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ff5af  lea     rdx, [rbp+140h+var_70]
0x1800ff5b6  cmp     [rbp+140h+var_58], r13
0x1800ff5bd  cmova   rdx, qword ptr [rbp+140h+var_70]
0x1800ff5c5  mov     r8, [rbp+140h+var_60]
0x1800ff5cc  lea     rcx, [rbp+140h+StringSecurityDescriptor]; Src
0x1800ff5d0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ff5d5  mov     r8, r14
0x1800ff5d8  lea     rdx, asc_18012AA8C; ")"
0x1800ff5df  lea     rcx, [rbp+140h+StringSecurityDescriptor]; Src
0x1800ff5e3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ff5e8  xorps   xmm0, xmm0
0x1800ff5eb  xor     eax, eax
0x1800ff5ed  movups  xmmword ptr [rbp+140h+SecurityDescriptor], xmm0
0x1800ff5f1  mov     [rbp+140h+var_160], rax
0x1800ff5f5  mov     dword ptr [rbp+140h+SecurityDescriptor], ebx
0x1800ff5f8  mov     dword ptr [rbp+140h+var_160], r12d
0x1800ff5fc  lea     rcx, [rbp+140h+StringSecurityDescriptor]
0x1800ff600  cmp     qword ptr [rbp+140h+var_C0+8], r13
0x1800ff607  cmova   rcx, [rbp+140h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800ff60c  xor     r9d, r9d; SecurityDescriptorSize
0x1800ff60f  lea     r8, [rbp+140h+SecurityDescriptor+8]; SecurityDescriptor
0x1800ff613  mov     edx, r14d; StringSDRevision
0x1800ff616  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ff61d  nop     dword ptr [rax+rax+00h]
0x1800ff622  test    eax, eax
0x1800ff624  jnz     short loc_1800FF64A
0x1800ff626  call    cs:__imp_GetLastError
0x1800ff62d  nop     dword ptr [rax+rax+00h]
0x1800ff632  mov     esi, eax
0x1800ff634  test    eax, eax
0x1800ff636  jle     loc_1800FFB3B
0x1800ff63c  movzx   esi, ax
0x1800ff63f  or      esi, 80070000h
0x1800ff645  jmp     loc_1800FFB3B
0x1800ff64a  lea     rdx, aPipe; "\\\\.\\pipe\\"
0x1800ff651  lea     rcx, [rbp+140h+lpName]
0x1800ff658  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ff65d  nop
0x1800ff65e  mov     rdx, [rbp+140h+StringUuid]
0x1800ff662  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ff666  inc     r8
0x1800ff669  cmp     [rdx+r8*2], r12w
0x1800ff66e  jnz     short loc_1800FF666
0x1800ff670  lea     rcx, [rbp+140h+lpName]; Src
0x1800ff677  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ff67c  mov     rax, [rbp+140h+lpBuffer+8]
0x1800ff680  lea     rcx, [rbp+140h+lpName]
0x1800ff687  cmp     [rbp+140h+var_98], r13
0x1800ff68e  cmova   rcx, [rbp+140h+lpName]; lpName
0x1800ff696  sub     eax, dword ptr [rbp+140h+lpBuffer]
0x1800ff699  lea     rdx, [rbp+140h+SecurityDescriptor]
0x1800ff69d  mov     [rsp+240h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x1800ff6a2  mov     [rsp+240h+nDefaultTimeOut], r12d; nDefaultTimeOut
0x1800ff6a7  mov     [rsp+240h+nInBufferSize], r12d; nInBufferSize
0x1800ff6ac  mov     [rsp+240h+nOutBufferSize], eax; nOutBufferSize
0x1800ff6b0  mov     r9d, r14d; nMaxInstances
0x1800ff6b3  mov     edx, 80002h; dwOpenMode
0x1800ff6b8  mov     r8d, 0Eh; dwPipeMode
0x1800ff6be  call    cs:__imp_CreateNamedPipeW
0x1800ff6c5  nop     dword ptr [rax+rax+00h]
0x1800ff6ca  mov     rbx, rax
0x1800ff6cd  mov     [rbp+140h+var_1C0], rax
0x1800ff6d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ff6d5  jnz     short loc_1800FF6FB
0x1800ff6d7  call    cs:__imp_GetLastError
0x1800ff6de  nop     dword ptr [rax+rax+00h]
0x1800ff6e3  mov     esi, eax
0x1800ff6e5  test    eax, eax
0x1800ff6e7  jle     loc_1800FFB24
0x1800ff6ed  movzx   esi, ax
0x1800ff6f0  or      esi, 80070000h
0x1800ff6f6  jmp     loc_1800FFB24
0x1800ff6fb  lea     rdx, aXN; "-x -n "
0x1800ff702  lea     rcx, [rbp+140h+lpCommandLine]
0x1800ff709  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ff70e  nop
0x1800ff70f  lea     rdx, [rbp+140h+lpName]
0x1800ff716  cmp     [rbp+140h+var_98], r13
0x1800ff71d  cmova   rdx, [rbp+140h+lpName]
0x1800ff725  mov     r8, [rbp+140h+var_A0]
0x1800ff72c  lea     rcx, [rbp+140h+lpCommandLine]; Src
0x1800ff733  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ff738  xorps   xmm0, xmm0
0x1800ff73b  movdqu  xmmword ptr [rsp+240h+lpDst], xmm0
0x1800ff741  mov     [rsp+240h+var_1D0], r12
0x1800ff746  xor     r8d, r8d; nSize
0x1800ff749  xor     edx, edx; lpDst
0x1800ff74b  lea     rcx, aWindirSystem32; "%windir%\\system32\\dmcertinst.exe "
0x1800ff752  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ff759  nop     dword ptr [rax+rax+00h]
0x1800ff75e  mov     r15d, eax
0x1800ff761  mov     rdx, [rsp+240h+lpDst]
0x1800ff766  mov     r14, [rsp+240h+lpDst+8]
0x1800ff76b  mov     rcx, r14
0x1800ff76e  sub     rcx, rdx
0x1800ff771  sar     rcx, 1
0x1800ff774  mov     edi, eax
0x1800ff776  cmp     r15, rcx
0x1800ff779  jnb     short loc_1800FF786
0x1800ff77b  lea     rcx, [rdx+r15*2]
0x1800ff77f  mov     [rsp+240h+lpDst+8], rcx
0x1800ff784  jmp     short loc_1800FF7C3
0x1800ff786  jbe     short loc_1800FF7C3
0x1800ff788  mov     rax, [rsp+240h+var_1D0]
0x1800ff78d  sub     rax, rdx
0x1800ff790  sar     rax, 1
0x1800ff793  cmp     rdi, rax
0x1800ff796  jbe     short loc_1800FF7A7
0x1800ff798  mov     rdx, rdi
0x1800ff79b  lea     rcx, [rsp+240h+lpDst]
0x1800ff7a0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ff7a5  jmp     short loc_1800FF7C3
0x1800ff7a7  sub     rdi, rcx
0x1800ff7aa  add     rdi, rdi
0x1800ff7ad  mov     r8, rdi; Size
0x1800ff7b0  xor     edx, edx; Val
0x1800ff7b2  mov     rcx, r14; void *
0x1800ff7b5  call    memset_0
0x1800ff7ba  lea     rax, [r14+rdi]
0x1800ff7be  mov     [rsp+240h+lpDst+8], rax
0x1800ff7c3  mov     r8d, r15d; nSize
0x1800ff7c6  mov     rdx, [rsp+240h+lpDst]; lpDst
0x1800ff7cb  lea     rcx, aWindirSystem32; "%windir%\\system32\\dmcertinst.exe "
0x1800ff7d2  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ff7d9  nop     dword ptr [rax+rax+00h]
0x1800ff7de  test    eax, eax
0x1800ff7e0  jnz     short loc_1800FF806
0x1800ff7e2  call    cs:__imp_GetLastError
0x1800ff7e9  nop     dword ptr [rax+rax+00h]
0x1800ff7ee  mov     esi, eax
0x1800ff7f0  test    eax, eax
0x1800ff7f2  jle     loc_1800FFAEC
0x1800ff7f8  movzx   esi, ax
0x1800ff7fb  or      esi, 80070000h
0x1800ff801  jmp     loc_1800FFAEC
0x1800ff806  mov     [rsp+240h+TokenHandle], r12
0x1800ff80b  xor     edx, edx
0x1800ff80d  lea     rcx, [rsp+240h+TokenHandle]
0x1800ff812  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ff817  call    cs:__imp_GetCurrentThread
0x1800ff81e  nop     dword ptr [rax+rax+00h]
0x1800ff823  lea     r9, [rsp+240h+TokenHandle]; TokenHandle
0x1800ff828  mov     edx, 0Bh; DesiredAccess
0x1800ff82d  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x1800ff831  mov     rcx, rax; ThreadHandle
0x1800ff834  call    cs:__imp_OpenThreadToken
0x1800ff83b  nop     dword ptr [rax+rax+00h]
0x1800ff840  test    eax, eax
0x1800ff842  jnz     short loc_1800FF868
0x1800ff844  call    cs:__imp_GetLastError
0x1800ff84b  nop     dword ptr [rax+rax+00h]
0x1800ff850  mov     esi, eax
0x1800ff852  test    eax, eax
0x1800ff854  jle     loc_1800FFAE1
0x1800ff85a  movzx   esi, ax
0x1800ff85d  or      esi, 80070000h
0x1800ff863  jmp     loc_1800FFAE1
0x1800ff868  xorps   xmm0, xmm0
0x1800ff86b  xor     eax, eax
0x1800ff86d  movups  xmmword ptr [rbp+140h+ProcessInformation.hProcess], xmm0
0x1800ff871  mov     qword ptr [rbp+140h+ProcessInformation.dwProcessId], rax
0x1800ff875  lea     edi, [rax+68h]
0x1800ff878  mov     r8d, edi; Size
0x1800ff87b  xor     edx, edx; Val
0x1800ff87d  lea     rcx, [rbp+140h+StartupInfo]; void *
0x1800ff881  call    memset_0
0x1800ff886  mov     [rbp+140h+StartupInfo.cb], edi
0x1800ff889  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x1800ff890  mov     [rbp+140h+StartupInfo.lpDesktop], rax
0x1800ff894  mov     eax, cs:dword_180155A70
0x1800ff89a  lea     rdi, dword_180155A70
0x1800ff8a1  cmp     eax, 5
0x1800ff8a4  jbe     short loc_1800FF8C9
0x1800ff8a6  lea     rax, aLaunchingDmcer_0; "Launching dmcertinst.exe process as use"...
0x1800ff8ad  mov     [rbp+140h+var_190], rax
0x1800ff8b1  lea     rax, [rbp+140h+var_190]
0x1800ff8b5  mov     qword ptr [rsp+240h+nOutBufferSize], rax
0x1800ff8ba  lea     rdx, byte_18013BDE1
0x1800ff8c1  mov     rcx, rdi
0x1800ff8c4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800ff8c9  lea     r8, [rbp+140h+lpCommandLine]
  ... truncated ...
```
