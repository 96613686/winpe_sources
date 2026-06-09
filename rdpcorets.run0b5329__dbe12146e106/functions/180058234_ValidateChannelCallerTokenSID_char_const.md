# ValidateChannelCallerTokenSID(char const *)

- ea: `0x180058234`
- end: `0x1800587d6`
- name: `?ValidateChannelCallerTokenSID@@YAJPEBD@Z`
- size: `1442`
- prototype: `__int64 __fastcall(const char *String1)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ef10`

## callees

- `0x1800036bc`
- `0x180033940`
- `0x180033da0`
- `0x180037e5c`
- `0x180037e7c`
- `0x1800453f0`
- `0x180055e9c`
- `0x180058034`
- `0x180058168`
- `0x18005818c`
- `0x1800581ec`
- `0x180058210`
- `0x180058234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x1800582b9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x1800582da`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x1800582f5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058310`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x18005832b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058346`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058361`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x18005837c`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058417`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x1800582b9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x1800582da`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x1800582f5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058310`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x18005832b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058346`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058361`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x18005837c`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp_l` at `0x180058417`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp_l` at `0x1800583b2`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp_l` at `0x1800583de`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp_l` at `0x1800583b2`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp_l` at `0x1800583de`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x1800587a6`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x1800587a6`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180058294`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180058294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005858d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005858d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800584c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800584c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800584d9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800584d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800585ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800585ea`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18005857f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180058646`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18005857f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180058646`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180058459`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180058459`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005869a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005869a`
- `RPCRT4!RpcRevertToSelf` at `0x18005850f`
- `RPCRT4!RpcRevertToSelf` at `0x180058790`
- `RPCRT4!RpcRevertToSelf` at `0x18005850f`
- `RPCRT4!RpcRevertToSelf` at `0x180058790`
- `RPCRT4!RpcImpersonateClient` at `0x180058496`
- `RPCRT4!RpcImpersonateClient` at `0x180058496`

## string_xrefs

- `0x1800586ec`: `ValidateChannelCallerTokenSID`
- `0x1800586fb`: `Channel blocked - caller is not the expected service`

## pseudocode

