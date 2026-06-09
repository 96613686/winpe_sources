# _lambda_b053858f74dd62c6928af3f449cbe1f6_::operator()(Windows::Internal::CNoResult &)

- ea: `0x180093a6c`
- end: `0x180093d25`
- name: `??R_lambda_b053858f74dd62c6928af3f449cbe1f6_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180094570`

## callees

- `0x180008524`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x1800230b0`
- `0x180047300`
- `0x180053e5c`
- `0x18007fb9c`
- `0x18008e3e4`
- `0x180093a6c`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093a8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093c31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093a8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093c31`
- `api-ms-win-core-localization-l1-2-0!EnumSystemGeoID` at `0x180093ac8`
- `api-ms-win-core-localization-l1-2-0!EnumSystemGeoID` at `0x180093ac8`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x180093c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093c93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093c93`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180093c85`

## string_xrefs

- `0x180093ad6`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180093b3b`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180093ba1`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180093c01`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180093c6a`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180093cb4`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180093ce7`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_b053858f74dd62c6928af3f449cbe1f6_::operator()(HSTRING *a1, __int64 a2)
{
  RTL_SRWLOCK *v3; // rbx
  const char *v4; // r9
  unsigned int LastError; // ebx
  unsigned int v6; // r15d
  void *v7; // rbx
  int v8; // eax
  __int64 (__fastcall *v9)(void *, _QWORD, HSTRING *, __int64 *); // rdi
  int v10; // eax
  HSTRING v11; // rsi
  char v12; // di
  BOOL (__stdcall *v13)(GEOID); // rax
  const char *v14; // r9
  __int64 (__fastcall *v15)(PCWSTR, __int64); // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v20; // [rsp+20h] [rbp-28h]
  HSTRING v21; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  HSTRING string; // [rsp+80h] [rbp+38h] BYREF
  __int64 v24; // [rsp+88h] [rbp+40h] BYREF
  void *v25; // [rsp+90h] [rbp+48h] BYREF
  RTL_SRWLOCK *v26; // [rsp+98h] [rbp+50h] BYREF

  v24 = a2;
  v3 = (RTL_SRWLOCK *)(*a1 + 32);
  AcquireSRWLockExclusive(v3);
  v26 = v3;
  v21 = a1[2];
  Microsoft::WRL::Wrappers::HString::Set((HSTRING *)*a1 + 17, &v21);
  CloudExperienceHostAPI::OobeRegionManagerStatics::s_InstanceSearchingForGeoId = (struct CloudExperienceHostAPI::OobeRegionManagerStatics *)*a1;
  if ( EnumSystemGeoID(0x10u, 0, CloudExperienceHostAPI::OobeRegionManagerStatics::FindRegionEnumProc) )
  {
    v6 = *((_DWORD *)*a1 + 36);
    *((_DWORD *)*a1 + 36) = 0;
    CloudExperienceHostAPI::OobeRegionManagerStatics::s_InstanceSearchingForGeoId = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
    if ( !v6 )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
        (const char *)0x8000FFFFLL,
        v20);
      return LastError;
    }
    v7 = (void *)*((_QWORD *)*a1 + 13);
    v25 = v7;
    if ( v7 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
      v7 = v25;
    }
    if ( !v7 )
    {
      v25 = 0;
      v8 = CloudExperienceHostCreateElevatedObject(
             &GUID_fd5a78d9_c2f5_45ff_9097_c615acd0aa51,
             &GUID_9c8fba4f_b489_4018_962a_3a563e318f00,
             &v25);
      LastError = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
          (const char *)(unsigned int)v8,
          v20);
LABEL_26:
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v25);
        return LastError;
      }
      v7 = v25;
    }
    LOBYTE(v24) = 0;
    string = 0;
    v9 = *(__int64 (__fastcall **)(void *, _QWORD, HSTRING *, __int64 *))(*(_QWORD *)v7 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v7, v6, &string, &v24);
    LastError = v10;
    if ( v10 >= 0 )
    {
      v11 = a1[1];
      v12 = v24;
      AcquireSRWLockExclusive((PSRWLOCK)v11 + 8);
      v26 = (RTL_SRWLOCK *)(v11 + 16);
      *((_BYTE *)v11 + 72) = v12;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
      v13 = (BOOL (__stdcall *)(GEOID))*((_QWORD *)*a1 + 15);
      if ( !v13 )
        v13 = SetUserGeoID;
      if ( !((unsigned int (__fastcall *)(_QWORD))v13)(v6) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xB6,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
          v14);
      v15 = (__int64 (__fastcall *)(PCWSTR, __int64))*((_QWORD *)*a1 + 14);
      if ( !v15 )
        v15 = (__int64 (__fastcall *)(PCWSTR, __int64))NlsUpdateLocale;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v17 = v15(StringRawBuffer, 1);
      if ( !v17 )
      {
        v18 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v25 + 56LL))(v25);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xC0,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
            (const char *)(unsigned int)v18,
            v20);
        WindowsDeleteString(string);
        LastError = 0;
        goto LABEL_25;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xBD,
                    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
                    (const char *)v17,
                    v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
        (const char *)(unsigned int)v10,
        v20);
    }
    WindowsDeleteString(string);
