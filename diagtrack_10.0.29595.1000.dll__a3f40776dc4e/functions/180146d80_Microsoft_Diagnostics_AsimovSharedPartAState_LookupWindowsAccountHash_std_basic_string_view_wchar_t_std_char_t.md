# Microsoft::Diagnostics::AsimovSharedPartAState::LookupWindowsAccountHash(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180146d80`
- end: `0x180147278`
- name: `?LookupWindowsAccountHash@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `1272`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180146a58`

## callees

- `0x180002a28`
- `0x1800034c0`
- `0x180003768`
- `0x1800202a4`
- `0x18002abec`
- `0x18002b7c0`
- `0x18002df00`
- `0x18009c8c0`
- `0x1800cf7d8`
- `0x1800e99a0`
- `0x18011bccc`
- `0x180142fcc`
- `0x180146bd4`
- `0x180146d80`
- `0x1801d1b14`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014721e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014721e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180146dd4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180146dd4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180146e8d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180146f2c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180146e8d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180146f2c`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180146fdf`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180146fdf`
- `logoncli!DsGetDcNameW` at `0x18014703c`
- `logoncli!DsGetDcNameW` at `0x18014703c`

## string_xrefs

- `0x18014722b`: `onecore\base\telemetry\utc\service\asimov\asimovsharedpartastate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _DOMAIN_CONTROLLER_INFOW *__fastcall Microsoft::Diagnostics::AsimovSharedPartAState::LookupWindowsAccountHash(
        __int64 a1,
        struct _DOMAIN_CONTROLLER_INFOW *a2)
{
  __int64 v4; // rax
  BOOL v5; // ebx
  signed int LastError; // eax
  int v7; // r8d
  int v8; // r9d
  WCHAR *v9; // rax
  WCHAR *v10; // r8
  signed int v11; // eax
  int v12; // r8d
  int v13; // r9d
  char v14; // bl
  const WCHAR *v15; // rdx
  int v16; // r8d
  LPWSTR *v17; // rdx
  __int64 v18; // rax
  int v19; // r8d
  int v20; // r9d
  __int128 *v21; // r9
  __int128 *v22; // r8
  LPWSTR *v23; // rdx
  LPWSTR *v24; // rdx
  __int64 v25; // rax
  int v26; // r8d
  __int64 v27; // r9
  int v28; // r8d
  int v29; // r9d
  DWORD v30; // eax
  unsigned int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35[4]; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+5Ch] [rbp-A4h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v42[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v43; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[16]; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR v45[2]; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v46; // [rsp+C0h] [rbp-40h]
  LPWSTR Name[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  _BYTE v49[32]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  DomainControllerInfo = a2;
  Sid = 0;
  v4 = std::wstring::wstring(v49);
  if ( *(_QWORD *)(v4 + 24) > 7u )
    v4 = *(_QWORD *)v4;
  v5 = ConvertStringSidToSidW((LPCWSTR)v4, &Sid);
  std::wstring::_Tidy_deallocate(v49);
  if ( !v5 )
  {
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x4000000) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v34 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&word_1803E396E,
        v7,
        v8,
        (__int64)&v34);
    }
    goto LABEL_49;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 122 )
  {
    v30 = GetLastError();
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x215,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\asimovsharedpartastate.cpp",
      (const char *)v30,
      ReferencedDomainName);
