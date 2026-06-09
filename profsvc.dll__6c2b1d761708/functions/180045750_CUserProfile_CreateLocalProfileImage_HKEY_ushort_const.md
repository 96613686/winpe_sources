# CUserProfile::CreateLocalProfileImage(HKEY__ *,ushort const *)

- ea: `0x180045750`
- end: `0x180045a93`
- name: `?CreateLocalProfileImage@CUserProfile@@IEAAJPEAUHKEY__@@PEBG@Z`
- size: `835`
- prototype: `int(CUserProfile *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e1dc`
- `0x18002e63c`

## callees

- `0x18000e1a0`
- `0x1800127a0`
- `0x180012ac8`
- `0x180019260`
- `0x180030ad0`
- `0x180030af8`
- `0x180040428`
- `0x180040e94`
- `0x180041504`
- `0x180045750`
- `0x180049e10`
- `0x1800500c4`
- `0x18005051c`
- `0x180051554`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800457a2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800457bd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800457d8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800457a2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800457bd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800457d8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180045973`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180045973`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180045987`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180045987`

## string_xrefs

- `0x18004581e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800458b2`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18004593d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800459cd`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180045a66`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180045997`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall CUserProfile::CreateLocalProfileImage(CUserProfile *this, HKEY a2, const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  int UserSid; // eax
  unsigned int v8; // ebx
  int VirtualServiceAccountProfileName; // edi
  int v10; // r8d
  __int64 v11; // rdx
  const WCHAR *v12; // rdi
  const unsigned __int16 *v13; // rdx
  int DirectoryForUser; // r14d
  __int64 v15; // rdx
  DWORD FileAttributesW; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  LPCWSTR lpFileName; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+28h] [rbp-28h]
  __int64 v23; // [rsp+30h] [rbp-20h]
  unsigned __int16 *v24; // [rsp+38h] [rbp-18h] BYREF
  __int64 v25; // [rsp+40h] [rbp-10h]
  __int64 v26; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  PSID Sid; // [rsp+98h] [rbp+48h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0z_EtwEventWriteTransfer(v6, EVENT_CREATE_LOCAL_PROFILE_START, a3);
  }
  if ( wcschr(a3, 0x25u) || wcschr(a3, 0x5Cu) || wcschr(a3, 0x2Fu) )
  {
    v8 = -2147022694;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)0x8007089ALL,
      (int)lpFileName);
    return v8;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((char *)this + 152);
  Sid = 0;
  UserSid = GetUserSid(*((HANDLE *)this + 3), &Sid);
  v8 = UserSid;
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)UserSid,
      (int)lpFileName);
    goto LABEL_32;
  }
  v24 = 0;
  v25 = 0;
  v26 = 0;
  lpFileName = 0;
  v22 = 0;
  v23 = 0;
  if ( (unsigned int)IsVirtualServiceAccount(Sid) )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
    v22 = -1;
    v23 = -1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
    v25 = -1;
    v26 = -1;
    VirtualServiceAccountProfileName = GetVirtualServiceAccountProfileName(a3, &v24, (unsigned __int16 **)&lpFileName);
    if ( VirtualServiceAccountProfileName < 0 )
    {
      v11 = 1237;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)VirtualServiceAccountProfileName,
        (int)lpFileName);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
      v8 = VirtualServiceAccountProfileName;
      goto LABEL_32;
    }
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
    v22 = -1;
    v23 = -1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
    v25 = -1;
    v26 = -1;
    VirtualServiceAccountProfileName = GetLocalProfileName(
                                         *((void **)this + 3),
                                         a3,
                                         &v24,
                                         (unsigned __int16 **)&lpFileName);
    if ( VirtualServiceAccountProfileName < 0 )
    {
      v11 = 1241;
      goto LABEL_12;
    }
  }
  v12 = lpFileName;
  DirectoryForUser = CreateDirectoryForUser(lpFileName, *((const unsigned __int16 **)this + 6), v10);
  if ( DirectoryForUser < 0 )
  {
    v15 = 1248;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)DirectoryForUser,
      (int)lpFileName);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
    v8 = DirectoryForUser;
    goto LABEL_32;
  }
  if ( (*((_BYTE *)this + 8) & 8) != 0 )
  {
    FileAttributesW = GetFileAttributesW(v12);
    SetFileAttributesW(v12, FileAttributesW | 6);
  }
  DirectoryForUser = SHRegSetExpandString(a2, v13, L"ProfileImagePath", v24);
  if ( DirectoryForUser < 0 )
  {
    v15 = 1261;
    goto LABEL_17;
  }
  v17 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
          (char *)this + 152,
          v12,
          -1);
  v8 = v17;
  if ( v17 >= 0 )
  {
    if ( !*((_DWORD *)this + 10)
      || (v17 = CopyRedirectedProfileListKeyForSid(a2, *((const unsigned __int16 **)this + 6)), v8 = v17, v17 >= 0) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
      {
        McTemplateU0z_EtwEventWriteTransfer(v19, EVENT_CREATE_LOCAL_PROFILE_SUCCESS, v12);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
      v8 = 0;
      goto LABEL_32;
    }
    v18 = 1268;
  }
  else
  {
    v18 = 1264;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v17,
    (int)lpFileName);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return v8;
}

```

