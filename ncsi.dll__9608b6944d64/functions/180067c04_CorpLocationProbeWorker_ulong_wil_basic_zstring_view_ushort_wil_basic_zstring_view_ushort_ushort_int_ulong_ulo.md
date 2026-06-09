# CorpLocationProbeWorker(ulong,wil::basic_zstring_view<ushort>,wil::basic_zstring_view<ushort>,ushort,int *,ulong &,ulong &)

- ea: `0x180067c04`
- end: `0x1800682f3`
- name: `?CorpLocationProbeWorker@@YA_NKV?$basic_zstring_view@G@wil@@0GPEAHAEAK2@Z`
- size: `1775`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005ee90`

## callees

- `0x180003da4`
- `0x18000d188`
- `0x180013e48`
- `0x1800299cc`
- `0x18002cf38`
- `0x180032474`
- `0x18003ee84`
- `0x180047240`
- `0x180047f78`
- `0x180051ab8`
- `0x18006082c`
- `0x180067c04`
- `0x180068e50`
- `0x180068ecc`
- `0x180068fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006817a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800681c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006826f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006817a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800681c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006826f`
- `WINHTTP!WinHttpConnect` at `0x180067f60`
- `WINHTTP!WinHttpConnect` at `0x180067f60`
- `WINHTTP!WinHttpOpenRequest` at `0x180067fe8`
- `WINHTTP!WinHttpOpenRequest` at `0x180067fe8`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800680d4`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800680d4`
- `WINHTTP!WinHttpSendRequest` at `0x180068170`
- `WINHTTP!WinHttpSendRequest` at `0x180068170`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800681b9`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800681b9`
- `WINHTTP!WinHttpQueryHeaders` at `0x18006823a`
- `WINHTTP!WinHttpQueryHeaders` at `0x18006823a`
- `WINHTTP!WinHttpOpen` at `0x180067d8d`
- `WINHTTP!WinHttpOpen` at `0x180067d8d`
- `WINHTTP!WinHttpSetOption` at `0x180067dfd`
- `WINHTTP!WinHttpSetOption` at `0x180067e54`
- `WINHTTP!WinHttpSetOption` at `0x180067ef4`
- `WINHTTP!WinHttpSetOption` at `0x1800680aa`
- `WINHTTP!WinHttpSetOption` at `0x1800680f1`
- `WINHTTP!WinHttpSetOption` at `0x18006810e`
- `WINHTTP!WinHttpSetOption` at `0x18006812b`
- `WINHTTP!WinHttpSetOption` at `0x180068148`
- `WINHTTP!WinHttpSetOption` at `0x180067dfd`
- `WINHTTP!WinHttpSetOption` at `0x180067e54`
- `WINHTTP!WinHttpSetOption` at `0x180067ef4`
- `WINHTTP!WinHttpSetOption` at `0x1800680aa`
- `WINHTTP!WinHttpSetOption` at `0x1800680f1`
- `WINHTTP!WinHttpSetOption` at `0x18006810e`
- `WINHTTP!WinHttpSetOption` at `0x18006812b`
- `WINHTTP!WinHttpSetOption` at `0x180068148`

## string_xrefs

- `0x1800682c3`: `Outside`
- `0x1800682cf`: `Inside`

## pseudocode

```c
char __fastcall CorpLocationProbeWorker(
        Ncsi::Power *a1,
        __int64 *a2,
        __int64 *a3,
        INTERNET_PORT a4,
        _DWORD *a5,
        DWORD *a6,
        _DWORD *lpBuffer)
{
  Ncsi::Power *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int v13; // edx
  __int64 v14; // r8
  __int64 v15; // r9
  char v16; // di
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbx
  DWORD LastError; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  NcsiConfigData *v22; // rcx
  __int64 v23; // r8
  unsigned __int16 *v24; // rax
  DWORD v25; // eax
  void *v26; // rax
  void *v27; // rbx
  DWORD v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  DWORD v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdx
  int v34; // r8d
  const char *v35; // rdx
  const char *v37; // [rsp+48h] [rbp-A9h] BYREF
  const char *v38; // [rsp+50h] [rbp-A1h] BYREF
  void *v39; // [rsp+58h] [rbp-99h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-91h] BYREF
  int v41; // [rsp+68h] [rbp-89h] BYREF
  unsigned __int16 v42; // [rsp+6Ch] [rbp-85h] BYREF
  unsigned __int8 v43; // [rsp+6Eh] [rbp-83h]
  int v44; // [rsp+70h] [rbp-81h] BYREF
  DWORD dwBufferLength; // [rsp+74h] [rbp-7Dh] BYREF
  _OWORD Buffer[2]; // [rsp+78h] [rbp-79h] BYREF
  _BYTE v47[64]; // [rsp+A0h] [rbp-51h] BYREF

  v40 = (unsigned int)a1;
  if ( Ncsi::Power::IsSystemInStandby(a1) && Ncsi::Power::ShouldDisconnectInStandby(v9) )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v38 = "Abandoning CorpLocationProbeWorker in disconnected standby";
      v37 = "CorpLocationProbeWorker - Exiting";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (int)&dword_18009A048,
        (int)&dword_18008B70C,
        v10,
        v11,
        (const unsigned __int16 **)&v37,
        (const unsigned __int16 **)&v38);
    }
    return 0;
  }
  memset_0(v47, 0, sizeof(v47));
  Ncsi::Power::ReferenceAllNetworkInterfaces(v47, 6, 60000);
  if ( !Ncsi::Power::AutoPdcNetworkRef::ActivationAcquired((Ncsi::Power::AutoPdcNetworkRef *)v47) )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v38 = "Abandoning ActiveCorpLocationProbe check as ReferenceAllNetworkInterfaces returned ActivationAcquired is false";
      v37 = "CorpLocationProbeWorker - Exiting";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (int)&dword_18009A048,
        (int)&byte_18008BDC7,
        v14,
        v15,
        (const unsigned __int16 **)&v37,
        (const unsigned __int16 **)&v38);
    }
    goto LABEL_9;
  }
  *a5 = 0;
  *a6 = 0;
  *lpBuffer = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_DSS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v13, v14, v40, *a2, *a3);
  }
  v16 = 1;
  v17 = (unsigned __int16 *)WinHttpOpen(0, 1u, 0, 0, 0);
  v37 = (const char *)v17;
  v18 = v17;
  if ( !v17 )
  {
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_39;
    }
    v21 = 41;
