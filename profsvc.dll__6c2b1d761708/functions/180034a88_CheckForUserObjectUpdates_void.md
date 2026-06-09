# CheckForUserObjectUpdates(void)

- ea: `0x180034a88`
- end: `0x180034e09`
- name: `?CheckForUserObjectUpdates@@YAJXZ`
- size: `897`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180034a70`

## callees

- `0x180004330`
- `0x180005330`
- `0x1800084bc`
- `0x180011c40`
- `0x18001a680`
- `0x180024260`
- `0x180026e5c`
- `0x1800283bc`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x180034a88`
- `0x180034e10`
- `0x18003bc70`
- `0x18003fdd8`
- `0x18003fe48`
- `0x18003fe6c`
- `0x18003ff28`
- `0x180040060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034af9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034af9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034d26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034d26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034adf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180034bfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180034bfc`
- `logoncli!DsGetDcNameW` at `0x180034c65`
- `logoncli!DsGetDcNameW` at `0x180034c9e`
- `logoncli!DsGetDcNameW` at `0x180034c65`
- `logoncli!DsGetDcNameW` at `0x180034c9e`
- `samcli!NetUserGetInfo` at `0x180034cde`
- `samcli!NetUserGetInfo` at `0x180034cde`

## string_xrefs

- `0x180034b0d`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x180034b5a`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x180034bd5`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x180034c7a`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x180034d3a`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 CheckForUserObjectUpdates(void)
{
  HANDLE CurrentThread; // rax
  const char *v1; // r9
  signed int LastError; // ebx
  int SidString; // eax
  __int64 v4; // rdx
  int UserNameAndDomain; // eax
  DWORD DcNameW; // eax
  __int64 v7; // rdx
  int v8; // edx
  const char *v9; // r9
  ULONG Flags; // [rsp+20h] [rbp-49h]
  ULONG Flagsa; // [rsp+20h] [rbp-49h]
  DWORD nSize; // [rsp+30h] [rbp-39h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR username; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR DomainName; // [rsp+50h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-11h] BYREF
  __int64 v19; // [rsp+60h] [rbp-9h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-1h] BYREF
  __int64 v21; // [rsp+70h] [rbp+7h]
  __int64 v22; // [rsp+78h] [rbp+Fh]
  __int64 *v23; // [rsp+80h] [rbp+17h] BYREF
  LPBYTE bufptr; // [rsp+88h] [rbp+1Fh] BYREF
  char v25; // [rsp+90h] [rbp+27h]
  WCHAR Buffer[16]; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  nSize = -1;
  if ( (unsigned int)GetMachineRole((int *)&nSize) && nSize )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x90,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cachedlogon.cpp",
                    v1);
LABEL_31:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return (unsigned int)LastError;
    }
    lpString1 = 0;
    v21 = 0;
    v22 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpString1);
    v21 = -1;
    v22 = -1;
    SidString = GetSidString(TokenHandle, (unsigned __int16 **)&lpString1);
    LastError = SidString;
    if ( SidString < 0 )
    {
      v4 = 147;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cachedlogon.cpp",
        (const char *)(unsigned int)SidString,
        Flags);
LABEL_30:
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpString1);
      goto LABEL_31;
    }
    nSize = 0;
    SidString = GetNextLogonCacheable(lpString1, (int *)&nSize);
    LastError = SidString;
    if ( SidString < 0 )
    {
      v4 = 150;
      goto LABEL_7;
    }
    if ( nSize )
    {
      username = 0;
      v15 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v15,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &username,
        0);
      UserNameAndDomain = GetUserNameAndDomain(NameSamCompatible, (unsigned __int16 **)&username, &v15);
      LastError = UserNameAndDomain;
      if ( UserNameAndDomain < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cachedlogon.cpp",
          (const char *)(unsigned int)UserNameAndDomain,
          Flags);
LABEL_29:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&username);
        goto LABEL_30;
      }
      nSize = 16;
      if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) || !StringIsEqual(v15, Buffer) )
      {
        DomainName = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &DomainName,
          0);
        GetUserNameAndDomain(NameDnsDomain, 0, (unsigned __int16 **)&DomainName);
        DomainControllerInfo = 0;
        if ( DomainName )
        {
          DcNameW = DsGetDcNameW(0, DomainName, 0, 0, 0x20100u, &DomainControllerInfo);
          if ( DcNameW )
          {
            v7 = 183;
LABEL_18:
            LastError = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)v7,
                          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cachedlogon.cpp",
                          (const char *)DcNameW,
                          Flagsa);