```c
__int64 __fastcall ValidateChannelCallerTokenSID(const char *String1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  struct localeinfo_struct *locale; // rax
  struct localeinfo_struct *v5; // r14
  __int64 v6; // rdx
  __int64 v7; // rax
  const WCHAR *v8; // rcx
  BOOL v9; // ebx
  const char *v10; // r9
  int LastError; // eax
  unsigned int v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  HANDLE CurrentThread; // rax
  BOOL v16; // ebx
  const char *v17; // r9
  const char *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  HLOCAL v21; // rax
  int token_information; // eax
  int v23; // r8d
  int v24; // r9d
  void *v25; // r15
  const wchar_t *v26; // rcx
  unsigned int PrivilegeSet; // [rsp+20h] [rbp-E0h]
  int PrivilegeSeta; // [rsp+20h] [rbp-E0h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE ClientToken; // [rsp+68h] [rbp-98h] BYREF
  PPRIVILEGE_SET v32; // [rsp+70h] [rbp-90h] BYREF
  DWORD PrivilegeSetLength; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL AccessStatus; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD GrantedAccess; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp-68h] BYREF
  char v39; // [rsp+A0h] [rbp-60h]
  int v40; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v41; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v42; // [rsp+B8h] [rbp-48h] BYREF
  const char *v43; // [rsp+C0h] [rbp-40h] BYREF
  const char *v44; // [rsp+C8h] [rbp-38h] BYREF
  const char *v45; // [rsp+D0h] [rbp-30h] BYREF
  int v46[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+E0h] [rbp-20h] BYREF
  struct _PRIVILEGE_SET v48; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( String1 )
  {
    locale = _create_locale(0, "C");
    v5 = locale;
    if ( !locale )
    {
      v2 = -2147024882;
      v3 = 122;
      goto LABEL_3;
    }
    if ( !_stricmp_l(String1, "Microsoft::Windows::RDS::Graphics", locale) )
    {
      v6 = 141;
LABEL_23:
      v2 = -2147024891;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
        (const char *)0x80070005LL,
        PrivilegeSet);
LABEL_60:
      _free_locale(v5);
      return v2;
    }
    if ( _stricmp_l(String1, "AUDIO_PLAYBACK_DVC", v5)
      && _stricmp_l(String1, "AUDIO_PLAYBACK_LOSSY_DVC", v5)
      && _stricmp_l(String1, "RDPSND", v5)
      && _stricmp_l(String1, "RDPDR", v5)
      && _stricmp_l(String1, "PNPDR", v5)
      && _stricmp_l(String1, "TSVCTKT", v5)
      && _stricmp_l(String1, "RDCamera_Device_Enumerator", v5) )
    {
      v7 = -1;
      do
        ++v7;
      while ( String1[v7] );
      if ( v7 != 17
        || (unsigned int)_o__strnicmp_l(String1, "RDCamera_Device_", 16, v5)
        || (unsigned __int8)(String1[16] - 48) > 9u )
      {
        if ( !(unsigned int)_o__strnicmp_l(String1, "RDCamera_Device_", 16, v5) )
        {
          v6 = 170;
          goto LABEL_23;
        }
        if ( _stricmp_l(String1, "URBDRMGR", v5) )
          goto LABEL_59;
        v8 = L"O:SYG:SYD:(A;;0x1;;;S-1-5-80-3155263681-2285186309-1774139670-4272879442-822179886)";
      }
      else
      {
        v8 = L"O:SYG:SYD:(A;;0x1;;;S-1-5-80-3915894004-2104103821-3047269622-1811662266-774708259)";
      }
    }
    else
    {
      v8 = L"O:SYG:SYD:(A;;0x1;;;S-1-5-80-2014626298-1656748749-3847481816-918933055-2469338456)";
    }
    pSecurityDescriptor = 0;
    SecurityDescriptor = 0;
    p_pSecurityDescriptor = &pSecurityDescriptor;
    v39 = 1;
    v9 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v8, 1u, &SecurityDescriptor, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pSecurityDescriptor);
    if ( !v9 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBB,
                    (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
                    v10);
LABEL_29:
      v2 = LastError;
LABEL_30:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
      goto LABEL_60;
    }
    v12 = RpcImpersonateClient(0);
    if ( v12 )
    {
      LastError = wil::details::in1diag3::Return_Win32(retaddr, v13, v14, (const char *)v12, PrivilegeSet);
      goto LABEL_29;
    }
    ClientToken = 0;
    p_pSecurityDescriptor = &ClientToken;
    SecurityDescriptor = 0;
    v39 = 1;
    CurrentThread = GetCurrentThread();
    v16 = OpenThreadToken(CurrentThread, 8u, 1, &SecurityDescriptor);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_pSecurityDescriptor);
    if ( !v16 )
    {
      v2 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xC3,
             (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
             v17);
LABEL_35:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
      RpcRevertToSelf();
      goto LABEL_30;
    }
    PrivilegeSetLength = 20;
    GenericMapping = (struct _GENERIC_MAPPING)_mm_load_si128((const __m128i *)&_xmm);
    GrantedAccess = 0;
    memset(&v48, 0, sizeof(v48));
    AccessStatus = 0;
    v32 = 0;
    if ( !AccessCheck(
            pSecurityDescriptor,
            ClientToken,
            1u,
            &GenericMapping,
            &v48,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus) )
    {
      if ( GetLastError() != 122 )
      {
        v19 = 212;
LABEL_39:
        v2 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v19,
               (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
               v18);
LABEL_40:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
        goto LABEL_35;
      }
      if ( !PrivilegeSetLength )
      {
        v2 = -2147418113;
        v20 = 213;
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
          (const char *)v2,
          PrivilegeSeta);
        goto LABEL_40;
      }
      v21 = LocalAlloc(0, PrivilegeSetLength);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v32,
        v21);
      if ( !v32 )
      {
        v2 = -2147024882;
        v20 = 216;
        goto LABEL_43;
      }
      if ( !AccessCheck(
              pSecurityDescriptor,
              ClientToken,
              1u,
              &GenericMapping,
              v32,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus) )
      {
        v19 = 222;
        goto LABEL_39;
      }
    }
    if ( !AccessStatus )
    {
      v41 = 0;
      Block = 0;
      token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, ClientToken);
      v25 = Block;
      if ( token_information >= 0 )
      {
        SecurityDescriptor = 0;
        p_pSecurityDescriptor = (PSECURITY_DESCRIPTOR *)&v41;
        v39 = 1;
        ConvertSidToStringSidW(*(PSID *)Block, (LPWSTR *)&SecurityDescriptor);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pSecurityDescriptor);
      }
      v2 = -2147024891;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v26 = L"<unknown>";
        v43 = String1;
        v40 = 238;
        if ( v41 )
          v26 = v41;
        v45 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp";
        v42 = v26;
        v44 = "ValidateChannelCallerTokenSID";
        *(_QWORD *)v46 = "Channel blocked - caller is not the expected service";
        LODWORD(Block) = -2147024891;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v26,
          (unsigned int)byte_18019973B,
          v23,
          v24,
          (__int64)v46,
          (__int64)&Block,
          (__int64)&v45,
          (__int64)&v40,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
        (const char *)0x80070005LL,
        PrivilegeSeta);
      if ( v25 )
        operator delete(v25);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
      goto LABEL_40;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
    RpcRevertToSelf();
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
LABEL_59:
    v2 = 0;
    goto LABEL_60;
  }
  v2 = -2147418113;
  v3 = 119;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdphlp.cpp",
    (const char *)v2,
    PrivilegeSet);
  return v2;
}

```