LABEL_38:
    WPP_SF_dd(*(_QWORD *)(v20 + 16), v21, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids, v40, LastError);
LABEL_39:
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
LABEL_9:
    Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef((Ncsi::Power::AutoPdcNetworkRef *)v47);
    return 0;
  }
  memset(Buffer, 0, sizeof(Buffer));
  HIDWORD(Buffer[0]) = 3;
  if ( !WinHttpSetOption(v17, 0xAAu, Buffer, 0x20u) )
  {
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_39;
    }
    v21 = 42;
    goto LABEL_38;
  }
  if ( !WinHttpSetOption(v18, 0x69u, &v40, 4u) )
  {
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_39;
    }
    v21 = 43;
    goto LABEL_38;
  }
  NcsiConfigData::GetCorpLocationTcpRtoParameters(v22);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_DDD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v42, v23, v40, v42, v43);
  }
  if ( !WinHttpSetOption(v18, 0x71u, &v42, 4u) )
  {
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_39;
    }
    v21 = 45;
    goto LABEL_38;
  }
  v24 = (unsigned __int16 *)WinHttpConnect(v18, (LPCWSTR)*a2, a4, 0);
  v38 = (const char *)v24;
  if ( !v24 )
  {
    v25 = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids, v40, v25);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
    goto LABEL_39;
  }
  v26 = WinHttpOpenRequest(v24, L"GET", (LPCWSTR)*a3, 0, 0, 0, 0x800000u);
  v39 = v26;
  v27 = v26;
  if ( v26 )
  {
    v44 = 8;
    if ( !WinHttpSetOption(v26, 0x3Fu, &v44, 4u) )
      goto LABEL_52;
    v41 = 1000 * dword_18009B3CC;
    if ( !WinHttpSetTimeouts(v27, 0, 1000 * dword_18009B3CC, 1000 * dword_18009B3CC, 1000 * dword_18009B3CC)
      || !WinHttpSetOption(v27, 3u, &v41, 4u)
      || !WinHttpSetOption(v27, 7u, &v41, 4u)
      || !WinHttpSetOption(v27, 6u, &v41, 4u)
      || !WinHttpSetOption(v27, 5u, &v41, 4u) )
    {
      goto LABEL_52;
    }
    if ( WinHttpSendRequest(v27, 0, 0, 0, 0, 0, 0) )
    {
      if ( WinHttpReceiveResponse(v27, 0) )
      {
        dwBufferLength = 4;
        if ( WinHttpQueryHeaders(v27, 0x20000013u, 0, lpBuffer, &dwBufferLength, 0) )
        {
          if ( (unsigned int)(*lpBuffer - 200) <= 0x63 )
            *a5 = 1;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          {
            v35 = "Inside";
            if ( !*a5 )
              v35 = "Outside";
            WPP_SF_DsD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (_DWORD)v35, v34, v40, (__int64)v35, *lpBuffer);
          }
          goto LABEL_53;
        }
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_52;
        }
        v28 = GetLastError();
        v29 = WPP_GLOBAL_Control;
        v30 = 50;
        goto LABEL_51;
      }
      v31 = GetLastError();
      *a6 = v31;
      v32 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
      {
        goto LABEL_53;
      }
      v33 = 49;
    }
    else
    {
      v31 = GetLastError();
      *a6 = v31;
      v32 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
      {
        goto LABEL_53;
      }
      v33 = 48;
    }
    WPP_SF_dd(*(_QWORD *)(v32 + 16), v33, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids, v40, v31);
    goto LABEL_53;
  }
  v28 = GetLastError();
  v29 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
    || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
  {
    goto LABEL_52;
  }
  v30 = 47;