LABEL_49:
    std::wstring::wstring(a2, qword_1804625F0);
    goto LABEL_50;
  }
  *(_OWORD *)Name = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Name[0]) = 0;
  *(_OWORD *)v45 = 0;
  v46 = si128;
  LOWORD(v45[0]) = 0;
  std::wstring::resize(Name, cchName);
  std::wstring::resize(v45, cchReferencedDomainName);
  v9 = (WCHAR *)v45;
  if ( v46.m128i_i64[1] > 7uLL )
    v9 = v45[0];
  v10 = (WCHAR *)Name;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = Name[0];
  if ( !LookupAccountSidW(0, Sid, v10, &cchName, v9, &cchReferencedDomainName, &peUse) )
  {
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x4000000) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v34 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&unk_1803E38B8,
        v12,
        v13,
        (__int64)&v34);
    }
    std::wstring::wstring(a2, qword_1804625F0);
    goto LABEL_22;
  }
  std::wstring::resize(Name, cchName);
  std::wstring::resize(v45, cchReferencedDomainName);
  v39 = 0;
  v14 = 0;
  if ( (int)LsaLookupUserAccountType(Sid, &v39) < 0 )
  {
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x4000000) )
    {
      v34 = v28 | 0x10000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)byte_1803E37DD,
        v28 | 0x10000000,
        v29,
        (__int64)&v34);
    }
  }
  else
  {
    if ( ((v39 - 2) & 0xFFFFFFFC) == 0 && v39 != 4 )
    {
      DomainControllerInfo = 0;
      v15 = (const WCHAR *)v45;
      if ( v46.m128i_i64[1] > 7uLL )
        v15 = v45[0];
      if ( DsGetDcNameW(0, v15, 0, 0, 0x40000000u, &DomainControllerInfo) )
      {
        if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x4000000) )
        {
          v34 = v16;
          v17 = v45;
          if ( v46.m128i_i64[1] > 7uLL )
            v17 = (LPWSTR *)v45[0];
          v18 = _tlgWrapBinary<wchar_t,2>(v42, v17, v46.m128i_u32[0]);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
            (unsigned int)&v34,
            (unsigned int)byte_1803E390D,
            v19,
            v20,
            v18,
            (__int64)&v34);
        }
        v43 = *(_OWORD *)std::wstring::operator std::wstring_view(Name, v44);
        v42[0] = *(_OWORD *)std::wstring::operator std::wstring_view(v45, v49);
        v21 = &v43;
        v22 = v42;
        goto LABEL_35;
      }
      v14 = 1;
      std::wstring::assign(v45, DomainControllerInfo->DomainName);
    }
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x4000000) )
    {
      v23 = Name;
      if ( si128.m128i_i64[1] > 7uLL )
        v23 = (LPWSTR *)Name[0];
      _tlgWrapBinary<wchar_t,2>(v49, v23, si128.m128i_u32[0]);
      v24 = v45;
      if ( v46.m128i_i64[1] > 7uLL )
        v24 = (LPWSTR *)v45[0];
      v25 = _tlgWrapBinary<wchar_t,2>(v44, v24, v46.m128i_u32[0]);
      v35[0] = v14;
      v34 = v39;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        v39,
        (unsigned int)word_1803E3832,
        v26,
        v27,
        (__int64)&v34,
        (__int64)v35,
        v25,
        v27);
    }
  }
  v42[0] = *(_OWORD *)std::wstring::operator std::wstring_view(Name, v49);
  v43 = *(_OWORD *)std::wstring::operator std::wstring_view(v45, v44);
  v21 = v42;
  v22 = &v43;
LABEL_35:
  LOBYTE(ReferencedDomainNamea) = v14;
  Microsoft::Diagnostics::AsimovSharedPartAState::HashWindowsAccount(a1, a2, v22, v21, ReferencedDomainNamea);
LABEL_22:
  std::wstring::_Tidy_deallocate(v45);
  std::wstring::_Tidy_deallocate(Name);
LABEL_50:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  return a2;
}