## disassembly

```asm
0x180058234  mov     [rsp-8+arg_8], rbx
0x180058239  mov     [rsp-8+arg_10], rsi
0x18005823e  push    rbp
0x18005823f  push    rdi
0x180058240  push    r12
0x180058242  push    r14
0x180058244  push    r15
0x180058246  lea     rbp, [rsp-10h]
0x18005824b  sub     rsp, 110h
0x180058252  mov     rax, cs:__security_cookie
0x180058259  xor     rax, rsp
0x18005825c  mov     [rbp+30h+var_28], rax
0x180058260  xor     r12d, r12d
0x180058263  mov     rsi, rcx
0x180058266  test    rcx, rcx
0x180058269  jnz     short loc_18005828B
0x18005826b  mov     ebx, 8000FFFFh
0x180058270  lea     edx, [rcx+77h]; void *
0x180058273  mov     rcx, [rbp+38h]; this
0x180058277  lea     r8, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005827e  mov     r9d, ebx; char *
0x180058281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058286  jmp     loc_1800587AC
0x18005828b  lea     rdx, Locale; "C"
0x180058292  xor     ecx, ecx; Category
0x180058294  call    cs:__imp__create_locale
0x18005829a  mov     r14, rax
0x18005829d  test    rax, rax
0x1800582a0  jnz     short loc_1800582AC
0x1800582a2  mov     ebx, 8007000Eh
0x1800582a7  lea     edx, [rax+7Ah]
0x1800582aa  jmp     short loc_180058273
0x1800582ac  mov     r8, r14; Locale
0x1800582af  lea     rdx, String2; "Microsoft::Windows::RDS::Graphics"
0x1800582b6  mov     rcx, rsi; String1
0x1800582b9  call    cs:__imp__stricmp_l
0x1800582bf  test    eax, eax
0x1800582c1  jnz     short loc_1800582CD
0x1800582c3  mov     edx, 8Dh
0x1800582c8  jmp     loc_1800583ED
0x1800582cd  mov     r8, r14; Locale
0x1800582d0  lea     rdx, aAudioPlaybackD; "AUDIO_PLAYBACK_DVC"
0x1800582d7  mov     rcx, rsi; String1
0x1800582da  call    cs:__imp__stricmp_l
0x1800582e0  test    eax, eax
0x1800582e2  jz      loc_18005842E
0x1800582e8  mov     r8, r14; Locale
0x1800582eb  lea     rdx, aAudioPlaybackL; "AUDIO_PLAYBACK_LOSSY_DVC"
0x1800582f2  mov     rcx, rsi; String1
0x1800582f5  call    cs:__imp__stricmp_l
0x1800582fb  test    eax, eax
0x1800582fd  jz      loc_18005842E
0x180058303  mov     r8, r14; Locale
0x180058306  lea     rdx, aRdpsnd; "RDPSND"
0x18005830d  mov     rcx, rsi; String1
0x180058310  call    cs:__imp__stricmp_l
0x180058316  test    eax, eax
0x180058318  jz      loc_18005842E
0x18005831e  mov     r8, r14; Locale
0x180058321  lea     rdx, aRdpdr; "RDPDR"
0x180058328  mov     rcx, rsi; String1
0x18005832b  call    cs:__imp__stricmp_l
0x180058331  test    eax, eax
0x180058333  jz      loc_18005842E
0x180058339  mov     r8, r14; Locale
0x18005833c  lea     rdx, aPnpdr; "PNPDR"
0x180058343  mov     rcx, rsi; String1
0x180058346  call    cs:__imp__stricmp_l
0x18005834c  test    eax, eax
0x18005834e  jz      loc_18005842E
0x180058354  mov     r8, r14; Locale
0x180058357  lea     rdx, aTsvctkt; "TSVCTKT"
0x18005835e  mov     rcx, rsi; String1
0x180058361  call    cs:__imp__stricmp_l
0x180058367  test    eax, eax
0x180058369  jz      loc_18005842E
0x18005836f  mov     r8, r14; Locale
0x180058372  lea     rdx, aRdcameraDevice; "RDCamera_Device_Enumerator"
0x180058379  mov     rcx, rsi; String1
0x18005837c  call    cs:__imp__stricmp_l
0x180058382  test    eax, eax
0x180058384  jz      loc_18005842E
0x18005838a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005838e  inc     rax
0x180058391  cmp     [rsi+rax], r12b
0x180058395  jnz     short loc_18005838E
0x180058397  mov     ebx, 10h
0x18005839c  cmp     rax, 11h
0x1800583a0  jnz     short loc_1800583CE
0x1800583a2  mov     r9, r14
0x1800583a5  lea     rdx, aRdcameraDevice_0; "RDCamera_Device_"
0x1800583ac  mov     r8d, ebx
0x1800583af  mov     rcx, rsi
0x1800583b2  call    cs:__imp__o__strnicmp_l
0x1800583b8  test    eax, eax
0x1800583ba  jnz     short loc_1800583CE
0x1800583bc  mov     al, [rsi+10h]
0x1800583bf  sub     al, 30h ; '0'
0x1800583c1  cmp     al, 9
0x1800583c3  ja      short loc_1800583CE
0x1800583c5  lea     rcx, aOSygSydA0x1S15_0; "O:SYG:SYD:(A;;0x1;;;S-1-5-80-3915894004"...
0x1800583cc  jmp     short loc_180058435
0x1800583ce  mov     r9, r14
0x1800583d1  lea     rdx, aRdcameraDevice_0; "RDCamera_Device_"
0x1800583d8  mov     r8, rbx
0x1800583db  mov     rcx, rsi
0x1800583de  call    cs:__imp__o__strnicmp_l
0x1800583e4  test    eax, eax
0x1800583e6  jnz     short loc_18005840A
0x1800583e8  mov     edx, 0AAh; void *
0x1800583ed  mov     rcx, [rbp+38h]; this
0x1800583f1  lea     r8, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800583f8  mov     ebx, 80070005h
0x1800583fd  mov     r9d, ebx; char *
0x180058400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058405  jmp     loc_1800587A3
0x18005840a  mov     r8, r14; Locale
0x18005840d  lea     rdx, aUrbdrmgr; "URBDRMGR"
0x180058414  mov     rcx, rsi; String1
0x180058417  call    cs:__imp__stricmp_l
0x18005841d  test    eax, eax
0x18005841f  jnz     loc_1800587A0
0x180058425  lea     rcx, aOSygSydA0x1S15; "O:SYG:SYD:(A;;0x1;;;S-1-5-80-3155263681"...
0x18005842c  jmp     short loc_180058435
0x18005842e  lea     rcx, aOSygSydA0x1S15_1; "O:SYG:SYD:(A;;0x1;;;S-1-5-80-2014626298"...
0x180058435  mov     edi, 1
0x18005843a  mov     [rsp+130h+pSecurityDescriptor], r12
0x18005843f  lea     rax, [rsp+130h+pSecurityDescriptor]
0x180058444  mov     [rbp+30h+SecurityDescriptor], r12
0x180058448  mov     edx, edi; StringSDRevision
0x18005844a  mov     [rbp+30h+var_A0], rax
0x18005844e  xor     r9d, r9d; SecurityDescriptorSize
0x180058451  mov     [rbp+30h+var_90], dil
0x180058455  lea     r8, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180058459  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005845f  lea     rcx, [rbp+30h+var_A0]
0x180058463  mov     ebx, eax
0x180058465  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005846a  test    ebx, ebx
0x18005846c  jnz     short loc_180058494
0x18005846e  mov     rcx, [rbp+38h]; this
0x180058472  lea     r8, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180058479  mov     edx, 0BBh; void *
0x18005847e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058483  mov     ebx, eax
0x180058485  lea     rcx, [rsp+130h+pSecurityDescriptor]
0x18005848a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005848f  jmp     loc_1800587A3
0x180058494  xor     ecx, ecx; BindingHandle
0x180058496  call    cs:__imp_RpcImpersonateClient
0x18005849c  test    eax, eax
0x18005849e  jz      short loc_1800584AE
0x1800584a0  mov     rcx, [rbp+38h]; this
0x1800584a4  mov     r9d, eax; char *
0x1800584a7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800584ac  jmp     short loc_180058483
0x1800584ae  lea     rax, [rsp+130h+ClientToken]
0x1800584b3  mov     [rsp+130h+ClientToken], r12
0x1800584b8  mov     [rbp+30h+var_A0], rax
0x1800584bc  mov     [rbp+30h+SecurityDescriptor], r12
0x1800584c0  mov     [rbp+30h+var_90], dil
0x1800584c4  call    cs:__imp_GetCurrentThread
0x1800584ca  lea     r9, [rbp+30h+SecurityDescriptor]; TokenHandle
0x1800584ce  mov     r8d, edi; OpenAsSelf
0x1800584d1  mov     rcx, rax; ThreadHandle
0x1800584d4  mov     edx, 8; DesiredAccess
0x1800584d9  call    cs:__imp_OpenThreadToken
0x1800584df  lea     rcx, [rbp+30h+var_A0]
0x1800584e3  mov     ebx, eax
0x1800584e5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800584ea  test    ebx, ebx
0x1800584ec  jnz     short loc_18005851A
0x1800584ee  mov     rcx, [rbp+38h]; this
0x1800584f2  lea     r8, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800584f9  mov     edx, 0C3h; void *
0x1800584fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058503  mov     ebx, eax
0x180058505  lea     rcx, [rsp+130h+ClientToken]
0x18005850a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005850f  call    cs:__imp_RpcRevertToSelf
0x180058515  jmp     loc_180058485
0x18005851a  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x180058522  lea     r9, [rbp+30h+GenericMapping]; GenericMapping
0x180058526  mov     rdx, [rsp+130h+ClientToken]; ClientToken
0x18005852b  xor     eax, eax
0x18005852d  mov     rcx, [rsp+130h+pSecurityDescriptor]; pSecurityDescriptor
0x180058532  xorps   xmm1, xmm1
0x180058535  mov     [rbp+30h+var_40.Privilege.Attributes], eax
0x180058538  mov     r8d, edi; DesiredAccess
0x18005853b  lea     rax, [rsp+130h+var_B4]
0x180058540  mov     [rsp+130h+var_B8], 14h
0x180058548  mov     [rsp+130h+AccessStatus], rax; AccessStatus
0x18005854d  lea     rax, [rbp+30h+var_B0]
0x180058551  mov     [rsp+130h+GrantedAccess], rax; GrantedAccess
0x180058556  lea     rax, [rsp+130h+var_B8]
0x18005855b  mov     [rsp+130h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180058560  lea     rax, [rbp+30h+var_40]
0x180058564  mov     [rsp+130h+PrivilegeSet], rax; int
0x180058569  movups  xmmword ptr [rbp+30h+GenericMapping.GenericRead], xmm0
0x18005856d  mov     [rbp+30h+var_B0], r12d
0x180058571  movups  xmmword ptr [rbp+30h+var_40.PrivilegeCount], xmm1
0x180058575  mov     [rsp+130h+var_B4], r12d
0x18005857a  mov     [rsp+130h+var_C0], r12
0x18005857f  call    cs:__imp_AccessCheck
0x180058585  test    eax, eax
0x180058587  jnz     loc_18005865A
0x18005858d  call    cs:__imp_GetLastError
0x180058593  cmp     eax, 7Ah ; 'z'
0x180058596  jz      short loc_1800585BE
0x180058598  mov     edx, 0D4h; void *
0x18005859d  mov     rcx, [rbp+38h]; this
0x1800585a1  lea     r8, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800585a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800585ad  mov     ebx, eax
0x1800585af  lea     rcx, [rsp+130h+var_C0]
0x1800585b4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800585b9  jmp     loc_180058505
0x1800585be  mov     eax, [rsp+130h+var_B8]
0x1800585c2  test    eax, eax
0x1800585c4  jnz     short loc_1800585E5
0x1800585c6  mov     ebx, 8000FFFFh
0x1800585cb  mov     edx, 0D5h; void *
0x1800585d0  mov     rcx, [rbp+38h]; this
0x1800585d4  lea     r8, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800585db  mov     r9d, ebx; char *
0x1800585de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800585e3  jmp     short loc_1800585AF
0x1800585e5  mov     rdx, rax; uBytes
0x1800585e8  xor     ecx, ecx; uFlags
0x1800585ea  call    cs:__imp_LocalAlloc
0x1800585f0  mov     rdx, rax
0x1800585f3  lea     rcx, [rsp+130h+var_C0]
0x1800585f8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800585fd  mov     rax, [rsp+130h+var_C0]
0x180058602  test    rax, rax
0x180058605  jnz     short loc_180058613
0x180058607  mov     ebx, 8007000Eh
0x18005860c  mov     edx, 0D8h
0x180058611  jmp     short loc_1800585D0
0x180058613  mov     rdx, [rsp+130h+ClientToken]; ClientToken
0x180058618  lea     rcx, [rsp+130h+var_B4]
0x18005861d  mov     [rsp+130h+AccessStatus], rcx; AccessStatus
0x180058622  lea     r9, [rbp+30h+GenericMapping]; GenericMapping
0x180058626  lea     rcx, [rbp+30h+var_B0]
0x18005862a  mov     r8d, edi; DesiredAccess
0x18005862d  mov     [rsp+130h+GrantedAccess], rcx; GrantedAccess
0x180058632  lea     rcx, [rsp+130h+var_B8]
0x180058637  mov     [rsp+130h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x18005863c  mov     rcx, [rsp+130h+pSecurityDescriptor]; pSecurityDescriptor
0x180058641  mov     [rsp+130h+PrivilegeSet], rax; PrivilegeSet
0x180058646  call    cs:__imp_AccessCheck
0x18005864c  test    eax, eax
0x18005864e  jnz     short loc_18005865A
0x180058650  mov     edx, 0DEh
0x180058655  jmp     loc_18005859D
0x18005865a  cmp     [rsp+130h+var_B4], r12d
0x18005865f  jnz     loc_18005877C
0x180058665  mov     rdx, [rsp+130h+ClientToken]
0x18005866a  lea     rcx, [rbp+30h+Block]
0x18005866e  mov     [rbp+30h+var_80], r12
0x180058672  mov     [rbp+30h+Block], r12
0x180058676  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18005867b  mov     r15, [rbp+30h+Block]
0x18005867f  test    eax, eax
0x180058681  js      short loc_1800586A9
0x180058683  lea     rax, [rbp+30h+var_80]
0x180058687  mov     [rbp+30h+SecurityDescriptor], r12
0x18005868b  mov     [rbp+30h+var_A0], rax
0x18005868f  lea     rdx, [rbp+30h+SecurityDescriptor]; StringSid
0x180058693  mov     [rbp+30h+var_90], dil
0x180058697  mov     rcx, [r15]; Sid
0x18005869a  call    cs:__imp_ConvertSidToStringSidW
0x1800586a0  lea     rcx, [rbp+30h+var_A0]
0x1800586a4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800586a9  mov     eax, cs:dword_1801B76C8
0x1800586af  lea     rdi, aClientcoreTerm_6; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800586b6  mov     ebx, 80070005h
0x1800586bb  cmp     eax, 2
0x1800586be  jbe     loc_18005874D
0x1800586c4  mov     rax, [rbp+30h+var_80]
0x1800586c8  lea     rcx, aUnknown; "<unknown>"
0x1800586cf  test    rax, rax
0x1800586d2  mov     [rbp+30h+var_70], rsi
0x1800586d6  lea     rdx, byte_18019973B
0x1800586dd  mov     [rbp+30h+var_88], 0EEh
0x1800586e4  cmovnz  rcx, rax
0x1800586e8  mov     [rbp+30h+var_60], rdi
0x1800586ec  lea     rax, aValidatechanne; "ValidateChannelCallerTokenSID"
0x1800586f3  mov     [rbp+30h+var_78], rcx
0x1800586f7  mov     [rbp+30h+var_68], rax
0x1800586fb  lea     rax, aChannelBlocked; "Channel blocked - caller is not the exp"...
0x180058702  mov     qword ptr [rbp+30h+var_58], rax
0x180058706  lea     rax, [rbp+30h+var_78]
0x18005870a  mov     [rsp+130h+var_E0], rax
0x18005870f  lea     rax, [rbp+30h+var_70]
0x180058713  mov     [rsp+130h+var_E8], rax
0x180058718  lea     rax, [rbp+30h+var_68]
0x18005871c  mov     [rsp+130h+var_F0], rax
0x180058721  lea     rax, [rbp+30h+var_88]
0x180058725  mov     [rsp+130h+AccessStatus], rax
  ... truncated ...
```