LABEL_28:
            wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(&DomainControllerInfo);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&DomainName);
            goto LABEL_29;
          }
        }
        else
        {
          DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x100u, &DomainControllerInfo);
          if ( DcNameW )
          {
            v7 = 192;
            goto LABEL_18;
          }
        }
        v19 = 0;
        v23 = &v19;
        bufptr = 0;
        v25 = 1;
        LastError = NetUserGetInfo(DomainControllerInfo->DomainControllerName, username, 3u, &bufptr);
        wil::details::out_param_ptr_t<unsigned char * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_3 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_3 *,_USER_INFO_3 *,0,std::nullptr_t>>>>::~out_param_ptr_t<unsigned char * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_3 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_3 *,_USER_INFO_3 *,0,std::nullptr_t>>>>(&v23);
        if ( LastError )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_27;
        }
        if ( !(unsigned int)AllowCachedLogon(
                              *(const unsigned __int16 **)(v19 + 160),
                              *(const unsigned __int16 **)(v19 + 24),
                              TokenHandle) )
        {
          if ( !SetThreadToken(0, 0) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xD3,
                          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cachedlogon.cpp",
                          v9);
LABEL_27:
            wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(&v19);
            goto LABEL_28;
          }
          SetNextLogonCacheable(lpString1, v8);
        }
        wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(&v19);
        wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(&DomainControllerInfo);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&DomainName);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&username);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpString1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x180034a88  mov     [rsp-8+arg_0], rbx
