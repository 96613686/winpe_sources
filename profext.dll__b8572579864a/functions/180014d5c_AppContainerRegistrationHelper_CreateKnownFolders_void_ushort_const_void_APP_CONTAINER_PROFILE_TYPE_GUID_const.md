# AppContainerRegistrationHelper::CreateKnownFolders(void *,ushort const *,void *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x180014d5c`
- end: `0x1800153af`
- name: `?CreateKnownFolders@AppContainerRegistrationHelper@@CAJPEAXPEBG0W4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `1619`
- prototype: `static int __high(void *, const unsigned __int16 *, void *, enum APP_CONTAINER_PROFILE_TYPE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009504`

## callees

- `0x180002030`
- `0x1800044e0`
- `0x1800045bc`
- `0x18000f41c`
- `0x18000f614`
- `0x18000f6cc`
- `0x180014750`
- `0x180014d5c`
- `0x180015fe0`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180014e4e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180014e4e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014ecb`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014db3`

## string_xrefs

- `0x180014df6`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014e7b`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014ef8`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014f72`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015001`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015098`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18001516d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18001520f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800152aa`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015345`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014ff2`: `Name %ls path %ls`
- `0x1800151bc`: `INetCache`
- `0x180015089`: `Name %ls path %ws`
- `0x18001515e`: `Name %ls path %ls temp %ls`
- `0x180015200`: `Name %ls path %ls dir %ws`
- `0x18001529b`: `Name %ls path %ls dir %ws`
- `0x180015336`: `Name %ls path %ls dir %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppContainerRegistrationHelper::CreateKnownFolders(
        void *a1,
        char *a2,
        void *a3,
        int a4,
        struct _GUID *a5)
{
  struct _ACL *v6; // rbx
  int LastErrorMsg; // edi
  __int64 v8; // r9
  int Folder; // ebx
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  char *v13; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID *v14; // [rsp+58h] [rbp-A8h] BYREF
  void *v15; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[6]; // [rsp+68h] [rbp-98h] BYREF
  char v17; // [rsp+98h] [rbp-68h]
  struct _ACL v18[66]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v15 = a1;
  v13 = a2;
  v11 = a4;
  v14 = a5;
  v12 = 0;
  v6 = (struct _ACL *)CoTaskMemAlloc(0x58u);
  v16[0] = v6;
  if ( !v6 )
  {
    LastErrorMsg = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x50D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x8007000ELL,
      (int)"Name %ls size %d",
      v13,
      88);
    goto LABEL_56;
  }
  v16[1] = &v12;
  v16[2] = &v15;
  v16[3] = &v13;
  v16[4] = &v11;
  v16[5] = &v14;
  v17 = 1;
  if ( !InitializeAcl(v6, 0x58u, 2u) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x518,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                     "Name %ls size %d",
                     v13,
                     88);
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  if ( !AddAccessAllowedAceEx(v6, 2u, 0x23u, 0x1F01FFu, a3) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x520,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                     "Name %ls size %d",
                     v13,
                     88);
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  LastErrorMsg = AppContainerRegistrationHelper::DeriveTopLevelFolderPath(v15, v13, (unsigned __int16 *)v18, v8, v11);
  if ( LastErrorMsg < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x530,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)"Name %ls",
      v13);
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  if ( v11 != 2 && !v15 )
  {
    LastErrorMsg = StringCchCatW((unsigned __int16 *)v18, 0x104u, L"\\AC");
    if ( LastErrorMsg < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x53C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)LastErrorMsg,
        (int)"Name %ls path %ls",
        v13,
        v18);
      if ( v12 == 1 )
        AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
      goto LABEL_56;
    }
  }
  LastErrorMsg = AppContainerRegistrationHelper::CreateFolder(v18, 0, 0x2000u, v6, v14);
  if ( LastErrorMsg == -2147024891 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_24;
  }
  if ( LastErrorMsg < 0 )
  {
LABEL_24:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x548,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)"Name %ls path %ws",
      v13,
      v18);
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  v12 = 1;
  Folder = AppContainerRegistrationHelper::CreateFolder(v18, L"Temp", 0x80u, 0, v14);
  if ( Folder == -2147024891 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_34:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x552,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)Folder,
      (int)"Name %ls path %ls temp %ls",
      v13,
      v18,
      L"Temp");
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    LastErrorMsg = Folder;
    goto LABEL_56;
  }
  LastErrorMsg = -2147024893;
  if ( Folder == -2147024893 )
  {
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  if ( Folder < 0 )
    goto LABEL_34;
  LastErrorMsg = AppContainerRegistrationHelper::CreateFolder(v18, L"INetCache", 0x2006u, 0, v14);
  if ( LastErrorMsg == -2147024891 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_40;
  }
  if ( LastErrorMsg < 0 )
  {
LABEL_40:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x55C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)"Name %ls path %ls dir %ws",
      v13,
      v18,
      L"INetCache");
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  LastErrorMsg = AppContainerRegistrationHelper::CreateFolder(v18, L"INetHistory", 0x2006u, 0, v14);
  if ( LastErrorMsg == -2147024891 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_46;
  }
  if ( LastErrorMsg < 0 )
  {
LABEL_46:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x566,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)"Name %ls path %ls dir %ws",
      v13,
      v18,
      L"INetHistory");
    if ( v12 == 1 )
      AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
    goto LABEL_56;
  }
  LastErrorMsg = AppContainerRegistrationHelper::CreateFolder(v18, L"INetCookies", 0x2006u, 0, v14);
  if ( LastErrorMsg == -2147024891 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else if ( LastErrorMsg >= 0 )
  {
    v12 = 0;
    LastErrorMsg = 0;
    goto LABEL_56;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x570,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)(unsigned int)LastErrorMsg,
    (int)"Name %ls path %ls dir %ws",
    v13,
    v18,
    L"INetCookies");
  if ( v12 == 1 )
    AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)v15, v13, v11, v14);
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v16);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x180014d5c  push    rbp
0x180014d5e  push    rbx
0x180014d5f  push    rdi
0x180014d60  push    r12
0x180014d62  push    r15
0x180014d64  lea     rbp, [rsp-1C0h]
0x180014d6c  sub     rsp, 2C0h
0x180014d73  mov     rax, cs:__security_cookie
0x180014d7a  xor     rax, rsp
0x180014d7d  mov     [rbp+1E0h+var_30], rax
0x180014d84  mov     rdi, r8
0x180014d87  mov     [rsp+2E0h+var_280], rcx
0x180014d8c  mov     [rsp+2E0h+var_290], rdx
0x180014d91  mov     [rsp+2E0h+var_2A0], r9d
0x180014d96  mov     rax, [rbp+1E0h+arg_20]
0x180014d9d  mov     [rsp+2E0h+var_288], rax
0x180014da2  mov     [rsp+2E0h+var_298], 0
0x180014daa  mov     r15d, 58h ; 'X'
0x180014db0  mov     ecx, r15d; cb
0x180014db3  call    cs:__imp_CoTaskMemAlloc
0x180014dba  nop     dword ptr [rax+rax+00h]
0x180014dbf  mov     rbx, rax
0x180014dc2  mov     [rsp+2E0h+var_278], rax
0x180014dc7  test    rax, rax
0x180014dca  jnz     short loc_180014E0C
0x180014dcc  mov     rcx, [rbp+1E8h]; this
0x180014dd3  mov     dword ptr [rsp+2E0h+var_2B0], r15d
0x180014dd8  mov     rax, [rsp+2E0h+var_290]
0x180014ddd  mov     [rsp+2E0h+var_2B8], rax; char *
0x180014de2  lea     r9, aNameLsSizeD; "Name %ls size %d"
0x180014de9  mov     [rsp+2E0h+pSid], r9; int
0x180014dee  mov     edi, 8007000Eh
0x180014df3  mov     r9d, edi; char *
0x180014df6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014dfd  mov     edx, 50Dh; void *
0x180014e02  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014e07  jmp     loc_180015384
0x180014e0c  lea     rax, [rsp+2E0h+var_298]
0x180014e11  mov     [rsp+2E0h+var_270], rax
0x180014e16  lea     rax, [rsp+2E0h+var_280]
0x180014e1b  mov     [rsp+2E0h+var_268], rax
0x180014e20  lea     rax, [rsp+2E0h+var_290]
0x180014e25  mov     [rbp+1E0h+var_260], rax
0x180014e29  lea     rax, [rsp+2E0h+var_2A0]
0x180014e2e  mov     [rbp+1E0h+var_258], rax
0x180014e32  lea     rax, [rsp+2E0h+var_288]
0x180014e37  mov     [rbp+1E0h+var_250], rax
0x180014e3b  mov     [rbp+1E0h+var_248], 1
0x180014e3f  mov     r12d, 2
0x180014e45  mov     r8d, r12d; dwAclRevision
0x180014e48  mov     edx, r15d; nAclLength
0x180014e4b  mov     rcx, rbx; pAcl
0x180014e4e  call    cs:__imp_InitializeAcl
0x180014e55  nop     dword ptr [rax+rax+00h]
0x180014e5a  test    eax, eax
0x180014e5c  jnz     short loc_180014EB4
0x180014e5e  mov     rax, [rsp+2E0h+var_290]
0x180014e63  mov     rcx, [rbp+1E8h]; this
0x180014e6a  mov     dword ptr [rsp+2E0h+var_2B8], r15d
0x180014e6f  mov     [rsp+2E0h+pSid], rax; char *
0x180014e74  lea     r9, aNameLsSizeD; "Name %ls size %d"
0x180014e7b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014e82  mov     edx, 518h; void *
0x180014e87  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180014e8c  mov     edi, eax
0x180014e8e  cmp     [rsp+2E0h+var_298], 1
0x180014e93  jnz     short loc_180014EAF
0x180014e95  mov     r9, [rsp+2E0h+var_288]
0x180014e9a  mov     r8d, [rsp+2E0h+var_2A0]
0x180014e9f  mov     rdx, [rsp+2E0h+var_290]
0x180014ea4  mov     rcx, [rsp+2E0h+var_280]
0x180014ea9  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180014eae  nop
0x180014eaf  jmp     loc_180015384
0x180014eb4  mov     [rsp+2E0h+pSid], rdi; pSid
0x180014eb9  mov     r9d, 1F01FFh; AccessMask
0x180014ebf  mov     r8d, 23h ; '#'; AceFlags
0x180014ec5  mov     edx, r12d; dwAceRevision
0x180014ec8  mov     rcx, rbx; pAcl
0x180014ecb  call    cs:__imp_AddAccessAllowedAceEx
0x180014ed2  nop     dword ptr [rax+rax+00h]
0x180014ed7  test    eax, eax
0x180014ed9  jnz     short loc_180014F31
0x180014edb  mov     rax, [rsp+2E0h+var_290]
0x180014ee0  mov     rcx, [rbp+1E8h]; this
0x180014ee7  mov     dword ptr [rsp+2E0h+var_2B8], r15d
0x180014eec  mov     [rsp+2E0h+pSid], rax; char *
0x180014ef1  lea     r9, aNameLsSizeD; "Name %ls size %d"
0x180014ef8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014eff  mov     edx, 520h; void *
0x180014f04  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180014f09  mov     edi, eax
0x180014f0b  cmp     [rsp+2E0h+var_298], 1
0x180014f10  jnz     short loc_180014F2C
0x180014f12  mov     r9, [rsp+2E0h+var_288]
0x180014f17  mov     r8d, [rsp+2E0h+var_2A0]
0x180014f1c  mov     rdx, [rsp+2E0h+var_290]
0x180014f21  mov     rcx, [rsp+2E0h+var_280]
0x180014f26  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180014f2b  nop
0x180014f2c  jmp     loc_180015384
0x180014f31  mov     eax, [rsp+2E0h+var_2A0]
0x180014f35  mov     dword ptr [rsp+2E0h+pSid], eax
0x180014f39  lea     r8, [rbp+1E0h+var_240]
0x180014f3d  mov     rdx, [rsp+2E0h+var_290]
0x180014f42  mov     rcx, [rsp+2E0h+var_280]
0x180014f47  call    ?DeriveTopLevelFolderPath@AppContainerRegistrationHelper@@CAJPEAXPEBGPEAG_KW4APP_CONTAINER_PROFILE_TYPE@@@Z; AppContainerRegistrationHelper::DeriveTopLevelFolderPath(void *,ushort const *,ushort *,unsigned __int64,APP_CONTAINER_PROFILE_TYPE)
0x180014f4c  mov     edi, eax
0x180014f4e  test    eax, eax
0x180014f50  jns     short loc_180014FAA
0x180014f52  mov     rcx, [rbp+1E8h]; this
0x180014f59  mov     rax, [rsp+2E0h+var_290]
0x180014f5e  mov     [rsp+2E0h+var_2B8], rax; char *
0x180014f63  lea     rax, aNameLs; "Name %ls"
0x180014f6a  mov     [rsp+2E0h+pSid], rax; int
0x180014f6f  mov     r9d, edi; char *
0x180014f72  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014f79  mov     edx, 530h; void *
0x180014f7e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014f83  nop
0x180014f84  cmp     [rsp+2E0h+var_298], 1
0x180014f89  jnz     short loc_180014FA5
0x180014f8b  mov     r9, [rsp+2E0h+var_288]
0x180014f90  mov     r8d, [rsp+2E0h+var_2A0]
0x180014f95  mov     rdx, [rsp+2E0h+var_290]
0x180014f9a  mov     rcx, [rsp+2E0h+var_280]
0x180014f9f  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180014fa4  nop
0x180014fa5  jmp     loc_180015384
0x180014faa  cmp     [rsp+2E0h+var_2A0], r12d
0x180014faf  jz      loc_180015039
0x180014fb5  cmp     [rsp+2E0h+var_280], 0
0x180014fbb  jnz     short loc_180015039
0x180014fbd  lea     r8, aAc; "\\AC"
0x180014fc4  mov     edx, 104h; unsigned __int64
0x180014fc9  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x180014fcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014fd2  mov     edi, eax
0x180014fd4  test    eax, eax
0x180014fd6  jns     short loc_180015039
0x180014fd8  mov     rcx, [rbp+1E8h]; this
0x180014fdf  lea     rax, [rbp+1E0h+var_240]
0x180014fe3  mov     [rsp+2E0h+var_2B0], rax
0x180014fe8  mov     rax, [rsp+2E0h+var_290]
0x180014fed  mov     [rsp+2E0h+var_2B8], rax; char *
0x180014ff2  lea     rax, aNameLsPathLs; "Name %ls path %ls"
0x180014ff9  mov     [rsp+2E0h+pSid], rax; int
0x180014ffe  mov     r9d, edi; char *
0x180015001  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015008  mov     edx, 53Ch; void *
0x18001500d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015012  nop
0x180015013  cmp     [rsp+2E0h+var_298], 1
0x180015018  jnz     short loc_180015034
0x18001501a  mov     r9, [rsp+2E0h+var_288]
0x18001501f  mov     r8d, [rsp+2E0h+var_2A0]
0x180015024  mov     rdx, [rsp+2E0h+var_290]
0x180015029  mov     rcx, [rsp+2E0h+var_280]
0x18001502e  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180015033  nop
0x180015034  jmp     loc_180015384
0x180015039  mov     rax, [rsp+2E0h+var_288]
0x18001503e  mov     [rsp+2E0h+pSid], rax; struct _GUID *
0x180015043  mov     r9, rbx; pDacl
0x180015046  xor     edx, edx; unsigned __int16 *
0x180015048  mov     r8d, 2000h; dwFileAttributes
0x18001504e  lea     rcx, [rbp+1E0h+var_240]; char *
0x180015052  call    ?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)
0x180015057  mov     edi, eax
0x180015059  mov     r15d, 80070005h
0x18001505f  cmp     eax, r15d
0x180015062  jnz     short loc_18001506B
0x180015064  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015069  jmp     short loc_18001506F
0x18001506b  test    edi, edi
0x18001506d  jns     short loc_1800150D0
0x18001506f  mov     rcx, [rbp+1E8h]; this
0x180015076  lea     rax, [rbp+1E0h+var_240]
0x18001507a  mov     [rsp+2E0h+var_2B0], rax
0x18001507f  mov     rax, [rsp+2E0h+var_290]
0x180015084  mov     [rsp+2E0h+var_2B8], rax; char *
0x180015089  lea     rax, aNameLsPathWs; "Name %ls path %ws"
0x180015090  mov     [rsp+2E0h+pSid], rax; int
0x180015095  mov     r9d, edi; char *
0x180015098  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001509f  mov     edx, 548h; void *
0x1800150a4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800150a9  nop
0x1800150aa  cmp     [rsp+2E0h+var_298], 1
0x1800150af  jnz     short loc_1800150CB
0x1800150b1  mov     r9, [rsp+2E0h+var_288]
0x1800150b6  mov     r8d, [rsp+2E0h+var_2A0]
0x1800150bb  mov     rdx, [rsp+2E0h+var_290]
0x1800150c0  mov     rcx, [rsp+2E0h+var_280]
0x1800150c5  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x1800150ca  nop
0x1800150cb  jmp     loc_180015384
0x1800150d0  mov     [rsp+2E0h+var_298], 1
0x1800150d8  mov     rax, [rsp+2E0h+var_288]
0x1800150dd  mov     [rsp+2E0h+pSid], rax; struct _GUID *
0x1800150e2  xor     r9d, r9d; pDacl
0x1800150e5  mov     r8d, 80h; dwFileAttributes
0x1800150eb  lea     r12, aTemp; "Temp"
0x1800150f2  mov     rdx, r12; unsigned __int16 *
0x1800150f5  lea     rcx, [rbp+1E0h+var_240]; char *
0x1800150f9  call    ?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)
0x1800150fe  mov     ebx, eax
0x180015100  cmp     eax, r15d
0x180015103  jnz     short loc_18001510C
0x180015105  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001510a  jmp     short loc_18001513F
0x18001510c  mov     edi, 80070003h
0x180015111  cmp     ebx, edi
0x180015113  jnz     short loc_18001513B
0x180015115  cmp     [rsp+2E0h+var_298], 1
0x18001511a  jnz     short loc_180015136
0x18001511c  mov     r9, [rsp+2E0h+var_288]
0x180015121  mov     r8d, [rsp+2E0h+var_2A0]
0x180015126  mov     rdx, [rsp+2E0h+var_290]
0x18001512b  mov     rcx, [rsp+2E0h+var_280]
0x180015130  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180015135  nop
0x180015136  jmp     loc_180015384
0x18001513b  test    ebx, ebx
0x18001513d  jns     short loc_1800151A7
0x18001513f  mov     rcx, [rbp+1E8h]; this
0x180015146  mov     [rsp+2E0h+var_2A8], r12
0x18001514b  lea     rax, [rbp+1E0h+var_240]
0x18001514f  mov     [rsp+2E0h+var_2B0], rax
0x180015154  mov     rax, [rsp+2E0h+var_290]
0x180015159  mov     [rsp+2E0h+var_2B8], rax; char *
0x18001515e  lea     rax, aNameLsPathLsTe; "Name %ls path %ls temp %ls"
0x180015165  mov     [rsp+2E0h+pSid], rax; int
0x18001516a  mov     r9d, ebx; char *
0x18001516d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015174  mov     edx, 552h; void *
0x180015179  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001517e  nop
0x18001517f  cmp     [rsp+2E0h+var_298], 1
0x180015184  jnz     short loc_1800151A0
0x180015186  mov     r9, [rsp+2E0h+var_288]
0x18001518b  mov     r8d, [rsp+2E0h+var_2A0]
0x180015190  mov     rdx, [rsp+2E0h+var_290]
0x180015195  mov     rcx, [rsp+2E0h+var_280]
0x18001519a  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x18001519f  nop
0x1800151a0  mov     edi, ebx
0x1800151a2  jmp     loc_180015384
0x1800151a7  mov     rax, [rsp+2E0h+var_288]
0x1800151ac  mov     [rsp+2E0h+pSid], rax; struct _GUID *
0x1800151b1  xor     r9d, r9d; pDacl
0x1800151b4  mov     ebx, 2006h
0x1800151b9  mov     r8d, ebx; dwFileAttributes
0x1800151bc  lea     r12, aInetcache; "INetCache"
0x1800151c3  mov     rdx, r12; unsigned __int16 *
0x1800151c6  lea     rcx, [rbp+1E0h+var_240]; char *
0x1800151ca  call    ?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)
0x1800151cf  mov     edi, eax
0x1800151d1  cmp     eax, r15d
0x1800151d4  jnz     short loc_1800151DD
0x1800151d6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800151db  jmp     short loc_1800151E1
0x1800151dd  test    edi, edi
0x1800151df  jns     short loc_180015247
0x1800151e1  mov     rcx, [rbp+1E8h]; this
0x1800151e8  mov     [rsp+2E0h+var_2A8], r12
0x1800151ed  lea     rax, [rbp+1E0h+var_240]
0x1800151f1  mov     [rsp+2E0h+var_2B0], rax
0x1800151f6  mov     rax, [rsp+2E0h+var_290]
0x1800151fb  mov     [rsp+2E0h+var_2B8], rax; char *
0x180015200  lea     rax, aNameLsPathLsDi; "Name %ls path %ls dir %ws"
0x180015207  mov     [rsp+2E0h+pSid], rax; int
0x18001520c  mov     r9d, edi; char *
0x18001520f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015216  mov     edx, 55Ch; void *
0x18001521b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015220  nop
0x180015221  cmp     [rsp+2E0h+var_298], 1
0x180015226  jnz     short loc_180015242
0x180015228  mov     r9, [rsp+2E0h+var_288]
0x18001522d  mov     r8d, [rsp+2E0h+var_2A0]
0x180015232  mov     rdx, [rsp+2E0h+var_290]
0x180015237  mov     rcx, [rsp+2E0h+var_280]
0x18001523c  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180015241  nop
0x180015242  jmp     loc_180015384
0x180015247  mov     rax, [rsp+2E0h+var_288]
0x18001524c  mov     [rsp+2E0h+pSid], rax; struct _GUID *
0x180015251  xor     r9d, r9d; pDacl
0x180015254  mov     r8d, ebx; dwFileAttributes
0x180015257  lea     r12, aInethistory; "INetHistory"
0x18001525e  mov     rdx, r12; unsigned __int16 *
0x180015261  lea     rcx, [rbp+1E0h+var_240]; char *
0x180015265  call    ?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)
0x18001526a  mov     edi, eax
0x18001526c  cmp     eax, r15d
0x18001526f  jnz     short loc_180015278
0x180015271  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015276  jmp     short loc_18001527C
0x180015278  test    edi, edi
  ... truncated ...
```