## disassembly

```asm
0x180045750  mov     [rsp-28h+arg_0], rbx
0x180045755  mov     [rsp-28h+arg_8], rsi
0x18004575a  push    rbp
0x18004575b  push    rdi
0x18004575c  push    r12
0x18004575e  push    r14
0x180045760  push    r15
0x180045762  mov     rbp, rsp
0x180045765  sub     rsp, 50h
0x180045769  mov     rdi, r8
0x18004576c  mov     r12, rdx
0x18004576f  mov     rsi, rcx
0x180045772  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180045779  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18004577e  test    al, al
0x180045780  jz      short loc_18004579A
0x180045782  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 0
0x180045789  jge     short loc_18004579A
0x18004578b  mov     r8, rdi
0x18004578e  lea     rdx, EVENT_CREATE_LOCAL_PROFILE_START
0x180045795  call    McTemplateU0z_EtwEventWriteTransfer
0x18004579a  mov     edx, 25h ; '%'; Ch
0x18004579f  mov     rcx, rdi; Str
0x1800457a2  call    cs:__imp_wcschr
0x1800457a9  nop     dword ptr [rax+rax+00h]
0x1800457ae  test    rax, rax
0x1800457b1  jnz     loc_180045A5A
0x1800457b7  lea     edx, [rax+5Ch]; Ch
0x1800457ba  mov     rcx, rdi; Str
0x1800457bd  call    cs:__imp_wcschr
0x1800457c4  nop     dword ptr [rax+rax+00h]
0x1800457c9  test    rax, rax
0x1800457cc  jnz     loc_180045A5A
0x1800457d2  lea     edx, [rax+2Fh]; Ch
0x1800457d5  mov     rcx, rdi; Str
0x1800457d8  call    cs:__imp_wcschr
0x1800457df  nop     dword ptr [rax+rax+00h]
0x1800457e4  test    rax, rax
0x1800457e7  jnz     loc_180045A5A
0x1800457ed  lea     r15, [rsi+98h]
0x1800457f4  mov     rcx, r15
0x1800457f7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800457fc  mov     [rbp+Sid], 0
0x180045804  lea     rdx, [rbp+Sid]; void **
0x180045808  mov     rcx, [rsi+18h]; TokenHandle
0x18004580c  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180045811  mov     ebx, eax
0x180045813  test    eax, eax
0x180045815  jns     short loc_180045834
0x180045817  mov     rcx, [rbp+28h]; this
0x18004581b  mov     r9d, eax; char *
0x18004581e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180045825  mov     edx, 4CEh; void *
0x18004582a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004582f  jmp     loc_180045A4F
0x180045834  mov     [rbp+var_18], 0
0x18004583c  mov     [rbp+var_10], 0
0x180045844  mov     [rbp+var_8], 0
0x18004584c  mov     [rbp+lpFileName], 0
0x180045854  mov     [rbp+var_28], 0
0x18004585c  mov     [rbp+var_20], 0
0x180045864  mov     rcx, [rbp+Sid]; Sid
0x180045868  call    ?IsVirtualServiceAccount@@YAHPEAX@Z; IsVirtualServiceAccount(void *)
0x18004586d  lea     rcx, [rbp+lpFileName]
0x180045871  test    eax, eax
0x180045873  jz      short loc_1800458DE
0x180045875  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004587a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004587e  mov     [rbp+var_28], rbx
0x180045882  mov     [rbp+var_20], rbx
0x180045886  lea     rcx, [rbp+var_18]
0x18004588a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004588f  mov     [rbp+var_10], rbx
0x180045893  mov     [rbp+var_8], rbx
0x180045897  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x18004589b  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x18004589f  mov     rcx, rdi; unsigned __int16 *
0x1800458a2  call    ?GetVirtualServiceAccountProfileName@@YAJPEBGPEAPEAG1@Z; GetVirtualServiceAccountProfileName(ushort const *,ushort * *,ushort * *)
0x1800458a7  mov     edi, eax
0x1800458a9  test    eax, eax
0x1800458ab  jns     short loc_180045921
0x1800458ad  mov     edx, 4D5h; void *
0x1800458b2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800458b9  mov     r9d, edi; char *
0x1800458bc  mov     rcx, [rbp+28h]; this
0x1800458c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800458c5  lea     rcx, [rbp+lpFileName]
0x1800458c9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800458ce  lea     rcx, [rbp+var_18]
0x1800458d2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800458d7  mov     ebx, edi
0x1800458d9  jmp     loc_180045A4F
0x1800458de  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800458e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800458e7  mov     [rbp+var_28], rbx
0x1800458eb  mov     [rbp+var_20], rbx
0x1800458ef  lea     rcx, [rbp+var_18]
0x1800458f3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800458f8  mov     [rbp+var_10], rbx
0x1800458fc  mov     [rbp+var_8], rbx
0x180045900  lea     r9, [rbp+lpFileName]; unsigned __int16 **
0x180045904  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180045908  mov     rdx, rdi; unsigned __int16 *
0x18004590b  mov     rcx, [rsi+18h]; void *
0x18004590f  call    ?GetLocalProfileName@@YAJPEAXPEBGPEAPEAG2@Z; GetLocalProfileName(void *,ushort const *,ushort * *,ushort * *)
0x180045914  mov     edi, eax
0x180045916  test    eax, eax
0x180045918  jns     short loc_180045921
0x18004591a  mov     edx, 4D9h
0x18004591f  jmp     short loc_1800458B2
0x180045921  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180045925  mov     rdi, [rbp+lpFileName]
0x180045929  mov     rcx, rdi; unsigned __int16 *
0x18004592c  call    ?CreateDirectoryForUser@@YAJPEBG0H@Z; CreateDirectoryForUser(ushort const *,ushort const *,int)
0x180045931  mov     r14d, eax
0x180045934  test    eax, eax
0x180045936  jns     short loc_18004596A
0x180045938  mov     edx, 4E0h; void *
0x18004593d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180045944  mov     r9d, r14d; char *
0x180045947  mov     rcx, [rbp+28h]; this
0x18004594b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045950  lea     rcx, [rbp+lpFileName]
0x180045954  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180045959  lea     rcx, [rbp+var_18]
0x18004595d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180045962  mov     ebx, r14d
0x180045965  jmp     loc_180045A4F
0x18004596a  test    byte ptr [rsi+8], 8
0x18004596e  jz      short loc_180045993
0x180045970  mov     rcx, rdi; lpFileName
0x180045973  call    cs:__imp_GetFileAttributesW
0x18004597a  nop     dword ptr [rax+rax+00h]
0x18004597f  or      eax, 6
0x180045982  mov     edx, eax; dwFileAttributes
0x180045984  mov     rcx, rdi; lpFileName
0x180045987  call    cs:__imp_SetFileAttributesW
0x18004598e  nop     dword ptr [rax+rax+00h]
0x180045993  mov     r9, [rbp+var_18]; unsigned __int16 *
0x180045997  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18004599e  mov     rcx, r12; HKEY
0x1800459a1  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800459a6  mov     r14d, eax
0x1800459a9  test    eax, eax
0x1800459ab  jns     short loc_1800459B4
0x1800459ad  mov     edx, 4EDh
0x1800459b2  jmp     short loc_18004593D
0x1800459b4  mov     r8, rbx
0x1800459b7  mov     rdx, rdi
0x1800459ba  mov     rcx, r15
0x1800459bd  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800459c2  mov     ebx, eax
0x1800459c4  test    eax, eax
0x1800459c6  jns     short loc_1800459F4
0x1800459c8  mov     edx, 4F0h; void *
0x1800459cd  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800459d4  mov     r9d, eax; char *
0x1800459d7  mov     rcx, [rbp+28h]; this
0x1800459db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800459e0  lea     rcx, [rbp+lpFileName]
0x1800459e4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800459e9  lea     rcx, [rbp+var_18]
0x1800459ed  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800459f2  jmp     short loc_180045A4F
0x1800459f4  cmp     dword ptr [rsi+28h], 0
0x1800459f8  jz      short loc_180045A13
0x1800459fa  mov     rdx, [rsi+30h]; unsigned __int16 *
0x1800459fe  mov     rcx, r12; hKeySrc
0x180045a01  call    ?CopyRedirectedProfileListKeyForSid@@YAJPEAUHKEY__@@PEBG@Z; CopyRedirectedProfileListKeyForSid(HKEY__ *,ushort const *)
0x180045a06  mov     ebx, eax
0x180045a08  test    eax, eax
0x180045a0a  jns     short loc_180045A13
0x180045a0c  mov     edx, 4F4h
0x180045a11  jmp     short loc_1800459CD
0x180045a13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180045a1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180045a1f  test    al, al
0x180045a21  jz      short loc_180045A3B
0x180045a23  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 0
0x180045a2a  jge     short loc_180045A3B
0x180045a2c  mov     r8, rdi
0x180045a2f  lea     rdx, EVENT_CREATE_LOCAL_PROFILE_SUCCESS
0x180045a36  call    McTemplateU0z_EtwEventWriteTransfer
0x180045a3b  lea     rcx, [rbp+lpFileName]
0x180045a3f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180045a44  lea     rcx, [rbp+var_18]
0x180045a48  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180045a4d  xor     ebx, ebx
0x180045a4f  lea     rcx, [rbp+Sid]
0x180045a53  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180045a58  jmp     short loc_180045A77
0x180045a5a  mov     rcx, [rbp+28h]; this
0x180045a5e  mov     ebx, 8007089Ah
0x180045a63  mov     r9d, ebx; char *
0x180045a66  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180045a6d  mov     edx, 4C8h; void *
0x180045a72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045a77  mov     eax, ebx
0x180045a79  lea     r11, [rsp+50h+var_s0]
0x180045a7e  mov     rbx, [r11+30h]
0x180045a82  mov     rsi, [r11+38h]
0x180045a86  mov     rsp, r11
0x180045a89  pop     r15
0x180045a8b  pop     r14
0x180045a8d  pop     r12
0x180045a8f  pop     rdi
0x180045a90  pop     rbp
0x180045a91  retn
```