0x180034a8d  mov     [rsp-8+arg_8], rdi
0x180034a92  push    rbp
0x180034a93  lea     rbp, [rsp-57h]
0x180034a98  sub     rsp, 0C0h
0x180034a9f  mov     rax, cs:__security_cookie
0x180034aa6  xor     rax, rsp
0x180034aa9  mov     [rbp+57h+var_8], rax
0x180034aad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034ab1  mov     [rbp+57h+nSize], ebx
0x180034ab4  lea     rcx, [rbp+57h+nSize]; int *
0x180034ab8  call    ?GetMachineRole@@YAHPEAH@Z; GetMachineRole(int *)
0x180034abd  xor     edi, edi
0x180034abf  test    eax, eax
0x180034ac1  jz      loc_180034DE5
0x180034ac7  cmp     [rbp+57h+nSize], edi
0x180034aca  jz      loc_180034DE5
0x180034ad0  mov     [rbp+57h+TokenHandle], rdi
0x180034ad4  xor     edx, edx
0x180034ad6  lea     rcx, [rbp+57h+TokenHandle]
0x180034ada  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180034adf  call    cs:__imp_GetCurrentThread
0x180034ae6  nop     dword ptr [rax+rax+00h]
0x180034aeb  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180034aef  lea     edx, [rbx+9]; DesiredAccess
0x180034af2  lea     r8d, [rbx+2]; OpenAsSelf
0x180034af6  mov     rcx, rax; ThreadHandle
0x180034af9  call    cs:__imp_OpenThreadToken
0x180034b00  nop     dword ptr [rax+rax+00h]
0x180034b05  test    eax, eax
0x180034b07  jnz     short loc_180034B25
0x180034b09  mov     rcx, [rbp+5Fh]; this
0x180034b0d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034b14  mov     edx, 90h; void *
0x180034b19  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034b1e  mov     ebx, eax
0x180034b20  jmp     loc_180034D89
0x180034b25  mov     [rbp+57h+lpString1], rdi
0x180034b29  mov     [rbp+57h+var_50], rdi
0x180034b2d  mov     [rbp+57h+var_48], rdi
0x180034b31  lea     rcx, [rbp+57h+lpString1]
0x180034b35  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180034b3a  mov     [rbp+57h+var_50], rbx
0x180034b3e  mov     [rbp+57h+var_48], rbx
0x180034b42  lea     rdx, [rbp+57h+lpString1]; unsigned __int16 **
0x180034b46  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180034b4a  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x180034b4f  mov     ebx, eax
0x180034b51  test    eax, eax
0x180034b53  jns     short loc_180034B72
0x180034b55  mov     edx, 93h; void *
0x180034b5a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034b61  mov     r9d, eax; char *
0x180034b64  mov     rcx, [rbp+5Fh]; this
0x180034b68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034b6d  jmp     loc_180034D7F
0x180034b72  mov     [rbp+57h+nSize], edi
0x180034b75  lea     rdx, [rbp+57h+nSize]; int *
0x180034b79  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180034b7d  call    ?GetNextLogonCacheable@@YAJPEBGPEAH@Z; GetNextLogonCacheable(ushort const *,int *)
0x180034b82  mov     ebx, eax
0x180034b84  test    eax, eax
0x180034b86  jns     short loc_180034B8F
0x180034b88  mov     edx, 96h
0x180034b8d  jmp     short loc_180034B5A
0x180034b8f  cmp     [rbp+57h+nSize], edi
0x180034b92  jz      loc_180034DD2
0x180034b98  mov     [rbp+57h+username], rdi
0x180034b9c  mov     [rbp+57h+var_80], rdi
0x180034ba0  xor     edx, edx
0x180034ba2  lea     rcx, [rbp+57h+var_80]
0x180034ba6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034bab  xor     edx, edx
0x180034bad  lea     rcx, [rbp+57h+username]
0x180034bb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034bb6  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x180034bba  lea     rdx, [rbp+57h+username]; unsigned __int16 **
0x180034bbe  mov     ecx, 2; NameFormat
0x180034bc3  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180034bc8  mov     ebx, eax
0x180034bca  test    eax, eax
0x180034bcc  jns     short loc_180034BEB
0x180034bce  mov     rcx, [rbp+5Fh]; this
0x180034bd2  mov     r9d, eax; char *
0x180034bd5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034bdc  mov     edx, 9Eh; void *
0x180034be1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034be6  jmp     loc_180034D6B
0x180034beb  mov     [rbp+57h+nSize], 10h
0x180034bf2  lea     r8, [rbp+57h+nSize]; nSize
0x180034bf6  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180034bfa  xor     ecx, ecx; NameType
0x180034bfc  call    cs:__imp_GetComputerNameExW
0x180034c03  nop     dword ptr [rax+rax+00h]
0x180034c08  test    eax, eax
0x180034c0a  jz      short loc_180034C21
0x180034c0c  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x180034c10  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180034c14  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180034c19  test    eax, eax
0x180034c1b  jnz     loc_180034DBE
0x180034c21  mov     [rbp+57h+DomainName], rdi
0x180034c25  xor     edx, edx
0x180034c27  lea     rcx, [rbp+57h+DomainName]
0x180034c2b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034c30  lea     r8, [rbp+57h+DomainName]; unsigned __int16 **
0x180034c34  xor     edx, edx; unsigned __int16 **
0x180034c36  lea     ecx, [rdx+0Ch]; NameFormat
0x180034c39  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180034c3e  nop
0x180034c3f  mov     rdx, [rbp+57h+DomainName]; DomainName
0x180034c43  mov     [rbp+57h+var_88], rdi
0x180034c47  lea     rax, [rbp+57h+var_88]
0x180034c4b  xor     r9d, r9d; SiteName
0x180034c4e  xor     r8d, r8d; DomainGuid
0x180034c51  xor     ecx, ecx; ComputerName
0x180034c53  mov     [rsp+0C0h+DomainControllerInfo], rax; DomainControllerInfo
0x180034c58  test    rdx, rdx
0x180034c5b  jz      short loc_180034C94
0x180034c5d  mov     [rsp+0C0h+Flags], 20100h; unsigned int
0x180034c65  call    cs:__imp_DsGetDcNameW
0x180034c6c  nop     dword ptr [rax+rax+00h]
0x180034c71  test    eax, eax
0x180034c73  jz      short loc_180034CB5
0x180034c75  mov     edx, 0B7h; void *
0x180034c7a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034c81  mov     r9d, eax; char *
0x180034c84  mov     rcx, [rbp+5Fh]; this
0x180034c88  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034c8d  mov     ebx, eax
0x180034c8f  jmp     loc_180034D57
0x180034c94  mov     [rsp+0C0h+Flags], 100h; Flags
0x180034c9c  xor     edx, edx; DomainName
0x180034c9e  call    cs:__imp_DsGetDcNameW
0x180034ca5  nop     dword ptr [rax+rax+00h]
0x180034caa  test    eax, eax
0x180034cac  jz      short loc_180034CB5
0x180034cae  mov     edx, 0C0h
0x180034cb3  jmp     short loc_180034C7A
0x180034cb5  mov     [rbp+57h+var_60], rdi
0x180034cb9  lea     rax, [rbp+57h+var_60]
0x180034cbd  mov     [rbp+57h+var_40], rax
0x180034cc1  mov     [rbp+57h+bufptr], rdi
0x180034cc5  mov     [rbp+57h+var_30], 1
0x180034cc9  lea     r9, [rbp+57h+bufptr]; bufptr
0x180034ccd  mov     r8d, 3; level
0x180034cd3  mov     rdx, [rbp+57h+username]; username
0x180034cd7  mov     rcx, [rbp+57h+var_88]
0x180034cdb  mov     rcx, [rcx]; servername
0x180034cde  call    cs:__imp_NetUserGetInfo
0x180034ce5  nop     dword ptr [rax+rax+00h]
0x180034cea  mov     ebx, eax
0x180034cec  lea     rcx, [rbp+57h+var_40]
0x180034cf0  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_USER_INFO_3@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_3 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_3 *,_USER_INFO_3 *,0,std::nullptr_t>>>>::~out_param_ptr_t<uchar * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_3 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_3 *,_USER_INFO_3 *,0,std::nullptr_t>>>>(void)
0x180034cf5  test    ebx, ebx
0x180034cf7  jz      short loc_180034D06
0x180034cf9  jle     short loc_180034D4D
0x180034cfb  movzx   ebx, bx
0x180034cfe  or      ebx, 80070000h
0x180034d04  jmp     short loc_180034D4D
0x180034d06  mov     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180034d0a  mov     rcx, [rbp+57h+var_60]
0x180034d0e  mov     rdx, [rcx+18h]; unsigned __int16 *
0x180034d12  mov     rcx, [rcx+0A0h]; unsigned __int16 *
0x180034d19  call    ?AllowCachedLogon@@YAHPEBG0PEAX@Z; AllowCachedLogon(ushort const *,ushort const *,void *)
0x180034d1e  test    eax, eax
0x180034d20  jnz     short loc_180034DA0
0x180034d22  xor     edx, edx; Token
0x180034d24  xor     ecx, ecx; Thread
0x180034d26  call    cs:__imp_SetThreadToken
0x180034d2d  nop     dword ptr [rax+rax+00h]
0x180034d32  test    eax, eax
0x180034d34  jnz     short loc_180034D96
0x180034d36  mov     rcx, [rbp+5Fh]; this
0x180034d3a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034d41  mov     edx, 0D3h; void *
0x180034d46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034d4b  mov     ebx, eax
0x180034d4d  lea     rcx, [rbp+57h+var_60]
0x180034d51  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x180034d56  nop
0x180034d57  lea     rcx, [rbp+57h+var_88]
0x180034d5b  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x180034d60  nop
0x180034d61  lea     rcx, [rbp+57h+DomainName]
0x180034d65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034d6a  nop
0x180034d6b  lea     rcx, [rbp+57h+var_80]
0x180034d6f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034d74  nop
0x180034d75  lea     rcx, [rbp+57h+username]
0x180034d79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034d7e  nop
0x180034d7f  lea     rcx, [rbp+57h+lpString1]
0x180034d83  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180034d88  nop
0x180034d89  lea     rcx, [rbp+57h+TokenHandle]
0x180034d8d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034d92  mov     eax, ebx
0x180034d94  jmp     short loc_180034DE7
0x180034d96  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180034d9a  call    ?SetNextLogonCacheable@@YAJPEBGH@Z; SetNextLogonCacheable(ushort const *,int)
0x180034d9f  nop
0x180034da0  lea     rcx, [rbp+57h+var_60]
0x180034da4  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x180034da9  nop
0x180034daa  lea     rcx, [rbp+57h+var_88]
0x180034dae  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x180034db3  nop
0x180034db4  lea     rcx, [rbp+57h+DomainName]
0x180034db8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034dbd  nop
0x180034dbe  lea     rcx, [rbp+57h+var_80]
0x180034dc2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034dc7  nop
0x180034dc8  lea     rcx, [rbp+57h+username]
0x180034dcc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034dd1  nop
0x180034dd2  lea     rcx, [rbp+57h+lpString1]
0x180034dd6  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180034ddb  nop
0x180034ddc  lea     rcx, [rbp+57h+TokenHandle]
0x180034de0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034de5  xor     eax, eax
0x180034de7  mov     rcx, [rbp+57h+var_8]
0x180034deb  xor     rcx, rsp; StackCookie
0x180034dee  call    __security_check_cookie
0x180034df3  lea     r11, [rsp+0C0h+var_s0]
0x180034dfb  mov     rbx, [r11+10h]
0x180034dff  mov     rdi, [r11+18h]
0x180034e03  mov     rsp, r11
0x180034e06  pop     rbp
0x180034e07  retn
```
