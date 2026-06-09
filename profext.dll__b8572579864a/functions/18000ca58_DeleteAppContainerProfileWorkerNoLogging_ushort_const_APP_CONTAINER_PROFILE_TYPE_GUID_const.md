# DeleteAppContainerProfileWorkerNoLogging(ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x18000ca58`
- end: `0x18000d114`
- name: `?DeleteAppContainerProfileWorkerNoLogging@@YAJPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `1724`
- prototype: `__int64 __fastcall(const char *, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015da0`

## callees

- `0x180001854`
- `0x180001ba0`
- `0x180001cfc`
- `0x180001ef0`
- `0x1800041ec`
- `0x1800044e0`
- `0x180004594`
- `0x18000aacc`
- `0x18000beb0`
- `0x18000c7d4`
- `0x18000c8d8`
- `0x18000c938`
- `0x18000ca58`
- `0x18000f440`
- `0x18000f5f0`
- `0x18000f614`
- `0x18000f6cc`
- `0x18000f884`
- `0x18000f9ac`
- `0x1800162d0`
- `0x180016740`
- `0x180017014`
- `0x18001a86c`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x18000cca3`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x18000cca3`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x18000cf5a`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x18000cf5a`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x18000cd2b`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x18000cef9`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x18000cd2b`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x18000cef9`
- `ntdll!RtlFreeSid` at `0x18000cd07`
- `ntdll!RtlFreeSid` at `0x18000cd07`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000ce70`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000ce70`
- `ntdll!RtlInitUnicodeString` at `0x18000ce59`
- `ntdll!RtlInitUnicodeString` at `0x18000ce59`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cde6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cde6`

## string_xrefs

- `0x18000cb07`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cb43`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cba9`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cbf6`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cc51`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ccce`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cd61`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cdaa`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ce09`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ce9b`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cf25`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000cf9f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000d02a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000d084`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000d01b`: `Name %ls display %ls Sid %ls type %d`

## pseudocode

```c
__int64 __fastcall DeleteAppContainerProfileWorkerNoLogging(const char *a1, int a2)
{
  char v4; // r14
  signed int v5; // ebx
  __int64 v6; // rdx
  const char *v7; // rax
  __int64 v8; // r8
  int v10; // eax
  HANDLE v11; // rbx
  int IsAppContainerToken; // eax
  __int64 v13; // rdx
  int v14; // esi
  int AppContainerSidFromToken; // eax
  unsigned int PackageFamilyNameFromToken; // eax
  int UserSid; // eax
  signed int LastErrorMsg; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // esi
  int v21; // edi
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp-A8h] BYREF
  PSID v26; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  PSID v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  HANDLE token; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING UniDest; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  char v33[144]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v4 = 1;
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v5 = -2147024809;
LABEL_7:
    v8 = 0;
    goto LABEL_8;
  }
  v6 = 65;
  v7 = a1;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = (65 - v6) & -(__int64)(v6 != 0);
  v5 = v6 == 0 ? 0x80070057 : 0;
  if ( !v6 )
    goto LABEL_7;
LABEL_8:
  if ( v5 == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB0E,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls",
      a1);
    return 2147942487LL;
  }
  if ( v5 >= 0 )
  {
    if ( !v8 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB10,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)0x80070057LL,
        (int)"Name %ls",
        a1);
      return 2147942487LL;
    }
    token = 0;
    v10 = AppContainerRegistrationHelper::OpenCurrentUserToken((char *)0xE, &token);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB15,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v10,
        (int)"Name %ls",
        a1);
LABEL_55:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
      return (unsigned int)v5;
    }
    packageFamilyNameLength = 0;
    v11 = token;
    IsAppContainerToken = AppContainerRegistrationHelper::IsAppContainerToken(token, (int *)&packageFamilyNameLength);
    v14 = IsAppContainerToken;
    if ( IsAppContainerToken < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB19,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)IsAppContainerToken,
        (int)"Name %ls",
        a1);
LABEL_19:
      v5 = v14;
      goto LABEL_55;
    }
    Sid = 0;
    if ( packageFamilyNameLength )
    {
      Sid = 0;
      AppContainerSidFromToken = AppContainerRegistrationHelper::GetAppContainerSidFromToken(v11, &Sid);
      v14 = AppContainerSidFromToken;
      if ( AppContainerSidFromToken < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB20,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)AppContainerSidFromToken,
          (int)"Name %ls",
          a1);
LABEL_23:
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        goto LABEL_19;
      }
    }
    else
    {
      packageFamilyNameLength = 2162688;
      AppModelPolicy_GetPolicy(v11, v13, &packageFamilyNameLength);
      if ( packageFamilyNameLength == 2162689 )
      {
        packageFamilyNameLength = 65;
        PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v11, &packageFamilyNameLength, packageFamilyName);
        if ( PackageFamilyNameFromToken )
        {
          v5 = wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 (void *)0xB34,
                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                 (const char *)PackageFamilyNameFromToken,
                 (unsigned int)"Name %ls",
                 a1);
LABEL_27:
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
          goto LABEL_55;
        }
        Sid = 0;
        v14 = AppContainerDeriveSidFromMoniker(packageFamilyName, &Sid);
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xB37,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)v14,
            (int)"Name %ls family %ls",
            a1,
            packageFamilyName);
          goto LABEL_23;
        }
      }
    }
    v26 = 0;
    UserSid = GetUserSid(v11, &v26);
    v5 = UserSid;
    if ( UserSid < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB3C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)UserSid,
        (int)"Name %ls",
        a1);
LABEL_32:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
      goto LABEL_27;
    }
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW(v26, &StringSid) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0xB3F,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                       "Name %ls",
                       a1);
LABEL_35:
      v5 = LastErrorMsg;
LABEL_36:
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
      goto LABEL_32;
    }
    memset_0(v33, 0, 0x82u);
    *(_QWORD *)&UniDest.Length = 8519680;
    UniDest.Buffer = (PWSTR)v33;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)a1);
    v19 = RtlDowncaseUnicodeString(&UniDest, &DestinationString, 0);
    if ( v19 < 0 )
    {
      LastErrorMsg = wil::details::in1diag3::Return_NtStatusMsg(
                       retaddr,
                       (void *)0xB49,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                       (const char *)(unsigned int)v19,
                       (int)"Name %ls",
                       a1);
      goto LABEL_35;
    }
    v28 = 0;
    if ( Sid )
    {
      v5 = AppContainerRegistrationHelper::DeriveChildAppContainerSid(Sid, (char *)UniDest.Buffer, &v28);
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB5D,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v5,
          (int)"Name %ls",
          v33);
LABEL_44:
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v28);
        goto LABEL_36;
      }
    }
    else
    {
      v5 = AppContainerDeriveSidFromMoniker(UniDest.Buffer, &v28);
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB55,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v5,
          (int)"Name %ls",
          v33);
        goto LABEL_44;
      }
    }
    v29 = 0;
    v20 = AppContainerLookupDisplayNameMrtReference(v28, &v29);
    if ( (int)(v20 + 0x80000000) < 0 || v20 == -2147024894 )
      v4 = 0;
    LOBYTE(v22) = v4;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0xB6C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v20,
      v22,
      (bool)"Name %ls",
      a1);
    v5 = 0;
    if ( v20 != -2147024894 )
      v5 = v20;
    v23 = (int)v28;
    v21 = AppContainerRegistrationHelper::DeleteProfileW(Sid, UniDest.Buffer, v29, StringSid);
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB7A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v21,
        (int)"Name %ls display %ls Sid %ls type %d",
        v33,
        v29,
        StringSid,
        a2);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void AppContainerFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void AppContainerFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v28);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
      v5 = v21;
      goto LABEL_55;
    }
    if ( v5 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void AppContainerFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void AppContainerFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v28);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
      v5 = 0;
      goto LABEL_55;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v5,
      v23);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void AppContainerFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void AppContainerFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xB0F,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)(unsigned int)v5,
    (int)"Name %ls",
    a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ca58  mov     [rsp-8+arg_18], rbx
0x18000ca5d  push    rbp
0x18000ca5e  push    rsi
0x18000ca5f  push    rdi
0x18000ca60  push    r12
0x18000ca62  push    r13
0x18000ca64  push    r14
0x18000ca66  push    r15
0x18000ca68  lea     rbp, [rsp-0E0h]
0x18000ca70  sub     rsp, 1E0h
0x18000ca77  mov     rax, cs:__security_cookie
0x18000ca7e  xor     rax, rsp
0x18000ca81  mov     [rbp+110h+var_40], rax
0x18000ca88  mov     r12, r8
0x18000ca8b  mov     r15d, edx
0x18000ca8e  mov     rdi, rcx
0x18000ca91  mov     ecx, 41h ; 'A'
0x18000ca96  lea     r14d, [rcx-40h]
0x18000ca9a  xor     r13d, r13d
0x18000ca9d  test    rdi, rdi
0x18000caa0  jnz     short loc_18000CAB0
0x18000caa2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000caa7  mov     esi, 80070057h
0x18000caac  mov     ebx, esi
0x18000caae  jmp     short loc_18000CAEA
0x18000cab0  mov     rdx, rcx
0x18000cab3  mov     rax, rdi
0x18000cab6  cmp     [rax], r13w
0x18000caba  jz      short loc_18000CAC5
0x18000cabc  add     rax, 2
0x18000cac0  sub     rdx, r14
0x18000cac3  jnz     short loc_18000CAB6
0x18000cac5  mov     rax, rdx
0x18000cac8  sub     rcx, rdx
0x18000cacb  neg     rax
0x18000cace  sbb     r8, r8
0x18000cad1  and     r8, rcx
0x18000cad4  mov     rax, rdx
0x18000cad7  neg     rax
0x18000cada  sbb     ebx, ebx
0x18000cadc  not     ebx
0x18000cade  mov     esi, 80070057h
0x18000cae3  and     ebx, esi
0x18000cae5  test    rdx, rdx
0x18000cae8  jnz     short loc_18000CAED
0x18000caea  mov     r8, r13
0x18000caed  cmp     ebx, esi
0x18000caef  jnz     short loc_18000CB24
0x18000caf1  mov     [rsp+210h+var_1E8], rdi; char *
0x18000caf6  lea     rdx, aNameLs; "Name %ls"
0x18000cafd  mov     [rsp+210h+var_1F0], rdx; int
0x18000cb02  mov     edx, 0B0Eh; void *
0x18000cb07  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cb0e  mov     r9d, esi; char *
0x18000cb11  mov     rcx, [rbp+118h]; this
0x18000cb18  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cb1d  mov     eax, esi
0x18000cb1f  jmp     loc_18000D0E9
0x18000cb24  test    ebx, ebx
0x18000cb26  jns     short loc_18000CB59
0x18000cb28  mov     rcx, [rbp+118h]; this
0x18000cb2f  mov     [rsp+210h+var_1E8], rdi; char *
0x18000cb34  lea     rdx, aNameLs; "Name %ls"
0x18000cb3b  mov     [rsp+210h+var_1F0], rdx; int
0x18000cb40  mov     r9d, ebx; char *
0x18000cb43  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cb4a  mov     edx, 0B0Fh; void *
0x18000cb4f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cb54  jmp     loc_18000D0E7
0x18000cb59  test    r8, r8
0x18000cb5c  jnz     short loc_18000CB76
0x18000cb5e  mov     [rsp+210h+var_1E8], rdi
0x18000cb63  lea     rdx, aNameLs; "Name %ls"
0x18000cb6a  mov     [rsp+210h+var_1F0], rdx
0x18000cb6f  mov     edx, 0B10h
0x18000cb74  jmp     short loc_18000CB07
0x18000cb76  mov     [rbp+110h+token], r13
0x18000cb7a  lea     rdx, [rbp+110h+token]; void **
0x18000cb7e  mov     ecx, 0Eh; char *
0x18000cb83  call    ?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z; AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)
0x18000cb88  mov     ebx, eax
0x18000cb8a  test    eax, eax
0x18000cb8c  jns     short loc_18000CBBF
0x18000cb8e  mov     rcx, [rbp+118h]; this
0x18000cb95  mov     [rsp+210h+var_1E8], rdi; char *
0x18000cb9a  lea     rdx, aNameLs; "Name %ls"
0x18000cba1  mov     [rsp+210h+var_1F0], rdx; int
0x18000cba6  mov     r9d, eax; char *
0x18000cba9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cbb0  mov     edx, 0B15h; void *
0x18000cbb5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cbba  jmp     loc_18000D0DE
0x18000cbbf  mov     [rsp+210h+packageFamilyNameLength], r13d
0x18000cbc4  lea     rdx, [rsp+210h+packageFamilyNameLength]; int *
0x18000cbc9  mov     rbx, [rbp+110h+token]
0x18000cbcd  mov     rcx, rbx; void *
0x18000cbd0  call    ?IsAppContainerToken@AppContainerRegistrationHelper@@SAJPEAXPEAH@Z; AppContainerRegistrationHelper::IsAppContainerToken(void *,int *)
0x18000cbd5  mov     esi, eax
0x18000cbd7  test    eax, eax
0x18000cbd9  jns     short loc_18000CC0E
0x18000cbdb  mov     rcx, [rbp+118h]; this
0x18000cbe2  mov     [rsp+210h+var_1E8], rdi; char *
0x18000cbe7  lea     rdx, aNameLs; "Name %ls"
0x18000cbee  mov     [rsp+210h+var_1F0], rdx; int
0x18000cbf3  mov     r9d, eax; char *
0x18000cbf6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cbfd  mov     edx, 0B19h; void *
0x18000cc02  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cc07  mov     ebx, esi
0x18000cc09  jmp     loc_18000D0DE
0x18000cc0e  mov     [rsp+210h+Sid], r13
0x18000cc13  mov     rcx, rbx; void *
0x18000cc16  cmp     [rsp+210h+packageFamilyNameLength], r13d
0x18000cc1b  jz      short loc_18000CC6F
0x18000cc1d  mov     [rsp+210h+Sid], r13
0x18000cc22  lea     rdx, [rsp+210h+Sid]; void **
0x18000cc27  call    ?GetAppContainerSidFromToken@AppContainerRegistrationHelper@@SAJPEAXPEAPEAX@Z; AppContainerRegistrationHelper::GetAppContainerSidFromToken(void *,void * *)
0x18000cc2c  mov     esi, eax
0x18000cc2e  test    eax, eax
0x18000cc30  jns     loc_18000CD77
0x18000cc36  mov     rcx, [rbp+118h]; this
0x18000cc3d  mov     [rsp+210h+var_1E8], rdi; char *
0x18000cc42  lea     rdx, aNameLs; "Name %ls"
0x18000cc49  mov     [rsp+210h+var_1F0], rdx; int
0x18000cc4e  mov     r9d, eax; char *
0x18000cc51  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cc58  mov     edx, 0B20h; void *
0x18000cc5d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cc62  nop
0x18000cc63  lea     rcx, [rsp+210h+Sid]
0x18000cc68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000cc6d  jmp     short loc_18000CC07
0x18000cc6f  mov     [rsp+210h+packageFamilyNameLength], 210000h
0x18000cc77  lea     r8, [rsp+210h+packageFamilyNameLength]
0x18000cc7c  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18000cc81  cmp     [rsp+210h+packageFamilyNameLength], 210001h
0x18000cc89  jnz     loc_18000CD77
0x18000cc8f  mov     [rsp+210h+packageFamilyNameLength], 41h ; 'A'
0x18000cc97  lea     r8, [rbp+110h+packageFamilyName]; packageFamilyName
0x18000cc9b  lea     rdx, [rsp+210h+packageFamilyNameLength]; packageFamilyNameLength
0x18000cca0  mov     rcx, rbx; token
0x18000cca3  call    cs:__imp_GetPackageFamilyNameFromToken
0x18000ccaa  nop     dword ptr [rax+rax+00h]
0x18000ccaf  test    eax, eax
0x18000ccb1  jz      short loc_18000CCF0
0x18000ccb3  mov     rcx, [rbp+118h]; this
0x18000ccba  mov     [rsp+210h+var_1E8], rdi; char *
0x18000ccbf  lea     rdx, aNameLs; "Name %ls"
0x18000ccc6  mov     [rsp+210h+var_1F0], rdx; unsigned int
0x18000cccb  mov     r9d, eax; char *
0x18000ccce  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ccd5  mov     edx, 0B34h; void *
0x18000ccda  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000ccdf  mov     ebx, eax
0x18000cce1  lea     rcx, [rsp+210h+Sid]
0x18000cce6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000cceb  jmp     loc_18000D0DE
0x18000ccf0  mov     rsi, [rsp+210h+Sid]
0x18000ccf5  test    rsi, rsi
0x18000ccf8  jz      short loc_18000CD1D
0x18000ccfa  lea     rcx, [rsp+210h+var_1B0]; this
0x18000ccff  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cd04  mov     rcx, rsi; Sid
0x18000cd07  call    cs:__imp_RtlFreeSid
0x18000cd0e  nop     dword ptr [rax+rax+00h]
0x18000cd13  lea     rcx, [rsp+210h+var_1B0]; this
0x18000cd18  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000cd1d  mov     [rsp+210h+Sid], r13
0x18000cd22  lea     rdx, [rsp+210h+Sid]
0x18000cd27  lea     rcx, [rbp+110h+packageFamilyName]
0x18000cd2b  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18000cd32  nop     dword ptr [rax+rax+00h]
0x18000cd37  mov     esi, eax
0x18000cd39  test    eax, eax
0x18000cd3b  jns     short loc_18000CD77
0x18000cd3d  mov     rcx, [rbp+118h]; this
0x18000cd44  lea     rax, [rbp+110h+packageFamilyName]
0x18000cd48  mov     [rsp+210h+var_1E0], rax
0x18000cd4d  mov     [rsp+210h+var_1E8], rdi; char *
0x18000cd52  lea     rax, aNameLsFamilyLs; "Name %ls family %ls"
0x18000cd59  mov     [rsp+210h+var_1F0], rax; int
0x18000cd5e  mov     r9d, esi; char *
0x18000cd61  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cd68  mov     edx, 0B37h; void *
0x18000cd6d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cd72  jmp     loc_18000CC63
0x18000cd77  mov     [rsp+210h+var_1B0], r13
0x18000cd7c  lea     rdx, [rsp+210h+var_1B0]; void **
0x18000cd81  mov     rcx, rbx; TokenHandle
0x18000cd84  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18000cd89  mov     ebx, eax
0x18000cd8b  test    eax, eax
0x18000cd8d  jns     short loc_18000CDCB
0x18000cd8f  mov     rcx, [rbp+118h]; this
0x18000cd96  mov     [rsp+210h+var_1E8], rdi; char *
0x18000cd9b  lea     rdx, aNameLs; "Name %ls"
0x18000cda2  mov     [rsp+210h+var_1F0], rdx; int
0x18000cda7  mov     r9d, eax; char *
0x18000cdaa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cdb1  mov     edx, 0B3Ch; void *
0x18000cdb6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cdbb  nop
0x18000cdbc  lea     rcx, [rsp+210h+var_1B0]
0x18000cdc1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000cdc6  jmp     loc_18000CCE1
0x18000cdcb  mov     [rsp+210h+StringSid], r13
0x18000cdd0  xor     edx, edx
0x18000cdd2  lea     rcx, [rsp+210h+StringSid]
0x18000cdd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000cddc  lea     rdx, [rsp+210h+StringSid]; StringSid
0x18000cde1  mov     rcx, [rsp+210h+var_1B0]; Sid
0x18000cde6  call    cs:__imp_ConvertSidToStringSidW
0x18000cded  nop     dword ptr [rax+rax+00h]
0x18000cdf2  test    eax, eax
0x18000cdf4  jnz     short loc_18000CE28
0x18000cdf6  mov     rcx, [rbp+118h]; this
0x18000cdfd  mov     [rsp+210h+var_1F0], rdi; char *
0x18000ce02  lea     r9, aNameLs; "Name %ls"
0x18000ce09  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ce10  mov     edx, 0B3Fh; void *
0x18000ce15  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000ce1a  mov     ebx, eax
0x18000ce1c  lea     rcx, [rsp+210h+StringSid]
0x18000ce21  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000ce26  jmp     short loc_18000CDBC
0x18000ce28  mov     ebx, 82h
0x18000ce2d  mov     r8d, ebx; Size
0x18000ce30  xor     edx, edx; Val
0x18000ce32  lea     rcx, [rbp+110h+var_160]; void *
0x18000ce36  call    memset_0
0x18000ce3b  xorps   xmm0, xmm0
0x18000ce3e  movups  xmmword ptr [rbp+110h+UniDest.Length], xmm0
0x18000ce42  lea     rax, [rbp+110h+var_160]
0x18000ce46  mov     [rbp+110h+UniDest.Buffer], rax
0x18000ce4a  mov     [rbp+110h+UniDest.MaximumLength], bx
0x18000ce4e  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm0
0x18000ce52  mov     rdx, rdi; SourceString
0x18000ce55  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x18000ce59  call    cs:__imp_RtlInitUnicodeString
0x18000ce60  nop     dword ptr [rax+rax+00h]
0x18000ce65  xor     r8d, r8d; AllocateDestinationString
0x18000ce68  lea     rdx, [rbp+110h+DestinationString]; UniSource
0x18000ce6c  lea     rcx, [rbp+110h+UniDest]; UniDest
0x18000ce70  call    cs:__imp_RtlDowncaseUnicodeString
0x18000ce77  nop     dword ptr [rax+rax+00h]
0x18000ce7c  test    eax, eax
0x18000ce7e  jns     short loc_18000CEB1
0x18000ce80  mov     rcx, [rbp+118h]; this
0x18000ce87  mov     [rsp+210h+var_1E8], rdi; char *
0x18000ce8c  lea     rdx, aNameLs; "Name %ls"
0x18000ce93  mov     [rsp+210h+var_1F0], rdx; int
0x18000ce98  mov     r9d, eax; char *
0x18000ce9b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cea2  mov     edx, 0B49h; void *
0x18000cea7  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18000ceac  jmp     loc_18000CE1A
0x18000ceb1  mov     rcx, [rsp+210h+Sid]; pSid
0x18000ceb6  mov     [rsp+210h+var_1A0], r13
0x18000cebb  test    rcx, rcx
0x18000cebe  jz      short loc_18000CEF0
0x18000cec0  lea     r8, [rsp+210h+var_1A0]; Sid
0x18000cec5  mov     rdx, [rbp+110h+UniDest.Buffer]; char *
0x18000cec9  call    ?DeriveChildAppContainerSid@AppContainerRegistrationHelper@@SAJPEAXPEBGPEAPEAX@Z; AppContainerRegistrationHelper::DeriveChildAppContainerSid(void *,ushort const *,void * *)
0x18000cece  mov     ebx, eax
0x18000ced0  test    eax, eax
0x18000ced2  jns     short loc_18000CF4B
0x18000ced4  lea     rax, [rbp+110h+var_160]
0x18000ced8  mov     [rsp+210h+var_1E8], rax
0x18000cedd  lea     rdx, aNameLs; "Name %ls"
0x18000cee4  mov     [rsp+210h+var_1F0], rdx
0x18000cee9  mov     edx, 0B5Dh
0x18000ceee  jmp     short loc_18000CF25
0x18000cef0  lea     rdx, [rsp+210h+var_1A0]
0x18000cef5  mov     rcx, [rbp+110h+UniDest.Buffer]
0x18000cef9  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18000cf00  nop     dword ptr [rax+rax+00h]
0x18000cf05  mov     ebx, eax
0x18000cf07  test    eax, eax
0x18000cf09  jns     short loc_18000CF4B
0x18000cf0b  lea     rax, [rbp+110h+var_160]
0x18000cf0f  mov     [rsp+210h+var_1E8], rax; char *
0x18000cf14  lea     rdx, aNameLs; "Name %ls"
0x18000cf1b  mov     [rsp+210h+var_1F0], rdx; int
0x18000cf20  mov     edx, 0B55h; void *
0x18000cf25  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cf2c  mov     r9d, ebx; char *
0x18000cf2f  mov     rcx, [rbp+118h]; this
0x18000cf36  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cf3b  nop
0x18000cf3c  lea     rcx, [rsp+210h+var_1A0]
0x18000cf41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000cf46  jmp     loc_18000CE1C
0x18000cf4b  mov     [rsp+210h+var_198], r13
0x18000cf50  lea     rdx, [rsp+210h+var_198]
0x18000cf55  mov     rcx, [rsp+210h+var_1A0]
0x18000cf5a  call    cs:__imp_AppContainerLookupDisplayNameMrtReference
0x18000cf61  nop     dword ptr [rax+rax+00h]
0x18000cf66  mov     esi, eax
0x18000cf68  mov     eax, 80000000h
0x18000cf6d  lea     ecx, [rsi+rax]
  ... truncated ...
```
