# CheckForUserObjectUpdates(void)

- ea: `0x180034438`
- end: `0x18003478e`
- name: `?CheckForUserObjectUpdates@@YAJXZ`
- size: `854`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180034420`

## callees

- `0x1800036e0`
- `0x180004b80`
- `0x180007978`
- `0x18000a9b8`
- `0x180016e00`
- `0x1800212a0`
- `0x1800245c0`
- `0x180025944`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e648`
- `0x180034438`
- `0x180034794`
- `0x18003a730`
- `0x18003e6f0`
- `0x18003e758`
- `0x18003e778`
- `0x18003e834`
- `0x18003e958`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800344a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800344a3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800346b2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800346b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003448f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003448f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800345a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800345a0`
- `logoncli!DsGetDcNameW` at `0x180034603`
- `logoncli!DsGetDcNameW` at `0x180034636`
- `logoncli!DsGetDcNameW` at `0x180034603`
- `logoncli!DsGetDcNameW` at `0x180034636`
- `samcli!NetUserGetInfo` at `0x180034670`
- `samcli!NetUserGetInfo` at `0x180034670`

## string_xrefs

- `0x1800344b1`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x1800344fe`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x180034579`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x180034612`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`
- `0x1800346c0`: `onecore\ds\security\gina\profile\profsvc\cachedlogon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&username);
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
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&DomainName);
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
        if ( !AllowCachedLogon(
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
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&DomainName);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&username);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&lpString1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x180034438  mov     [rsp-8+arg_0], rbx
0x18003443d  mov     [rsp-8+arg_8], rdi
0x180034442  push    rbp
0x180034443  lea     rbp, [rsp-57h]
0x180034448  sub     rsp, 0C0h
0x18003444f  mov     rax, cs:__security_cookie
0x180034456  xor     rax, rsp
0x180034459  mov     [rbp+57h+var_8], rax
0x18003445d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034461  mov     [rbp+57h+nSize], ebx
0x180034464  lea     rcx, [rbp+57h+nSize]; int *
0x180034468  call    ?GetMachineRole@@YAHPEAH@Z; GetMachineRole(int *)
0x18003446d  xor     edi, edi
0x18003446f  test    eax, eax
0x180034471  jz      loc_18003476B
0x180034477  cmp     [rbp+57h+nSize], edi
0x18003447a  jz      loc_18003476B
0x180034480  mov     [rbp+57h+TokenHandle], rdi
0x180034484  xor     edx, edx
0x180034486  lea     rcx, [rbp+57h+TokenHandle]
0x18003448a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003448f  call    cs:__imp_GetCurrentThread
0x180034495  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180034499  lea     edx, [rbx+9]; DesiredAccess
0x18003449c  lea     r8d, [rbx+2]; OpenAsSelf
0x1800344a0  mov     rcx, rax; ThreadHandle
0x1800344a3  call    cs:__imp_OpenThreadToken
0x1800344a9  test    eax, eax
0x1800344ab  jnz     short loc_1800344C9
0x1800344ad  mov     rcx, [rbp+5Fh]; this
0x1800344b1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800344b8  mov     edx, 90h; void *
0x1800344bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800344c2  mov     ebx, eax
0x1800344c4  jmp     loc_18003470F
0x1800344c9  mov     [rbp+57h+lpString1], rdi
0x1800344cd  mov     [rbp+57h+var_50], rdi
0x1800344d1  mov     [rbp+57h+var_48], rdi
0x1800344d5  lea     rcx, [rbp+57h+lpString1]
0x1800344d9  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800344de  mov     [rbp+57h+var_50], rbx
0x1800344e2  mov     [rbp+57h+var_48], rbx
0x1800344e6  lea     rdx, [rbp+57h+lpString1]; unsigned __int16 **
0x1800344ea  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800344ee  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x1800344f3  mov     ebx, eax
0x1800344f5  test    eax, eax
0x1800344f7  jns     short loc_180034516
0x1800344f9  mov     edx, 93h; void *
0x1800344fe  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034505  mov     r9d, eax; char *
0x180034508  mov     rcx, [rbp+5Fh]; this
0x18003450c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034511  jmp     loc_180034705
0x180034516  mov     [rbp+57h+nSize], edi
0x180034519  lea     rdx, [rbp+57h+nSize]; int *
0x18003451d  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180034521  call    ?GetNextLogonCacheable@@YAJPEBGPEAH@Z; GetNextLogonCacheable(ushort const *,int *)
0x180034526  mov     ebx, eax
0x180034528  test    eax, eax
0x18003452a  jns     short loc_180034533
0x18003452c  mov     edx, 96h
0x180034531  jmp     short loc_1800344FE
0x180034533  cmp     [rbp+57h+nSize], edi
0x180034536  jz      loc_180034758
0x18003453c  mov     [rbp+57h+username], rdi
0x180034540  mov     [rbp+57h+var_80], rdi
0x180034544  xor     edx, edx
0x180034546  lea     rcx, [rbp+57h+var_80]
0x18003454a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003454f  xor     edx, edx
0x180034551  lea     rcx, [rbp+57h+username]
0x180034555  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003455a  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x18003455e  lea     rdx, [rbp+57h+username]; unsigned __int16 **
0x180034562  mov     ecx, 2; NameFormat
0x180034567  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x18003456c  mov     ebx, eax
0x18003456e  test    eax, eax
0x180034570  jns     short loc_18003458F
0x180034572  mov     rcx, [rbp+5Fh]; this
0x180034576  mov     r9d, eax; char *
0x180034579  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034580  mov     edx, 9Eh; void *
0x180034585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003458a  jmp     loc_1800346F1
0x18003458f  mov     [rbp+57h+nSize], 10h
0x180034596  lea     r8, [rbp+57h+nSize]; nSize
0x18003459a  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18003459e  xor     ecx, ecx; NameType
0x1800345a0  call    cs:__imp_GetComputerNameExW
0x1800345a6  test    eax, eax
0x1800345a8  jz      short loc_1800345BF
0x1800345aa  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800345ae  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800345b2  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800345b7  test    eax, eax
0x1800345b9  jnz     loc_180034744
0x1800345bf  mov     [rbp+57h+DomainName], rdi
0x1800345c3  xor     edx, edx
0x1800345c5  lea     rcx, [rbp+57h+DomainName]
0x1800345c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800345ce  lea     r8, [rbp+57h+DomainName]; unsigned __int16 **
0x1800345d2  xor     edx, edx; unsigned __int16 **
0x1800345d4  lea     ecx, [rdx+0Ch]; NameFormat
0x1800345d7  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x1800345dc  nop
0x1800345dd  mov     rdx, [rbp+57h+DomainName]; DomainName
0x1800345e1  mov     [rbp+57h+var_88], rdi
0x1800345e5  lea     rax, [rbp+57h+var_88]
0x1800345e9  xor     r9d, r9d; SiteName
0x1800345ec  xor     r8d, r8d; DomainGuid
0x1800345ef  xor     ecx, ecx; ComputerName
0x1800345f1  mov     [rsp+0C0h+DomainControllerInfo], rax; DomainControllerInfo
0x1800345f6  test    rdx, rdx
0x1800345f9  jz      short loc_18003462C
0x1800345fb  mov     [rsp+0C0h+Flags], 20100h; unsigned int
0x180034603  call    cs:__imp_DsGetDcNameW
0x180034609  test    eax, eax
0x18003460b  jz      short loc_180034647
0x18003460d  mov     edx, 0B7h; void *
0x180034612  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180034619  mov     r9d, eax; char *
0x18003461c  mov     rcx, [rbp+5Fh]; this
0x180034620  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034625  mov     ebx, eax
0x180034627  jmp     loc_1800346DD
0x18003462c  mov     [rsp+0C0h+Flags], 100h; Flags
0x180034634  xor     edx, edx; DomainName
0x180034636  call    cs:__imp_DsGetDcNameW
0x18003463c  test    eax, eax
0x18003463e  jz      short loc_180034647
0x180034640  mov     edx, 0C0h
0x180034645  jmp     short loc_180034612
0x180034647  mov     [rbp+57h+var_60], rdi
0x18003464b  lea     rax, [rbp+57h+var_60]
0x18003464f  mov     [rbp+57h+var_40], rax
0x180034653  mov     [rbp+57h+bufptr], rdi
0x180034657  mov     [rbp+57h+var_30], 1
0x18003465b  lea     r9, [rbp+57h+bufptr]; bufptr
0x18003465f  mov     r8d, 3; level
0x180034665  mov     rdx, [rbp+57h+username]; username
0x180034669  mov     rcx, [rbp+57h+var_88]
0x18003466d  mov     rcx, [rcx]; servername
0x180034670  call    cs:__imp_NetUserGetInfo
0x180034676  mov     ebx, eax
0x180034678  lea     rcx, [rbp+57h+var_40]
0x18003467c  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_USER_INFO_3@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_3 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_3 *,_USER_INFO_3 *,0,std::nullptr_t>>>>::~out_param_ptr_t<uchar * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_3 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_3 *,_USER_INFO_3 *,0,std::nullptr_t>>>>(void)
0x180034681  test    ebx, ebx
0x180034683  jz      short loc_180034692
0x180034685  jle     short loc_1800346D3
0x180034687  movzx   ebx, bx
0x18003468a  or      ebx, 80070000h
0x180034690  jmp     short loc_1800346D3
0x180034692  mov     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180034696  mov     rcx, [rbp+57h+var_60]
0x18003469a  mov     rdx, [rcx+18h]; unsigned __int16 *
0x18003469e  mov     rcx, [rcx+0A0h]; unsigned __int16 *
0x1800346a5  call    ?AllowCachedLogon@@YAHPEBG0PEAX@Z; AllowCachedLogon(ushort const *,ushort const *,void *)
0x1800346aa  test    eax, eax
0x1800346ac  jnz     short loc_180034726
0x1800346ae  xor     edx, edx; Token
0x1800346b0  xor     ecx, ecx; Thread
0x1800346b2  call    cs:__imp_SetThreadToken
0x1800346b8  test    eax, eax
0x1800346ba  jnz     short loc_18003471C
0x1800346bc  mov     rcx, [rbp+5Fh]; this
0x1800346c0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800346c7  mov     edx, 0D3h; void *
0x1800346cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800346d1  mov     ebx, eax
0x1800346d3  lea     rcx, [rbp+57h+var_60]
0x1800346d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x1800346dc  nop
0x1800346dd  lea     rcx, [rbp+57h+var_88]
0x1800346e1  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x1800346e6  nop
0x1800346e7  lea     rcx, [rbp+57h+DomainName]
0x1800346eb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800346f0  nop
0x1800346f1  lea     rcx, [rbp+57h+var_80]
0x1800346f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800346fa  nop
0x1800346fb  lea     rcx, [rbp+57h+username]
0x1800346ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034704  nop
0x180034705  lea     rcx, [rbp+57h+lpString1]
0x180034709  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003470e  nop
0x18003470f  lea     rcx, [rbp+57h+TokenHandle]
0x180034713  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034718  mov     eax, ebx
0x18003471a  jmp     short loc_18003476D
0x18003471c  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180034720  call    ?SetNextLogonCacheable@@YAJPEBGH@Z; SetNextLogonCacheable(ushort const *,int)
0x180034725  nop
0x180034726  lea     rcx, [rbp+57h+var_60]
0x18003472a  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x18003472f  nop
0x180034730  lea     rcx, [rbp+57h+var_88]
0x180034734  call    ??1?$unique_storage@U?$resource_policy@PEAU_DOMAIN_CONTROLLER_INFOW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DOMAIN_CONTROLLER_INFOW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DOMAIN_CONTROLLER_INFOW *,_DOMAIN_CONTROLLER_INFOW *,0,std::nullptr_t>>(void)
0x180034739  nop
0x18003473a  lea     rcx, [rbp+57h+DomainName]
0x18003473e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034743  nop
0x180034744  lea     rcx, [rbp+57h+var_80]
0x180034748  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003474d  nop
0x18003474e  lea     rcx, [rbp+57h+username]
0x180034752  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034757  nop
0x180034758  lea     rcx, [rbp+57h+lpString1]
0x18003475c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180034761  nop
0x180034762  lea     rcx, [rbp+57h+TokenHandle]
0x180034766  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003476b  xor     eax, eax
0x18003476d  mov     rcx, [rbp+57h+var_8]
0x180034771  xor     rcx, rsp; StackCookie
0x180034774  call    __security_check_cookie
0x180034779  lea     r11, [rsp+0C0h+var_s0]
0x180034781  mov     rbx, [r11+10h]
0x180034785  mov     rdi, [r11+18h]
0x180034789  mov     rsp, r11
0x18003478c  pop     rbp
0x18003478d  retn
```