LABEL_51:
  WPP_SF_dd(*(_QWORD *)(v29 + 16), v30, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids, v40, v28);
LABEL_52:
  v16 = 0;
LABEL_53:
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v39);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
  Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef((Ncsi::Power::AutoPdcNetworkRef *)v47);
  return v16;
}

```

## disassembly

```asm
0x180067c04  push    rbp
0x180067c06  push    rbx
0x180067c07  push    rsi
0x180067c08  push    rdi
0x180067c09  push    r12
0x180067c0b  push    r13
0x180067c0d  push    r14
0x180067c0f  push    r15
0x180067c11  lea     rbp, [rsp-7]
0x180067c16  sub     rsp, 0F8h
0x180067c1d  mov     rax, cs:__security_cookie
0x180067c24  xor     rax, rsp
0x180067c27  mov     [rbp+3Fh+var_50], rax
0x180067c2b  mov     r15, [rbp+3Fh+arg_20]
0x180067c2f  mov     r13, r8
0x180067c32  mov     r14, [rbp+3Fh+arg_28]
0x180067c36  mov     r12, rdx
0x180067c39  mov     rsi, [rbp+3Fh+lpBuffer]
0x180067c3d  mov     [rsp+130h+var_F0], r9w
0x180067c43  mov     [rsp+130h+var_D0], ecx
0x180067c47  call    ?IsSystemInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::IsSystemInStandby(void)
0x180067c4c  xor     ebx, ebx
0x180067c4e  test    al, al
0x180067c50  jz      short loc_180067CAC
0x180067c52  call    ?ShouldDisconnectInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::ShouldDisconnectInStandby(void)
0x180067c57  test    al, al
0x180067c59  jz      short loc_180067CAC
0x180067c5b  mov     eax, cs:dword_18009A048
0x180067c61  cmp     eax, 5
0x180067c64  jbe     short loc_180067CA5
0x180067c66  lea     rax, aAbandoningCorp; "Abandoning CorpLocationProbeWorker in d"...
0x180067c6d  mov     [rsp+130h+var_E0], rax
0x180067c72  lea     rdx, dword_18008B70C
0x180067c79  lea     rax, aCorplocationpr_0; "CorpLocationProbeWorker - Exiting"
0x180067c80  mov     [rsp+130h+var_E8], rax
0x180067c85  lea     rcx, dword_18009A048
0x180067c8c  lea     rax, [rsp+130h+var_E0]
0x180067c91  mov     [rsp+130h+ppwszAcceptTypes], rax
0x180067c96  lea     rax, [rsp+130h+var_E8]
0x180067c9b  mov     qword ptr [rsp+130h+dwFlags], rax
0x180067ca0  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180067ca5  xor     al, al
0x180067ca7  jmp     loc_18006806D
0x180067cac  xor     edx, edx; Val
0x180067cae  lea     rcx, [rbp+3Fh+var_90]; void *
0x180067cb2  lea     r8d, [rdx+40h]; Size
0x180067cb6  call    memset_0
0x180067cbb  mov     edx, 6
0x180067cc0  lea     rcx, [rbp+3Fh+var_90]
0x180067cc4  mov     r8d, 0EA60h
0x180067cca  call    ?ReferenceAllNetworkInterfaces@Power@Ncsi@@YA?AVAutoPdcNetworkRef@12@W4NetworkRefReason@12@K@Z; Ncsi::Power::ReferenceAllNetworkInterfaces(Ncsi::Power::NetworkRefReason,ulong)
0x180067ccf  lea     rcx, [rbp+3Fh+var_90]; this
0x180067cd3  call    ?ActivationAcquired@AutoPdcNetworkRef@Power@Ncsi@@QEBA_NXZ; Ncsi::Power::AutoPdcNetworkRef::ActivationAcquired(void)
0x180067cd8  test    al, al
0x180067cda  jnz     short loc_180067D34
0x180067cdc  mov     eax, cs:dword_18009A048
0x180067ce2  cmp     eax, 5
0x180067ce5  jbe     short loc_180067D26
0x180067ce7  lea     rax, aAbandoningActi_0; "Abandoning ActiveCorpLocationProbe chec"...
0x180067cee  mov     [rsp+130h+var_E0], rax
0x180067cf3  lea     rdx, byte_18008BDC7
0x180067cfa  lea     rax, aCorplocationpr_0; "CorpLocationProbeWorker - Exiting"
0x180067d01  mov     [rsp+130h+var_E8], rax
0x180067d06  lea     rcx, dword_18009A048
0x180067d0d  lea     rax, [rsp+130h+var_E0]
0x180067d12  mov     [rsp+130h+ppwszAcceptTypes], rax
0x180067d17  lea     rax, [rsp+130h+var_E8]
0x180067d1c  mov     qword ptr [rsp+130h+dwFlags], rax
0x180067d21  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180067d26  lea     rcx, [rbp+3Fh+var_90]; this
0x180067d2a  call    ??1AutoPdcNetworkRef@Power@Ncsi@@QEAA@XZ; Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef(void)
0x180067d2f  jmp     loc_180067CA5
0x180067d34  mov     [r15], ebx
0x180067d37  mov     [r14], ebx
0x180067d3a  mov     [rsi], ebx
0x180067d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067d43  lea     rax, WPP_GLOBAL_Control
0x180067d4a  cmp     rcx, rax
0x180067d4d  jz      short loc_180067D7B
0x180067d4f  test    byte ptr [rcx+1Ch], 10h
0x180067d53  jz      short loc_180067D7B
0x180067d55  cmp     byte ptr [rcx+19h], 5
0x180067d59  jb      short loc_180067D7B
0x180067d5b  mov     rax, [r13+0]
0x180067d5f  mov     r9d, [rsp+130h+var_D0]
0x180067d64  mov     rcx, [rcx+10h]
0x180067d68  mov     [rsp+130h+ppwszAcceptTypes], rax
0x180067d6d  mov     rax, [r12]
0x180067d71  mov     qword ptr [rsp+130h+dwFlags], rax
0x180067d76  call    WPP_SF_DSS
0x180067d7b  xor     r9d, r9d; pszProxyBypassW
0x180067d7e  mov     [rsp+130h+dwFlags], ebx; dwFlags
0x180067d82  xor     r8d, r8d; pszProxyW
0x180067d85  xor     ecx, ecx; pszAgentW
0x180067d87  lea     edi, [r9+1]
0x180067d8b  mov     edx, edi; dwAccessType
0x180067d8d  call    cs:__imp_WinHttpOpen
0x180067d93  mov     [rsp+130h+var_E8], rax
0x180067d98  mov     rbx, rax
0x180067d9b  test    rax, rax
0x180067d9e  jnz     short loc_180067DD9
0x180067da0  call    cs:__imp_GetLastError
0x180067da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180067dad  lea     rdx, WPP_GLOBAL_Control
0x180067db4  cmp     rcx, rdx
0x180067db7  jz      loc_180067F41
0x180067dbd  test    byte ptr [rcx+1Ch], 10h
0x180067dc1  jz      loc_180067F41
0x180067dc7  cmp     byte ptr [rcx+19h], 2
0x180067dcb  jb      loc_180067F41
0x180067dd1  lea     edx, [rdi+28h]
0x180067dd4  jmp     loc_180067F28
0x180067dd9  xorps   xmm0, xmm0
0x180067ddc  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x180067de0  movups  [rbp+3Fh+Buffer], xmm0
0x180067de4  mov     r9d, 20h ; ' '; dwBufferLength
0x180067dea  mov     dword ptr [rbp+3Fh+Buffer+0Ch], 3
0x180067df1  mov     edx, 0AAh; dwOption
0x180067df6  mov     rcx, rbx; hInternet
0x180067df9  movups  [rbp+3Fh+var_A8], xmm0
0x180067dfd  call    cs:__imp_WinHttpSetOption
0x180067e03  test    eax, eax
0x180067e05  jnz     short loc_180067E42
0x180067e07  call    cs:__imp_GetLastError
0x180067e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e14  lea     rdx, WPP_GLOBAL_Control
0x180067e1b  cmp     rcx, rdx
0x180067e1e  jz      loc_180067F41
0x180067e24  test    byte ptr [rcx+1Ch], 10h
0x180067e28  jz      loc_180067F41
0x180067e2e  cmp     byte ptr [rcx+19h], 2
0x180067e32  jb      loc_180067F41
0x180067e38  mov     edx, 2Ah ; '*'
0x180067e3d  jmp     loc_180067F28
0x180067e42  mov     r9d, 4; dwBufferLength
0x180067e48  lea     r8, [rsp+130h+var_D0]; lpBuffer
0x180067e4d  mov     rcx, rbx; hInternet
0x180067e50  lea     edx, [r9+65h]; dwOption
0x180067e54  call    cs:__imp_WinHttpSetOption
0x180067e5a  test    eax, eax
0x180067e5c  jnz     short loc_180067E99
0x180067e5e  call    cs:__imp_GetLastError
0x180067e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e6b  lea     rdx, WPP_GLOBAL_Control
0x180067e72  cmp     rcx, rdx
0x180067e75  jz      loc_180067F41
0x180067e7b  test    byte ptr [rcx+1Ch], 10h
0x180067e7f  jz      loc_180067F41
0x180067e85  cmp     byte ptr [rcx+19h], 2
0x180067e89  jb      loc_180067F41
0x180067e8f  mov     edx, 2Bh ; '+'
0x180067e94  jmp     loc_180067F28
0x180067e99  lea     rdx, [rsp+130h+var_C4]
0x180067e9e  call    ?GetCorpLocationTcpRtoParameters@NcsiConfigData@@QEAA?AU_TCP_INITIAL_RTO_PARAMETERS@@XZ; NcsiConfigData::GetCorpLocationTcpRtoParameters(void)
0x180067ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180067eaa  lea     rax, WPP_GLOBAL_Control
0x180067eb1  cmp     rcx, rax
0x180067eb4  jz      short loc_180067EE2
0x180067eb6  test    byte ptr [rcx+1Ch], 10h
0x180067eba  jz      short loc_180067EE2
0x180067ebc  cmp     byte ptr [rcx+19h], 5
0x180067ec0  jb      short loc_180067EE2
0x180067ec2  movzx   eax, [rsp+130h+var_C2]
0x180067ec7  movzx   edx, [rsp+130h+var_C4]
0x180067ecc  mov     r9d, [rsp+130h+var_D0]
0x180067ed1  mov     rcx, [rcx+10h]
0x180067ed5  mov     dword ptr [rsp+130h+ppwszAcceptTypes], eax
0x180067ed9  mov     [rsp+130h+dwFlags], edx
0x180067edd  call    WPP_SF_DDD
0x180067ee2  mov     r9d, 4; dwBufferLength
0x180067ee8  lea     r8, [rsp+130h+var_C4]; lpBuffer
0x180067eed  mov     rcx, rbx; hInternet
0x180067ef0  lea     edx, [r9+6Dh]; dwOption
0x180067ef4  call    cs:__imp_WinHttpSetOption
0x180067efa  test    eax, eax
0x180067efc  jnz     short loc_180067F50
0x180067efe  call    cs:__imp_GetLastError
0x180067f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f0b  lea     rdx, WPP_GLOBAL_Control
0x180067f12  cmp     rcx, rdx
0x180067f15  jz      short loc_180067F41
0x180067f17  test    byte ptr [rcx+1Ch], 10h
0x180067f1b  jz      short loc_180067F41
0x180067f1d  cmp     byte ptr [rcx+19h], 2
0x180067f21  jb      short loc_180067F41
0x180067f23  mov     edx, 2Dh ; '-'
0x180067f28  mov     r9d, [rsp+130h+var_D0]
0x180067f2d  lea     r8, WPP_c67a6644af093602b51c782a1df615fe_Traceguids
0x180067f34  mov     rcx, [rcx+10h]
0x180067f38  mov     [rsp+130h+dwFlags], eax
0x180067f3c  call    WPP_SF_dd
0x180067f41  lea     rcx, [rsp+130h+var_E8]
0x180067f46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@Win32APIWrappers@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180067f4b  jmp     loc_180067D26
0x180067f50  movzx   r8d, [rsp+130h+var_F0]; nServerPort
0x180067f56  xor     r9d, r9d; dwReserved
0x180067f59  mov     rdx, [r12]; pswzServerName
0x180067f5d  mov     rcx, rbx; hSession
0x180067f60  call    cs:__imp_WinHttpConnect
0x180067f66  xor     r12d, r12d
0x180067f69  mov     [rsp+130h+var_E0], rax
0x180067f6e  test    rax, rax
0x180067f71  jnz     short loc_180067FC5
0x180067f73  call    cs:__imp_GetLastError
0x180067f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f80  lea     rdx, WPP_GLOBAL_Control
0x180067f87  cmp     rcx, rdx
0x180067f8a  jz      short loc_180067FB6
0x180067f8c  test    byte ptr [rcx+1Ch], 10h
0x180067f90  jz      short loc_180067FB6
0x180067f92  cmp     byte ptr [rcx+19h], 2
0x180067f96  jb      short loc_180067FB6
0x180067f98  mov     r9d, [rsp+130h+var_D0]
0x180067f9d  lea     edx, [r12+2Eh]
0x180067fa2  mov     rcx, [rcx+10h]
0x180067fa6  lea     r8, WPP_c67a6644af093602b51c782a1df615fe_Traceguids
0x180067fad  mov     [rsp+130h+dwFlags], eax
0x180067fb1  call    WPP_SF_dd
0x180067fb6  lea     rcx, [rsp+130h+var_E0]
0x180067fbb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@Win32APIWrappers@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180067fc0  jmp     loc_180067F41
0x180067fc5  mov     r8, [r13+0]; pwszObjectName
0x180067fc9  lea     rdx, pwszVerb; "GET"
0x180067fd0  mov     [rsp+130h+var_100], 800000h; dwFlags
0x180067fd8  xor     r9d, r9d; pwszVersion
0x180067fdb  mov     [rsp+130h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x180067fe0  mov     rcx, rax; hConnect
0x180067fe3  mov     qword ptr [rsp+130h+dwFlags], r12; pwszReferrer
0x180067fe8  call    cs:__imp_WinHttpOpenRequest
0x180067fee  mov     [rsp+130h+var_D8], rax
0x180067ff3  mov     rbx, rax
0x180067ff6  test    rax, rax
0x180067ff9  jnz     loc_18006808D
0x180067fff  call    cs:__imp_GetLastError
0x180068005  mov     rcx, cs:WPP_GLOBAL_Control
0x18006800c  lea     rdx, WPP_GLOBAL_Control
0x180068013  cmp     rcx, rdx
0x180068016  jz      short loc_180068040
0x180068018  test    byte ptr [rcx+1Ch], 10h
0x18006801c  jz      short loc_180068040
0x18006801e  cmp     byte ptr [rcx+19h], 2
0x180068022  jb      short loc_180068040
0x180068024  lea     edx, [rbx+2Fh]
0x180068027  mov     r9d, [rsp+130h+var_D0]
0x18006802c  lea     r8, WPP_c67a6644af093602b51c782a1df615fe_Traceguids
0x180068033  mov     rcx, [rcx+10h]
0x180068037  mov     [rsp+130h+dwFlags], eax
0x18006803b  call    WPP_SF_dd
0x180068040  mov     dil, r12b
0x180068043  lea     rcx, [rsp+130h+var_D8]
0x180068048  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@Win32APIWrappers@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006804d  lea     rcx, [rsp+130h+var_E0]
0x180068052  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@Win32APIWrappers@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180068057  lea     rcx, [rsp+130h+var_E8]
0x18006805c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@Win32APIWrappers@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&Win32APIWrappers::WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180068061  lea     rcx, [rbp+3Fh+var_90]; this
0x180068065  call    ??1AutoPdcNetworkRef@Power@Ncsi@@QEAA@XZ; Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef(void)
0x18006806a  mov     al, dil
0x18006806d  mov     rcx, [rbp+3Fh+var_50]
0x180068071  xor     rcx, rsp; StackCookie
0x180068074  call    __security_check_cookie
0x180068079  add     rsp, 0F8h
0x180068080  pop     r15
0x180068082  pop     r14
0x180068084  pop     r13
0x180068086  pop     r12
0x180068088  pop     rdi
0x180068089  pop     rsi
0x18006808a  pop     rbx
0x18006808b  pop     rbp
0x18006808c  retn
0x18006808d  mov     r13d, 4
0x180068093  mov     [rsp+130h+var_C0], 8
0x18006809b  mov     r9d, r13d; dwBufferLength
0x18006809e  lea     r8, [rsp+130h+var_C0]; lpBuffer
0x1800680a3  mov     rcx, rbx; hInternet
0x1800680a6  lea     edx, [r13+3Bh]; dwOption
0x1800680aa  call    cs:__imp_WinHttpSetOption
0x1800680b0  test    eax, eax
0x1800680b2  jz      short loc_180068040
0x1800680b4  mov     eax, cs:dword_18009B3CC
0x1800680ba  xor     edx, edx; nResolveTimeout
0x1800680bc  imul    r8d, eax, 3E8h; nConnectTimeout
0x1800680c3  nop
0x1800680c4  mov     rcx, rbx; hInternet
0x1800680c7  mov     r9d, r8d; nSendTimeout
0x1800680ca  mov     [rsp+130h+var_C8], r8d
0x1800680cf  mov     [rsp+130h+dwFlags], r8d; nReceiveTimeout
0x1800680d4  call    cs:__imp_WinHttpSetTimeouts
0x1800680da  test    eax, eax
0x1800680dc  jz      loc_180068040
0x1800680e2  mov     r9d, r13d; dwBufferLength
0x1800680e5  lea     r8, [rsp+130h+var_C8]; lpBuffer
0x1800680ea  lea     edx, [r13-1]; dwOption
0x1800680ee  mov     rcx, rbx; hInternet
0x1800680f1  call    cs:__imp_WinHttpSetOption
0x1800680f7  test    eax, eax
0x1800680f9  jz      loc_180068040
0x1800680ff  mov     r9d, r13d; dwBufferLength
0x180068102  lea     r8, [rsp+130h+var_C8]; lpBuffer
  ... truncated ...
```
