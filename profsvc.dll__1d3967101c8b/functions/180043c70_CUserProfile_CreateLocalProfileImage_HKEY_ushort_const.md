# CUserProfile::CreateLocalProfileImage(HKEY__ *,ushort const *)

- ea: `0x180043c70`
- end: `0x180043f94`
- name: `?CreateLocalProfileImage@CUserProfile@@IEAAJPEAUHKEY__@@PEBG@Z`
- size: `804`
- prototype: `__int64 __fastcall(CUserProfile *this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b6b8`
- `0x180032ce0`

## callees

- `0x1800049e0`
- `0x1800111a0`
- `0x1800154e0`
- `0x18002541c`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002f738`
- `0x18003ecf8`
- `0x18003f6f4`
- `0x18003fd14`
- `0x180043c70`
- `0x180047cbc`
- `0x18004cdc0`
- `0x18004d208`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043cc2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043cd7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043cec`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043cc2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043cd7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043cec`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043e81`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043e81`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043e8f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043e8f`

## string_xrefs

- `0x180043d2c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043dc0`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043e4b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043ecf`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043f68`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043e99`: `ProfileImagePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180043c70  mov     [rsp-28h+arg_0], rbx
0x180043c75  mov     [rsp-28h+arg_8], rsi
0x180043c7a  push    rbp
0x180043c7b  push    rdi
0x180043c7c  push    r12
0x180043c7e  push    r14
0x180043c80  push    r15
0x180043c82  mov     rbp, rsp
0x180043c85  sub     rsp, 50h
0x180043c89  mov     rdi, r8
0x180043c8c  mov     r12, rdx
0x180043c8f  mov     rsi, rcx
0x180043c92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180043c99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180043c9e  test    al, al
0x180043ca0  jz      short loc_180043CBA
0x180043ca2  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 0
0x180043ca9  jge     short loc_180043CBA
0x180043cab  mov     r8, rdi
0x180043cae  lea     rdx, EVENT_CREATE_LOCAL_PROFILE_START
0x180043cb5  call    McTemplateU0z_EtwEventWriteTransfer
0x180043cba  mov     edx, 25h ; '%'; Ch
0x180043cbf  mov     rcx, rdi; Str
0x180043cc2  call    cs:__imp_wcschr
0x180043cc8  test    rax, rax
0x180043ccb  jnz     loc_180043F5C
0x180043cd1  lea     edx, [rax+5Ch]; Ch
0x180043cd4  mov     rcx, rdi; Str
0x180043cd7  call    cs:__imp_wcschr
0x180043cdd  test    rax, rax
0x180043ce0  jnz     loc_180043F5C
0x180043ce6  lea     edx, [rax+2Fh]; Ch
0x180043ce9  mov     rcx, rdi; Str
0x180043cec  call    cs:__imp_wcschr
0x180043cf2  test    rax, rax
0x180043cf5  jnz     loc_180043F5C
0x180043cfb  lea     r15, [rsi+98h]
0x180043d02  mov     rcx, r15
0x180043d05  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043d0a  mov     [rbp+Sid], 0
0x180043d12  lea     rdx, [rbp+Sid]; void **
0x180043d16  mov     rcx, [rsi+18h]; TokenHandle
0x180043d1a  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180043d1f  mov     ebx, eax
0x180043d21  test    eax, eax
0x180043d23  jns     short loc_180043D42
0x180043d25  mov     rcx, [rbp+28h]; this
0x180043d29  mov     r9d, eax; char *
0x180043d2c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043d33  mov     edx, 4CEh; void *
0x180043d38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043d3d  jmp     loc_180043F51
0x180043d42  mov     [rbp+var_18], 0
0x180043d4a  mov     [rbp+var_10], 0
0x180043d52  mov     [rbp+var_8], 0
0x180043d5a  mov     [rbp+lpFileName], 0
0x180043d62  mov     [rbp+var_28], 0
0x180043d6a  mov     [rbp+var_20], 0
0x180043d72  mov     rcx, [rbp+Sid]; Sid
0x180043d76  call    ?IsVirtualServiceAccount@@YAHPEAX@Z; IsVirtualServiceAccount(void *)
0x180043d7b  lea     rcx, [rbp+lpFileName]
0x180043d7f  test    eax, eax
0x180043d81  jz      short loc_180043DEC
0x180043d83  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043d88  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180043d8c  mov     [rbp+var_28], rbx
0x180043d90  mov     [rbp+var_20], rbx
0x180043d94  lea     rcx, [rbp+var_18]
0x180043d98  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043d9d  mov     [rbp+var_10], rbx
0x180043da1  mov     [rbp+var_8], rbx
0x180043da5  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x180043da9  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180043dad  mov     rcx, rdi; unsigned __int16 *
0x180043db0  call    ?GetVirtualServiceAccountProfileName@@YAJPEBGPEAPEAG1@Z; GetVirtualServiceAccountProfileName(ushort const *,ushort * *,ushort * *)
0x180043db5  mov     edi, eax
0x180043db7  test    eax, eax
0x180043db9  jns     short loc_180043E2F
0x180043dbb  mov     edx, 4D5h; void *
0x180043dc0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043dc7  mov     r9d, edi; char *
0x180043dca  mov     rcx, [rbp+28h]; this
0x180043dce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043dd3  lea     rcx, [rbp+lpFileName]
0x180043dd7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043ddc  lea     rcx, [rbp+var_18]
0x180043de0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043de5  mov     ebx, edi
0x180043de7  jmp     loc_180043F51
0x180043dec  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043df1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180043df5  mov     [rbp+var_28], rbx
0x180043df9  mov     [rbp+var_20], rbx
0x180043dfd  lea     rcx, [rbp+var_18]
0x180043e01  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043e06  mov     [rbp+var_10], rbx
0x180043e0a  mov     [rbp+var_8], rbx
0x180043e0e  lea     r9, [rbp+lpFileName]; unsigned __int16 **
0x180043e12  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180043e16  mov     rdx, rdi; unsigned __int16 *
0x180043e19  mov     rcx, [rsi+18h]; void *
0x180043e1d  call    ?GetLocalProfileName@@YAJPEAXPEBGPEAPEAG2@Z; GetLocalProfileName(void *,ushort const *,ushort * *,ushort * *)
0x180043e22  mov     edi, eax
0x180043e24  test    eax, eax
0x180043e26  jns     short loc_180043E2F
0x180043e28  mov     edx, 4D9h
0x180043e2d  jmp     short loc_180043DC0
0x180043e2f  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180043e33  mov     rdi, [rbp+lpFileName]
0x180043e37  mov     rcx, rdi; unsigned __int16 *
0x180043e3a  call    ?CreateDirectoryForUser@@YAJPEBG0H@Z; CreateDirectoryForUser(ushort const *,ushort const *,int)
0x180043e3f  mov     r14d, eax
0x180043e42  test    eax, eax
0x180043e44  jns     short loc_180043E78
0x180043e46  mov     edx, 4E0h; void *
0x180043e4b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043e52  mov     r9d, r14d; char *
0x180043e55  mov     rcx, [rbp+28h]; this
0x180043e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043e5e  lea     rcx, [rbp+lpFileName]
0x180043e62  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043e67  lea     rcx, [rbp+var_18]
0x180043e6b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043e70  mov     ebx, r14d
0x180043e73  jmp     loc_180043F51
0x180043e78  test    byte ptr [rsi+8], 8
0x180043e7c  jz      short loc_180043E95
0x180043e7e  mov     rcx, rdi; lpFileName
0x180043e81  call    cs:__imp_GetFileAttributesW
0x180043e87  or      eax, 6
0x180043e8a  mov     edx, eax; dwFileAttributes
0x180043e8c  mov     rcx, rdi; lpFileName
0x180043e8f  call    cs:__imp_SetFileAttributesW
0x180043e95  mov     r9, [rbp+var_18]; unsigned __int16 *
0x180043e99  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180043ea0  mov     rcx, r12; HKEY
0x180043ea3  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180043ea8  mov     r14d, eax
0x180043eab  test    eax, eax
0x180043ead  jns     short loc_180043EB6
0x180043eaf  mov     edx, 4EDh
0x180043eb4  jmp     short loc_180043E4B
0x180043eb6  mov     r8, rbx
0x180043eb9  mov     rdx, rdi
0x180043ebc  mov     rcx, r15
0x180043ebf  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180043ec4  mov     ebx, eax
0x180043ec6  test    eax, eax
0x180043ec8  jns     short loc_180043EF6
0x180043eca  mov     edx, 4F0h; void *
0x180043ecf  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043ed6  mov     r9d, eax; char *
0x180043ed9  mov     rcx, [rbp+28h]; this
0x180043edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043ee2  lea     rcx, [rbp+lpFileName]
0x180043ee6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043eeb  lea     rcx, [rbp+var_18]
0x180043eef  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043ef4  jmp     short loc_180043F51
0x180043ef6  cmp     dword ptr [rsi+28h], 0
0x180043efa  jz      short loc_180043F15
0x180043efc  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180043f00  mov     rcx, r12; hKeySrc
0x180043f03  call    ?CopyRedirectedProfileListKeyForSid@@YAJPEAUHKEY__@@PEBG@Z; CopyRedirectedProfileListKeyForSid(HKEY__ *,ushort const *)
0x180043f08  mov     ebx, eax
0x180043f0a  test    eax, eax
0x180043f0c  jns     short loc_180043F15
0x180043f0e  mov     edx, 4F4h
0x180043f13  jmp     short loc_180043ECF
0x180043f15  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180043f1c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180043f21  test    al, al
0x180043f23  jz      short loc_180043F3D
0x180043f25  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 0
0x180043f2c  jge     short loc_180043F3D
0x180043f2e  mov     r8, rdi
0x180043f31  lea     rdx, EVENT_CREATE_LOCAL_PROFILE_SUCCESS
0x180043f38  call    McTemplateU0z_EtwEventWriteTransfer
0x180043f3d  lea     rcx, [rbp+lpFileName]
0x180043f41  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043f46  lea     rcx, [rbp+var_18]
0x180043f4a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043f4f  xor     ebx, ebx
0x180043f51  lea     rcx, [rbp+Sid]
0x180043f55  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043f5a  jmp     short loc_180043F79
0x180043f5c  mov     rcx, [rbp+28h]; this
0x180043f60  mov     ebx, 8007089Ah
0x180043f65  mov     r9d, ebx; char *
0x180043f68  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043f6f  mov     edx, 4C8h; void *
0x180043f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043f79  mov     eax, ebx
0x180043f7b  lea     r11, [rsp+50h+var_s0]
0x180043f80  mov     rbx, [r11+30h]
0x180043f84  mov     rsi, [r11+38h]
0x180043f88  mov     rsp, r11
0x180043f8b  pop     r15
0x180043f8d  pop     r14
0x180043f8f  pop     r12
0x180043f91  pop     rdi
0x180043f92  pop     rbp
0x180043f93  retn
```