```

## disassembly

```asm
0x180146d80  mov     [rsp-8+arg_18], rbx
0x180146d85  push    rbp
0x180146d86  push    rsi
0x180146d87  push    rdi
0x180146d88  lea     rbp, [rsp-20h]
0x180146d8d  sub     rsp, 120h
0x180146d94  mov     rax, cs:__security_cookie
0x180146d9b  xor     rax, rsp
0x180146d9e  mov     [rbp+30h+var_20], rax
0x180146da2  mov     rdi, rdx
0x180146da5  mov     rsi, rcx
0x180146da8  mov     [rsp+130h+DomainControllerInfo], rdx
0x180146dad  mov     [rsp+130h+Sid], 0
0x180146db6  mov     rdx, r8
0x180146db9  lea     rcx, [rbp+30h+var_40]
0x180146dbd  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180146dc2  cmp     qword ptr [rax+18h], 7
0x180146dc7  jbe     short loc_180146DCC
0x180146dc9  mov     rax, [rax]
0x180146dcc  lea     rdx, [rsp+130h+Sid]; Sid
0x180146dd1  mov     rcx, rax; StringSid
0x180146dd4  call    cs:__imp_ConvertStringSidToSidW
0x180146dda  mov     ebx, eax
0x180146ddc  lea     rcx, [rbp+30h+var_40]
0x180146de0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180146de5  test    ebx, ebx
0x180146de7  jnz     short loc_180146E49
0x180146de9  mov     eax, cs:dword_1804543B0
0x180146def  cmp     eax, 5
0x180146df2  jbe     loc_18014723C
0x180146df8  mov     edx, 4000000h
0x180146dfd  lea     rcx, dword_1804543B0
0x180146e04  call    _tlgKeywordOn
0x180146e09  test    al, al
0x180146e0b  jz      loc_18014723C
0x180146e11  call    cs:__imp_GetLastError
0x180146e17  test    eax, eax
0x180146e19  jle     short loc_180146E23
0x180146e1b  movzx   eax, ax
0x180146e1e  or      eax, 80070000h
0x180146e23  mov     [rsp+130h+var_F0], eax
0x180146e27  lea     rax, [rsp+130h+var_F0]
0x180146e2c  mov     [rsp+130h+ReferencedDomainName], rax
0x180146e31  lea     rdx, word_1803E396E
0x180146e38  lea     rcx, dword_1804543B0
0x180146e3f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180146e44  jmp     loc_18014723C
0x180146e49  mov     [rsp+130h+cchName], 0
0x180146e51  mov     [rsp+130h+var_E4], 0
0x180146e59  mov     [rsp+130h+var_D4], 8
0x180146e61  lea     rax, [rsp+130h+var_D4]
0x180146e66  mov     [rsp+130h+peUse], rax; peUse
0x180146e6b  lea     rax, [rsp+130h+var_E4]
0x180146e70  mov     [rsp+130h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180146e75  mov     [rsp+130h+ReferencedDomainName], 0; unsigned int
0x180146e7e  lea     r9, [rsp+130h+cchName]; cchName
0x180146e83  xor     r8d, r8d; Name
0x180146e86  mov     rdx, [rsp+130h+Sid]; Sid
0x180146e8b  xor     ecx, ecx; lpSystemName
0x180146e8d  call    cs:__imp_LookupAccountSidW
0x180146e93  test    eax, eax
0x180146e95  jnz     loc_18014721E
0x180146e9b  call    cs:__imp_GetLastError
0x180146ea1  cmp     eax, 7Ah ; 'z'
0x180146ea4  jnz     loc_18014721E
0x180146eaa  xorps   xmm0, xmm0
0x180146ead  movups  xmmword ptr [rbp+30h+Name], xmm0
0x180146eb1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180146eb9  movdqu  [rbp+30h+var_50], xmm1
0x180146ebe  xor     eax, eax
0x180146ec0  mov     word ptr [rbp+30h+Name], ax
0x180146ec4  movups  xmmword ptr [rbp+30h+var_80], xmm0
0x180146ec8  movdqu  [rbp+30h+var_70], xmm1
0x180146ecd  mov     word ptr [rbp+30h+var_80], ax
0x180146ed1  mov     edx, [rsp+130h+cchName]
0x180146ed5  lea     rcx, [rbp+30h+Name]
0x180146ed9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180146ede  mov     edx, [rsp+130h+var_E4]
0x180146ee2  lea     rcx, [rbp+30h+var_80]
0x180146ee6  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180146eeb  lea     rax, [rbp+30h+var_80]
0x180146eef  cmp     qword ptr [rbp+30h+var_70+8], 7
0x180146ef4  cmova   rax, [rbp+30h+var_80]
0x180146ef9  lea     r8, [rbp+30h+Name]
0x180146efd  cmp     qword ptr [rbp+30h+var_50+8], 7
0x180146f02  cmova   r8, [rbp+30h+Name]; Name
0x180146f07  lea     rcx, [rsp+130h+var_D4]
0x180146f0c  mov     [rsp+130h+peUse], rcx; peUse
0x180146f11  lea     rcx, [rsp+130h+var_E4]
0x180146f16  mov     [rsp+130h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180146f1b  mov     [rsp+130h+ReferencedDomainName], rax; ReferencedDomainName
0x180146f20  lea     r9, [rsp+130h+cchName]; cchName
0x180146f25  mov     rdx, [rsp+130h+Sid]; Sid
0x180146f2a  xor     ecx, ecx; lpSystemName
0x180146f2c  call    cs:__imp_LookupAccountSidW
0x180146f32  test    eax, eax
0x180146f34  jnz     short loc_180146FB1
0x180146f36  mov     eax, cs:dword_1804543B0
0x180146f3c  cmp     eax, 5
0x180146f3f  jbe     short loc_180146F89
0x180146f41  mov     edx, 4000000h
0x180146f46  lea     rcx, dword_1804543B0
0x180146f4d  call    _tlgKeywordOn
0x180146f52  test    al, al
0x180146f54  jz      short loc_180146F89
0x180146f56  call    cs:__imp_GetLastError
0x180146f5c  test    eax, eax
0x180146f5e  jle     short loc_180146F68
0x180146f60  movzx   eax, ax
0x180146f63  or      eax, 80070000h
0x180146f68  mov     [rsp+130h+var_F0], eax
0x180146f6c  lea     rax, [rsp+130h+var_F0]
0x180146f71  mov     [rsp+130h+ReferencedDomainName], rax
0x180146f76  lea     rdx, unk_1803E38B8
0x180146f7d  lea     rcx, dword_1804543B0
0x180146f84  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180146f89  lea     rdx, qword_1804625F0
0x180146f90  mov     rcx, rdi
0x180146f93  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180146f98  nop
0x180146f99  lea     rcx, [rbp+30h+var_80]
0x180146f9d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180146fa2  nop
0x180146fa3  lea     rcx, [rbp+30h+Name]
0x180146fa7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180146fac  jmp     loc_18014724C
0x180146fb1  mov     edx, [rsp+130h+cchName]
0x180146fb5  lea     rcx, [rbp+30h+Name]
0x180146fb9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180146fbe  mov     edx, [rsp+130h+var_E4]
0x180146fc2  lea     rcx, [rbp+30h+var_80]
0x180146fc6  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180146fcb  mov     [rsp+130h+var_D8], 0
0x180146fd3  xor     bl, bl
0x180146fd5  lea     rdx, [rsp+130h+var_D8]
0x180146fda  mov     rcx, [rsp+130h+Sid]
0x180146fdf  call    cs:__imp_LsaLookupUserAccountType
0x180146fe5  mov     r8d, eax
0x180146fe8  test    eax, eax
0x180146fea  js      loc_18014719E
0x180146ff0  mov     ecx, [rsp+130h+var_D8]
0x180146ff4  lea     eax, [rcx-2]
0x180146ff7  test    eax, 0FFFFFFFCh
0x180146ffc  jnz     loc_180147105
0x180147002  cmp     ecx, 4
0x180147005  jz      loc_180147105
0x18014700b  mov     [rsp+130h+DomainControllerInfo], 0
0x180147014  lea     rdx, [rbp+30h+var_80]
0x180147018  cmp     qword ptr [rbp+30h+var_70+8], 7
0x18014701d  cmova   rdx, [rbp+30h+var_80]; DomainName
0x180147022  lea     rax, [rsp+130h+DomainControllerInfo]
0x180147027  mov     [rsp+130h+cchReferencedDomainName], rax; DomainControllerInfo
0x18014702c  mov     dword ptr [rsp+130h+ReferencedDomainName], 40000000h; Flags
0x180147034  xor     r9d, r9d; SiteName
0x180147037  xor     r8d, r8d; DomainGuid
0x18014703a  xor     ecx, ecx; ComputerName
0x18014703c  call    cs:__imp_DsGetDcNameW
0x180147042  mov     r8d, eax
0x180147045  test    eax, eax
0x180147047  jz      loc_1801470F1
0x18014704d  mov     ecx, cs:dword_1804543B0
0x180147053  cmp     ecx, 5
0x180147056  jbe     short loc_1801470A9
0x180147058  mov     edx, 4000000h
0x18014705d  lea     rcx, dword_1804543B0
0x180147064  call    _tlgKeywordOn
0x180147069  test    al, al
0x18014706b  jz      short loc_1801470A9
0x18014706d  mov     [rsp+130h+var_F0], r8d
0x180147072  lea     rdx, [rbp+30h+var_80]
0x180147076  cmp     qword ptr [rbp+30h+var_70+8], 7
0x18014707b  cmova   rdx, [rbp+30h+var_80]
0x180147080  mov     r8d, dword ptr [rbp+30h+var_70]
0x180147084  lea     rcx, [rsp+130h+var_C0]
0x180147089  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18014708e  lea     rcx, [rsp+130h+var_F0]
0x180147093  mov     [rsp+130h+cchReferencedDomainName], rcx
0x180147098  mov     [rsp+130h+ReferencedDomainName], rax
0x18014709d  lea     rdx, byte_1803E390D
0x1801470a4  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x1801470a9  lea     rdx, [rbp+30h+var_90]
0x1801470ad  lea     rcx, [rbp+30h+Name]
0x1801470b1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801470b6  movups  xmm0, xmmword ptr [rax]
0x1801470b9  movdqu  [rbp+30h+var_A0], xmm0
0x1801470be  lea     rdx, [rbp+30h+var_40]
0x1801470c2  lea     rcx, [rbp+30h+var_80]
0x1801470c6  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801470cb  movups  xmm0, xmmword ptr [rax]
0x1801470ce  movdqu  [rsp+130h+var_C0], xmm0
0x1801470d4  lea     r9, [rbp+30h+var_A0]
0x1801470d8  lea     r8, [rsp+130h+var_C0]
0x1801470dd  mov     byte ptr [rsp+130h+ReferencedDomainName], bl
0x1801470e1  mov     rdx, rdi
0x1801470e4  mov     rcx, rsi
0x1801470e7  call    ?HashWindowsAccount@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@0_N@Z; Microsoft::Diagnostics::AsimovSharedPartAState::HashWindowsAccount(std::wstring_view,std::wstring_view,bool)
0x1801470ec  jmp     loc_180146F99
0x1801470f1  mov     bl, 1
0x1801470f3  mov     rdx, [rsp+130h+DomainControllerInfo]
0x1801470f8  mov     rdx, [rdx+28h]
0x1801470fc  lea     rcx, [rbp+30h+var_80]
0x180147100  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180147105  mov     eax, cs:dword_1804543B0
0x18014710b  cmp     eax, 5
0x18014710e  jbe     loc_1801471E5
0x180147114  mov     edx, 4000000h
0x180147119  lea     rcx, dword_1804543B0
0x180147120  call    _tlgKeywordOn
0x180147125  test    al, al
0x180147127  jz      loc_1801471E5
0x18014712d  lea     rdx, [rbp+30h+Name]
0x180147131  cmp     qword ptr [rbp+30h+var_50+8], 7
0x180147136  cmova   rdx, [rbp+30h+Name]
0x18014713b  mov     r8d, dword ptr [rbp+30h+var_50]
0x18014713f  lea     rcx, [rbp+30h+var_40]
0x180147143  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180147148  mov     r9, rax
0x18014714b  lea     rdx, [rbp+30h+var_80]
0x18014714f  cmp     qword ptr [rbp+30h+var_70+8], 7
0x180147154  cmova   rdx, [rbp+30h+var_80]
0x180147159  mov     r8d, dword ptr [rbp+30h+var_70]
0x18014715d  lea     rcx, [rbp+30h+var_90]
0x180147161  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180147166  mov     [rsp+130h+var_EC], bl
0x18014716a  mov     ecx, [rsp+130h+var_D8]
0x18014716e  mov     [rsp+130h+var_F0], ecx
0x180147172  mov     [rsp+130h+var_F8], r9
0x180147177  mov     [rsp+130h+peUse], rax
0x18014717c  lea     rax, [rsp+130h+var_EC]
0x180147181  mov     [rsp+130h+cchReferencedDomainName], rax
0x180147186  lea     rax, [rsp+130h+var_F0]
0x18014718b  mov     [rsp+130h+ReferencedDomainName], rax
0x180147190  lea     rdx, word_1803E3832
0x180147197  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperArray@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperArray@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x18014719c  jmp     short loc_1801471E5
0x18014719e  mov     eax, cs:dword_1804543B0
0x1801471a4  cmp     eax, 5
0x1801471a7  jbe     short loc_1801471E5
0x1801471a9  mov     edx, 4000000h
0x1801471ae  lea     rcx, dword_1804543B0
0x1801471b5  call    _tlgKeywordOn
0x1801471ba  test    al, al
0x1801471bc  jz      short loc_1801471E5
0x1801471be  bts     r8d, 1Ch
0x1801471c3  mov     [rsp+130h+var_F0], r8d
0x1801471c8  lea     rax, [rsp+130h+var_F0]
0x1801471cd  mov     [rsp+130h+ReferencedDomainName], rax
0x1801471d2  lea     rdx, byte_1803E37DD
0x1801471d9  lea     rcx, dword_1804543B0
0x1801471e0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801471e5  lea     rdx, [rbp+30h+var_40]
0x1801471e9  lea     rcx, [rbp+30h+Name]
0x1801471ed  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801471f2  movups  xmm0, xmmword ptr [rax]
0x1801471f5  movdqu  [rsp+130h+var_C0], xmm0
0x1801471fb  lea     rdx, [rbp+30h+var_90]
0x1801471ff  lea     rcx, [rbp+30h+var_80]
0x180147203  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180147208  movups  xmm0, xmmword ptr [rax]
0x18014720b  movdqu  [rbp+30h+var_A0], xmm0
0x180147210  lea     r9, [rsp+130h+var_C0]
0x180147215  lea     r8, [rbp+30h+var_A0]
0x180147219  jmp     loc_1801470DD
0x18014721e  call    cs:__imp_GetLastError
0x180147224  mov     r9d, eax; char *
0x180147227  mov     rcx, [rbp+38h]; this
0x18014722b  lea     r8, aOnecoreBaseTel_239; "onecore\\base\\telemetry\\utc\\service"...
0x180147232  mov     edx, 215h; void *
0x180147237  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18014723c  lea     rdx, qword_1804625F0
0x180147243  mov     rcx, rdi
0x180147246  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18014724b  nop
0x18014724c  lea     rcx, [rsp+130h+Sid]
0x180147251  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180147256  mov     rax, rdi
0x180147259  mov     rcx, [rbp+30h+var_20]
0x18014725d  xor     rcx, rsp; StackCookie
0x180147260  call    __security_check_cookie
0x180147265  mov     rbx, [rsp+130h+arg_18]
0x18014726d  add     rsp, 120h
0x180147274  pop     rdi
0x180147275  pop     rsi
0x180147276  pop     rbp
0x180147277  retn
```