LABEL_25:
    string = 0;
    goto LABEL_26;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x9F,
                (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
                v4);
  CloudExperienceHostAPI::OobeRegionManagerStatics::s_InstanceSearchingForGeoId = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
  return LastError;
}

```

## disassembly

```asm
0x180093a6c  mov     [rsp-30h+arg_8], rdx
0x180093a71  push    rbp
0x180093a72  push    rbx
0x180093a73  push    rsi
0x180093a74  push    rdi
0x180093a75  push    r14
0x180093a77  push    r15
0x180093a79  mov     rbp, rsp
0x180093a7c  sub     rsp, 48h
0x180093a80  mov     r14, rcx
0x180093a83  mov     rbx, [rcx]
0x180093a86  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180093a8a  mov     rcx, rbx; SRWLock
0x180093a8d  call    cs:__imp_AcquireSRWLockExclusive
0x180093a93  mov     [rbp+arg_18], rbx
0x180093a97  mov     rax, [r14+10h]
0x180093a9b  mov     [rbp+var_18], rax
0x180093a9f  mov     rcx, [r14]
0x180093aa2  add     rcx, 88h; newString
0x180093aa9  lea     rdx, [rbp+var_18]; HSTRING *
0x180093aad  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180093ab2  mov     rax, [r14]
0x180093ab5  mov     cs:?s_InstanceSearchingForGeoId@OobeRegionManagerStatics@CloudExperienceHostAPI@@0PEAV12@EA, rax; CloudExperienceHostAPI::OobeRegionManagerStatics * CloudExperienceHostAPI::OobeRegionManagerStatics::s_InstanceSearchingForGeoId
0x180093abc  lea     r8, ?FindRegionEnumProc@OobeRegionManagerStatics@CloudExperienceHostAPI@@CAHJ@Z; lpGeoEnumProc
0x180093ac3  xor     edx, edx; ParentGeoId
0x180093ac5  lea     ecx, [rdx+10h]; GeoClass
0x180093ac8  call    cs:__imp_EnumSystemGeoID
0x180093ace  test    eax, eax
0x180093ad0  jnz     short loc_180093B02
0x180093ad2  mov     rcx, [rbp+30h]; this
0x180093ad6  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093add  mov     edx, 9Fh; void *
0x180093ae2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180093ae7  mov     ebx, eax
0x180093ae9  mov     cs:?s_InstanceSearchingForGeoId@OobeRegionManagerStatics@CloudExperienceHostAPI@@0PEAV12@EA, 0; CloudExperienceHostAPI::OobeRegionManagerStatics * CloudExperienceHostAPI::OobeRegionManagerStatics::s_InstanceSearchingForGeoId
0x180093af4  lea     rcx, [rbp+arg_18]
0x180093af8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180093afd  jmp     loc_180093D16
0x180093b02  mov     rax, [r14]
0x180093b05  mov     r15d, [rax+90h]
0x180093b0c  mov     dword ptr [rax+90h], 0
0x180093b16  mov     cs:?s_InstanceSearchingForGeoId@OobeRegionManagerStatics@CloudExperienceHostAPI@@0PEAV12@EA, 0; CloudExperienceHostAPI::OobeRegionManagerStatics * CloudExperienceHostAPI::OobeRegionManagerStatics::s_InstanceSearchingForGeoId
0x180093b21  lea     rcx, [rbp+arg_18]
0x180093b25  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180093b2a  test    r15d, r15d
0x180093b2d  jnz     short loc_180093B51
0x180093b2f  mov     rcx, [rbp+30h]; this
0x180093b33  mov     ebx, 8000FFFFh
0x180093b38  mov     r9d, ebx; char *
0x180093b3b  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093b42  mov     edx, 0A4h; void *
0x180093b47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093b4c  jmp     loc_180093D16
0x180093b51  mov     rbx, [r14]
0x180093b54  mov     rbx, [rbx+68h]
0x180093b58  mov     [rbp+arg_10], rbx
0x180093b5c  test    rbx, rbx
0x180093b5f  jz      short loc_180093B74
0x180093b61  mov     rax, [rbx]
0x180093b64  mov     rcx, rbx
0x180093b67  mov     rax, [rax+8]
0x180093b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b70  mov     rbx, [rbp+arg_10]
0x180093b74  test    rbx, rbx
0x180093b77  jnz     short loc_180093BBB
0x180093b79  mov     [rbp+arg_10], rbx
0x180093b7d  lea     r8, [rbp+arg_10]; void **
0x180093b81  lea     rdx, _GUID_9c8fba4f_b489_4018_962a_3a563e318f00; struct _GUID *
0x180093b88  lea     rcx, _GUID_fd5a78d9_c2f5_45ff_9097_c615acd0aa51; struct _GUID *
0x180093b8f  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x180093b94  mov     ebx, eax
0x180093b96  test    eax, eax
0x180093b98  jns     short loc_180093BB7
0x180093b9a  mov     rcx, [rbp+30h]; this
0x180093b9e  mov     r9d, eax; char *
0x180093ba1  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093ba8  mov     edx, 0A9h; void *
0x180093bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093bb2  jmp     loc_180093D0D
0x180093bb7  mov     rbx, [rbp+arg_10]
0x180093bbb  mov     byte ptr [rbp+arg_8], 0
0x180093bbf  mov     [rbp+string], 0
0x180093bc7  mov     rax, [rbx]
0x180093bca  mov     rdi, [rax+30h]
0x180093bce  xor     ecx, ecx; string
0x180093bd0  call    cs:__imp_WindowsDeleteString
0x180093bd6  mov     [rbp+string], 0
0x180093bde  lea     r9, [rbp+arg_8]
0x180093be2  lea     r8, [rbp+string]
0x180093be6  mov     edx, r15d
0x180093be9  mov     rcx, rbx
0x180093bec  mov     rax, rdi
0x180093bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093bf4  mov     ebx, eax
0x180093bf6  test    eax, eax
0x180093bf8  jns     short loc_180093C22
0x180093bfa  mov     rcx, [rbp+30h]; this
0x180093bfe  mov     r9d, eax; char *
0x180093c01  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093c08  mov     edx, 0AEh; void *
0x180093c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093c12  nop
0x180093c13  mov     rcx, [rbp+string]; string
0x180093c17  call    cs:__imp_WindowsDeleteString
0x180093c1d  jmp     loc_180093D05
0x180093c22  mov     rsi, [r14+8]
0x180093c26  mov     dil, byte ptr [rbp+arg_8]
0x180093c2a  lea     rbx, [rsi+40h]
0x180093c2e  mov     rcx, rbx; SRWLock
0x180093c31  call    cs:__imp_AcquireSRWLockExclusive
0x180093c37  mov     [rbp+arg_18], rbx
0x180093c3b  mov     [rsi+48h], dil
0x180093c3f  lea     rcx, [rbp+arg_18]
0x180093c43  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180093c48  mov     rax, [r14]
0x180093c4b  mov     rax, [rax+78h]
0x180093c4f  test    rax, rax
0x180093c52  cmovz   rax, cs:__imp_SetUserGeoID
0x180093c5a  mov     ecx, r15d
0x180093c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c62  mov     rcx, [rbp+30h]; this
0x180093c66  test    eax, eax
0x180093c68  jnz     short loc_180093C7B
0x180093c6a  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093c71  mov     edx, 0B6h; void *
0x180093c76  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180093c7b  mov     rax, [r14]
0x180093c7e  mov     rbx, [rax+70h]
0x180093c82  test    rbx, rbx
0x180093c85  cmovz   rbx, cs:__imp_NlsUpdateLocale
0x180093c8d  xor     edx, edx; length
0x180093c8f  mov     rcx, [rbp+string]; string
0x180093c93  call    cs:__imp_WindowsGetStringRawBuffer
0x180093c99  mov     edx, 1
0x180093c9e  mov     rcx, rax
0x180093ca1  mov     rax, rbx
0x180093ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ca9  test    eax, eax
0x180093cab  jz      short loc_180093CCC
0x180093cad  mov     rcx, [rbp+30h]; this
0x180093cb1  mov     r9d, eax; char *
0x180093cb4  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093cbb  mov     edx, 0BDh; void *
0x180093cc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180093cc5  mov     ebx, eax
0x180093cc7  jmp     loc_180093C13
0x180093ccc  mov     rcx, [rbp+arg_10]
0x180093cd0  mov     rax, [rcx]
0x180093cd3  mov     rax, [rax+38h]
0x180093cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cdc  mov     rcx, [rbp+30h]; this
0x180093ce0  test    eax, eax
0x180093ce2  jns     short loc_180093CF9
0x180093ce4  mov     r9d, eax; char *
0x180093ce7  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x180093cee  mov     edx, 0C0h; void *
0x180093cf3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093cf8  nop
0x180093cf9  mov     rcx, [rbp+string]; string
0x180093cfd  call    cs:__imp_WindowsDeleteString
0x180093d03  xor     ebx, ebx
0x180093d05  mov     [rbp+string], 0
0x180093d0d  lea     rcx, [rbp+arg_10]
0x180093d11  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180093d16  mov     eax, ebx
0x180093d18  add     rsp, 48h
0x180093d1c  pop     r15
0x180093d1e  pop     r14
0x180093d20  pop     rdi
0x180093d21  pop     rsi
0x180093d22  pop     rbx
0x180093d23  pop     rbp
0x180093d24  retn
```
