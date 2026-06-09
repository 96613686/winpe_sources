# NtlmLogging::SspLogNTLMClientResponse(_AUTHENTICATE_MESSAGE const *,ulong,int,_SSP_CONTEXT const *,_UNICODE_STRING const *,utl::optional<utl::vector<utl::pair<NtlmHelper::Blocking::Decision,NtlmHelper::Blocking::Reason>,utl::allocator<utl::pair<NtlmHelper::Blocking::Decision,NtlmHelper::Blocking::Reason>>>> const &)

- ea: `0x1800587c8`
- end: `0x180059757`
- name: `?SspLogNTLMClientResponse@NtlmLogging@@YAXPEBU_AUTHENTICATE_MESSAGE@@KHPEBU_SSP_CONTEXT@@PEBU_UNICODE_STRING@@AEBV?$optional@V?$vector@U?$pair@W4Decision@Blocking@NtlmHelper@@UReason@23@@utl@@V?$allocator@U?$pair@W4Decision@Blocking@NtlmHelper@@UReason@23@@utl@@@2@@utl@@@utl@@@Z`
- size: `3983`
- prototype: `__int64 __usercall@<rax>(struct _AUTHENTICATE_MESSAGE *@<rcx>, unsigned int@<edx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800268dc`

## callees

- `0x18000cba0`
- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x180021acc`
- `0x18002e3e8`
- `0x18002e7a8`
- `0x18002f03c`
- `0x18002fb50`
- `0x1800486ac`
- `0x18004c874`
- `0x180057bb8`
- `0x180057c9c`
- `0x180057ccc`
- `0x180057d1c`
- `0x180057d80`
- `0x180057de8`
- `0x180057e48`
- `0x180057ecc`
- `0x180057f4c`
- `0x180057f84`
- `0x180058068`
- `0x1800587c8`
- `0x18005a010`
- `0x18005a2f0`
- `0x18005a318`
- `0x1800692ac`
- `0x1800693f8`
- `0x1800696dc`
- `0x1800698e0`
- `0x180069de4`
- `0x18006d010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180058837`
- `ntdll!EtwEventEnabled` at `0x18005884f`
- `ntdll!EtwEventEnabled` at `0x1800596af`
- `ntdll!EtwEventEnabled` at `0x1800596d4`
- `ntdll!EtwEventEnabled` at `0x180058837`
- `ntdll!EtwEventEnabled` at `0x18005884f`
- `ntdll!EtwEventEnabled` at `0x1800596af`
- `ntdll!EtwEventEnabled` at `0x1800596d4`
- `ntdll!EtwEventWrite` at `0x180059632`
- `ntdll!EtwEventWrite` at `0x1800596fd`
- `ntdll!EtwEventWrite` at `0x180059632`
- `ntdll!EtwEventWrite` at `0x1800596fd`
- `LSASRV!LsaIFreeHeap` at `0x180058b31`
- `LSASRV!LsaIFreeHeap` at `0x180058b3c`
- `LSASRV!LsaIFreeHeap` at `0x180058bf8`
- `LSASRV!LsaIFreeHeap` at `0x180058c03`
- `LSASRV!LsaIFreeHeap` at `0x180058c56`
- `LSASRV!LsaIFreeHeap` at `0x180058c61`
- `LSASRV!LsaIFreeHeap` at `0x180058ce1`
- `LSASRV!LsaIFreeHeap` at `0x180058cec`
- `LSASRV!LsaIFreeHeap` at `0x180058d36`
- `LSASRV!LsaIFreeHeap` at `0x180058d41`
- `LSASRV!LsaIFreeHeap` at `0x180058d82`
- `LSASRV!LsaIFreeHeap` at `0x180058d8d`
- `LSASRV!LsaIFreeHeap` at `0x180058dce`
- `LSASRV!LsaIFreeHeap` at `0x180058dd9`
- `LSASRV!LsaIFreeHeap` at `0x180058e21`
- `LSASRV!LsaIFreeHeap` at `0x180058e2c`
- `LSASRV!LsaIFreeHeap` at `0x180058e8c`
- `LSASRV!LsaIFreeHeap` at `0x180058e97`
- `LSASRV!LsaIFreeHeap` at `0x180058f19`
- `LSASRV!LsaIFreeHeap` at `0x180058f24`
- `LSASRV!LsaIFreeHeap` at `0x180058f93`
- `LSASRV!LsaIFreeHeap` at `0x180058f9e`
- `LSASRV!LsaIFreeHeap` at `0x180058ff5`
- `LSASRV!LsaIFreeHeap` at `0x180059000`
- `LSASRV!LsaIFreeHeap` at `0x180059080`
- `LSASRV!LsaIFreeHeap` at `0x18005908b`
- `LSASRV!LsaIFreeHeap` at `0x180059114`
- `LSASRV!LsaIFreeHeap` at `0x18005911f`
- `LSASRV!LsaIFreeHeap` at `0x18005917c`
- `LSASRV!LsaIFreeHeap` at `0x180059187`
- `LSASRV!LsaIFreeHeap` at `0x1800591e5`
- `LSASRV!LsaIFreeHeap` at `0x1800591f0`
- `LSASRV!LsaIFreeHeap` at `0x180059266`
- `LSASRV!LsaIFreeHeap` at `0x180059271`
- `LSASRV!LsaIFreeHeap` at `0x1800592ce`
- `LSASRV!LsaIFreeHeap` at `0x1800592d9`
- `LSASRV!LsaIFreeHeap` at `0x180059334`
- `LSASRV!LsaIFreeHeap` at `0x18005933f`
- `LSASRV!LsaIFreeHeap` at `0x180059398`
- `LSASRV!LsaIFreeHeap` at `0x1800593a3`
- `LSASRV!LsaIFreeHeap` at `0x18005956d`
- `LSASRV!LsaIFreeHeap` at `0x180059578`
- `LSASRV!LsaIFreeHeap` at `0x1800595e4`
- `LSASRV!LsaIFreeHeap` at `0x1800595ef`
- `LSASRV!LsaIFreeHeap` at `0x18005966e`
- `LSASRV!LsaIFreeHeap` at `0x180059679`
- `LSASRV!LsaIFreeHeap` at `0x180059727`
- `LSASRV!LsaIFreeHeap` at `0x180059732`
- `LSASRV!LsaIFreeHeap` at `0x180058b31`
- `LSASRV!LsaIFreeHeap` at `0x180058b3c`
- `LSASRV!LsaIFreeHeap` at `0x180058bf8`
- `LSASRV!LsaIFreeHeap` at `0x180058c03`
- `LSASRV!LsaIFreeHeap` at `0x180058c56`
- `LSASRV!LsaIFreeHeap` at `0x180058c61`
- `LSASRV!LsaIFreeHeap` at `0x180058ce1`
- `LSASRV!LsaIFreeHeap` at `0x180058cec`
- `LSASRV!LsaIFreeHeap` at `0x180058d36`
- `LSASRV!LsaIFreeHeap` at `0x180058d41`
- `LSASRV!LsaIFreeHeap` at `0x180058d82`
- `LSASRV!LsaIFreeHeap` at `0x180058d8d`
- `LSASRV!LsaIFreeHeap` at `0x180058dce`
- `LSASRV!LsaIFreeHeap` at `0x180058dd9`
- `LSASRV!LsaIFreeHeap` at `0x180058e21`
- `LSASRV!LsaIFreeHeap` at `0x180058e2c`
- `LSASRV!LsaIFreeHeap` at `0x180058e8c`
- `LSASRV!LsaIFreeHeap` at `0x180058e97`
- `LSASRV!LsaIFreeHeap` at `0x180058f19`
- `LSASRV!LsaIFreeHeap` at `0x180058f24`
- `LSASRV!LsaIFreeHeap` at `0x180058f93`
- `LSASRV!LsaIFreeHeap` at `0x180058f9e`
- `LSASRV!LsaIFreeHeap` at `0x180058ff5`
- `LSASRV!LsaIFreeHeap` at `0x180059000`
- `LSASRV!LsaIFreeHeap` at `0x180059080`
- `LSASRV!LsaIFreeHeap` at `0x18005908b`
- `LSASRV!LsaIFreeHeap` at `0x180059114`
- `LSASRV!LsaIFreeHeap` at `0x18005911f`
- `LSASRV!LsaIFreeHeap` at `0x18005917c`
- `LSASRV!LsaIFreeHeap` at `0x180059187`
- `LSASRV!LsaIFreeHeap` at `0x1800591e5`
- `LSASRV!LsaIFreeHeap` at `0x1800591f0`
- `LSASRV!LsaIFreeHeap` at `0x180059266`
- `LSASRV!LsaIFreeHeap` at `0x180059271`
- `LSASRV!LsaIFreeHeap` at `0x1800592ce`
- `LSASRV!LsaIFreeHeap` at `0x1800592d9`
- `LSASRV!LsaIFreeHeap` at `0x180059334`
- `LSASRV!LsaIFreeHeap` at `0x18005933f`
- `LSASRV!LsaIFreeHeap` at `0x180059398`
- `LSASRV!LsaIFreeHeap` at `0x1800593a3`
- `LSASRV!LsaIFreeHeap` at `0x18005956d`
- `LSASRV!LsaIFreeHeap` at `0x180059578`
- `LSASRV!LsaIFreeHeap` at `0x1800595e4`
- `LSASRV!LsaIFreeHeap` at `0x1800595ef`
- `LSASRV!LsaIFreeHeap` at `0x18005966e`
- `LSASRV!LsaIFreeHeap` at `0x180059679`
- `LSASRV!LsaIFreeHeap` at `0x180059727`
- `LSASRV!LsaIFreeHeap` at `0x180059732`
- `LSASRV!LsaIGetNetworkInfo` at `0x180058c8f`
- `LSASRV!LsaIGetNetworkInfo` at `0x180058c8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall NtlmLogging::SspLogNTLMClientResponse(
        struct _AUTHENTICATE_MESSAGE *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6)
{
  __int64 v9; // r8
  __int64 v10; // rbx
  int v11; // ebx
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  __int64 SessionKeyStatus; // rax
  __int64 v15; // rbx
  __int64 v16; // rdi
  _QWORD *v17; // rax
  __int64 *v18; // rdx
  __int64 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING v23; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v24; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v25; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v26; // [rsp+70h] [rbp-90h]
  _WORD v27[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v28[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v29[8]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v30[2]; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v31[8]; // [rsp+B8h] [rbp-48h] BYREF
  void *v32; // [rsp+C8h] [rbp-38h] BYREF
  char *v33; // [rsp+D0h] [rbp-30h]
  _WORD v34[8]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v35[2]; // [rsp+E8h] [rbp-18h] BYREF
  _WORD v36[8]; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING **v37; // [rsp+108h] [rbp+8h] BYREF
  struct _UNICODE_STRING *v38; // [rsp+110h] [rbp+10h]
  struct _UNICODE_STRING *v39; // [rsp+118h] [rbp+18h] BYREF
  char v40; // [rsp+120h] [rbp+20h]
  int v41; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v42; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v43[40]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v44[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v45[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v46[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v47[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v48[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v49[32]; // [rsp+200h] [rbp+100h] BYREF
  unsigned int v50; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v51[120]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v52[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v53[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned int v54[6]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _WORD v55[788]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v56[8]; // [rsp+908h] [rbp+808h] BYREF

  if ( NtlmDoEnhancedAuditing
    && (int)SspInitEtwLogHandle() >= 0
    && ((unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedClientLogsInfo)
     || (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedClientLogsWarning))
    && a4
    && (*(_DWORD *)(a4 + 48) & 0x4000) == 0 )
  {
    NtlmHelper::AuthenticateMessage::AuthenticateMessage((NtlmHelper::AuthenticateMessage *)v47, a1, a2);
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v53, LsaFunctions);
    SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v53, &v20);
    NtlmLogging::EventDataHelper::EventDataHelper((NtlmLogging::EventDataHelper *)&v21, 0x17u);
    v25 = v27;
    v26 = v27;
    v27[0] = 0;
    v9 = -1;
    do
      ++v9;
    while ( v55[v9] );
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      &v25,
      v55,
      v9);
    if ( v25 == v26 && v54[0] == 4 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        &v25,
        L"SYSTEM",
        6);
    }
    else
    {
      v10 = v20;
      if ( v20 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v25,
          L" (",
          2);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v25,
          v10);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v25,
          L")",
          1);
      }
    }
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, &v25)
      || !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)&v21, v54) )
    {
      goto LABEL_32;
    }
    v28[0] = v29;
    v28[1] = v29;
    v29[0] = 0;
    if ( v47[0] == v47[1] && v48[0] == v48[1] )
    {
      if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"ANONYMOUS LOGON", 0x20u)
        || !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"ANONYMOUS LOGON", 0x20u) )
      {
        goto LABEL_31;
      }
      v11 = 1;
    }
    else
    {
      if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v47)
        || !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v48) )
      {
        goto LABEL_31;
      }
      v11 = 0;
    }
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v49) )
      goto LABEL_31;
    v12 = L"Single Sign-On";
    if ( !*(_BYTE *)(a4 + 384) )
      v12 = L"Supplied Credentials";
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      v28,
      v12,
      (-(__int64)(*(_BYTE *)(a4 + 384) != 0) & 0xFFFFFFFFFFFFFFFAuLL) + 20);
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v28) )
      goto LABEL_31;
    v19 = 0;
    v30[0] = v31;
    v30[1] = v31;
    v31[0] = 0;
    v23 = 0;
    v24 = 0;
    v37 = (struct _UNICODE_STRING **)&v19;
    v38 = &v23;
    v39 = &v24;
    v40 = 1;
    NtlmHelper::AvPairHelper::GetTargetInfo(v51, v44);
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v44) )
      goto LABEL_29;
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v45) )
      goto LABEL_29;
    NtLmDuplicateUnicodeString(&v24, a5);
    if ( !NtlmLogging::EventDataHelper::AddUnicodeString((NtlmLogging::EventDataHelper *)&v21, &v24) )
      goto LABEL_29;
    if ( (int)LsaIGetNetworkInfo(&v19, &v23) < 0 )
    {
      if ( !NtlmLogging::EventDataHelper::AddNullString((NtlmLogging::EventDataHelper *)&v21)
        || !NtlmLogging::EventDataHelper::AddNullString((NtlmLogging::EventDataHelper *)&v21) )
      {
        goto LABEL_29;
      }
    }
    else
    {
      v13 = NtlmLogging::IpToString(&v32, v19);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v30,
        v13);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v32);
      if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v30)
        || !NtlmLogging::EventDataHelper::AddUnicodeString((NtlmLogging::EventDataHelper *)&v21, &v23) )
      {
        goto LABEL_29;
      }
    }
    if ( !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)&v21, (const unsigned int *)(a4 + 380))
      || (NtlmLogging::FailureReasonToString(&v32, *(unsigned int *)(a4 + 380)),
          !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, v32, 2LL * (_QWORD)v33 + 2)) )
    {
LABEL_29:
      NtlmHelper::AuthenticateHeader::~AuthenticateHeader((NtlmHelper::AuthenticateHeader *)v44);
      LsaIFreeHeap(v19);
      LsaIFreeHeap(v23.Buffer);
      ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(v24.Buffer);
LABEL_30:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v30);
LABEL_31:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v28);
LABEL_32:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v25);
      utl::vector<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>,utl::allocator<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>>>::_Uninit(&v21);
      wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v20);
      wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v56);
      NtlmHelper::AuthenticateMessage::~AuthenticateMessage((NtlmHelper::AuthenticateMessage *)v47);
      return;
    }
    v35[0] = v36;
    v35[1] = v36;
    v36[0] = 0;
    NtlmHelper::AvPairHelper::GetFlags(v51, &v42);
    if ( NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)&v21, &v50) )
    {
      if ( v51[104] )
      {
        if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"NTLMv2", 0xEu) )
          goto LABEL_96;
      }
      else
      {
        if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"NTLMv1", 0xEu) )
          goto LABEL_96;
        v11 = 1;
      }
      SessionKeyStatus = NtlmHelper::AuthenticateMessage::GetSessionKeyStatus(v47, &v32);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v35,
        SessionKeyStatus);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v32);
      if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v35) )
        goto LABEL_96;
      v41 = 10;
      if ( (_BYTE *)utl::_Tree<enum MSV1_0_AVID,utl::pair<enum MSV1_0_AVID const,utl::vector<unsigned char,utl::allocator<unsigned char>>>,utl::less<enum MSV1_0_AVID>,utl::allocator<utl::pair<enum MSV1_0_AVID const,utl::vector<unsigned char,utl::allocator<unsigned char>>>>,0>::_FindImpl<enum MSV1_0_AVID>(
                      v51,
                      &v41) == v51 )
      {
        if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"Not Supported", 0x1Cu) )
          goto LABEL_96;
        v11 = 1;
      }
      else if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"Supported", 0x14u) )
      {
        goto LABEL_96;
      }
      if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v46) )
        goto LABEL_96;
      if ( NtlmHelper::AvPairHelper::SupportsMic((NtlmHelper::AvPairHelper *)v51) )
      {
        if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"Protected", 0x14u) )
          goto LABEL_96;
      }
      else
      {
        if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)&v21, L"Unprotected", 0x18u) )
          goto LABEL_96;
        v11 = 1;
      }
      if ( !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)&v21, &v42)
        || !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, v43) )
      {
        goto LABEL_96;
      }
      if ( (v42 & 4) != 0 )
        v11 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_NtlmBlockingPolicy>::GetImpl'::`2'::impl)
        && *((_BYTE *)a6 + 24) )
      {
        v37 = &v39;
        v38 = (struct _UNICODE_STRING *)&v39;
        LOWORD(v39) = 0;
        v32 = v34;
        v33 = (char *)v34;
        v34[0] = 0;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v32,
          L"\n\t\t",
          3);
        if ( !*((_BYTE *)a6 + 24) )
          __int2c();
        v15 = *a6;
        v16 = a6[1];
        while ( v15 != v16 )
        {
          if ( *(_DWORD *)v15 == 1 )
          {
            v17 = (_QWORD *)NtlmLogging::ULongToWString(v52, *(unsigned int *)(v15 + 8));
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              &v37,
              *v17,
              (__int64)(v17[1] - *v17) >> 1);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v52);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              &v37,
              L", ",
              2);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              &v32,
              *(_QWORD *)(v15 + 16),
              *(_QWORD *)(v15 + 24));
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              &v32,
              L"\n\t\t",
              3);
          }
          v15 += 32;
        }
        if ( (unsigned __int64)(((char *)v38 - (char *)v37) >> 1) >= 2 )
        {
          v38 = (struct _UNICODE_STRING *)((char *)v38 - 2);
          v38->Length = 0;
          v38 = (struct _UNICODE_STRING *)((char *)v38 - 2);
          v38->Length = 0;
        }
        if ( (unsigned __int64)((v33 - (_BYTE *)v32) >> 1) >= 3 )
        {
          v33 -= 2;
          *(_WORD *)v33 = 0;
          v33 -= 2;
          *(_WORD *)v33 = 0;
          v33 -= 2;
          *(_WORD *)v33 = 0;
        }
        if ( (unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, &v37)
          && (unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(&v21, &v32) )
        {
          EtwEventWrite(MsvEtwLogHandle, NTLMLessBlockingPolicyAudit, (v22 - v21) >> 4);
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v32);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v37);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v35);
        NtlmHelper::AuthenticateHeader::~AuthenticateHeader((NtlmHelper::AuthenticateHeader *)v44);
        LsaIFreeHeap(v19);
        LsaIFreeHeap(v23.Buffer);
        ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(v24.Buffer);
        goto LABEL_30;
      }
      if ( v11 )
      {
        if ( (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedClientLogsWarning) )
        {
          v18 = NTLMLessEnhancedClientLogsWarning;
          goto LABEL_95;
        }
      }
      else if ( (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedClientLogsInfo) )
      {
        v18 = NTLMLessEnhancedClientLogsInfo;
LABEL_95:
        EtwEventWrite(MsvEtwLogHandle, v18, (v22 - v21) >> 4);
      }
    }
LABEL_96:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v35);
    NtlmHelper::AuthenticateHeader::~AuthenticateHeader((NtlmHelper::AuthenticateHeader *)v44);
    LsaIFreeHeap(v19);
    LsaIFreeHeap(v23.Buffer);
    ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(v24.Buffer);
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x1800587c8  mov     [rsp-8+arg_8], rbx
0x1800587cd  mov     [rsp-8+arg_10], rsi
0x1800587d2  push    rbp
0x1800587d3  push    rdi
0x1800587d4  push    r12
0x1800587d6  push    r14
0x1800587d8  push    r15
0x1800587da  lea     rbp, [rsp-820h]
0x1800587e2  sub     rsp, 920h
0x1800587e9  mov     rax, cs:__security_cookie
0x1800587f0  xor     rax, rsp
0x1800587f3  mov     [rbp+840h+var_30], rax
0x1800587fa  mov     rdi, r9
0x1800587fd  mov     ebx, r8d
0x180058800  mov     esi, edx
0x180058802  mov     r14, rcx
0x180058805  mov     r15, [rbp+840h+arg_20]
0x18005880c  xor     r12d, r12d
0x18005880f  cmp     cs:NtlmDoEnhancedAuditing, r12b
0x180058816  jz      loc_180058BA9
0x18005881c  call    SspInitEtwLogHandle
0x180058821  test    eax, eax
0x180058823  js      loc_180058BA9
0x180058829  lea     rdx, NTLMLessEnhancedClientLogsInfo
0x180058830  mov     rcx, cs:MsvEtwLogHandle
0x180058837  call    cs:__imp_EtwEventEnabled
0x18005883d  test    al, al
0x18005883f  jnz     short loc_18005885D
0x180058841  lea     rdx, NTLMLessEnhancedClientLogsWarning
0x180058848  mov     rcx, cs:MsvEtwLogHandle
0x18005884f  call    cs:__imp_EtwEventEnabled
0x180058855  test    al, al
0x180058857  jz      loc_180058BA9
0x18005885d  test    rdi, rdi
0x180058860  jz      loc_180058BA9
0x180058866  test    dword ptr [rdi+30h], 4000h
0x18005886d  jnz     loc_180058BA9
0x180058873  test    ebx, ebx
0x180058875  setnz   r9b; bool
0x180058879  mov     r8d, esi; unsigned int
0x18005887c  mov     rdx, r14; struct _AUTHENTICATE_MESSAGE *
0x18005887f  lea     rcx, [rbp+840h+var_780]; this
0x180058886  call    ??0AuthenticateMessage@NtlmHelper@@QEAA@PEBU_AUTHENTICATE_MESSAGE@@K_N@Z; NtlmHelper::AuthenticateMessage::AuthenticateMessage(_AUTHENTICATE_MESSAGE const *,ulong,bool)
0x18005888b  nop
0x18005888c  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x180058893  lea     rcx, [rbp+840h+var_680]; this
0x18005889a  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x18005889f  nop
0x1800588a0  lea     rdx, [rsp+940h+var_918]
0x1800588a5  lea     rcx, [rbp+840h+var_680]
0x1800588ac  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x1800588b1  nop
0x1800588b2  mov     edx, 17h; unsigned int
0x1800588b7  lea     rcx, [rsp+940h+var_910]; this
0x1800588bc  call    ??0EventDataHelper@NtlmLogging@@QEAA@I@Z; NtlmLogging::EventDataHelper::EventDataHelper(uint)
0x1800588c1  nop
0x1800588c2  lea     rax, [rsp+940h+var_8C8]
0x1800588c7  mov     [rsp+940h+var_8D8], rax
0x1800588cc  lea     rax, [rsp+940h+var_8C8]
0x1800588d1  mov     [rsp+940h+var_8D0], rax
0x1800588d6  mov     [rsp+940h+var_8C8], r12w
0x1800588dc  lea     rax, [rbp+840h+var_660]
0x1800588e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800588e7  inc     r8
0x1800588ea  cmp     [rax+r8*2], r12w
0x1800588ef  jnz     short loc_1800588E7
0x1800588f1  lea     rdx, [rbp+840h+var_660]
0x1800588f8  lea     rcx, [rsp+940h+var_8D8]
0x1800588fd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180058902  mov     esi, 1
0x180058907  lea     r14d, [rsi+1]
0x18005890b  mov     rax, [rsp+940h+var_8D0]
0x180058910  cmp     [rsp+940h+var_8D8], rax
0x180058915  jnz     short loc_180058937
0x180058917  cmp     [rbp+840h+var_678], 4
0x18005891e  jnz     short loc_180058937
0x180058920  lea     r8d, [rsi+5]
0x180058924  lea     rdx, aSystem; "SYSTEM"
0x18005892b  lea     rcx, [rsp+940h+var_8D8]
0x180058930  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180058935  jmp     short loc_180058976
0x180058937  mov     rbx, [rsp+940h+var_918]
0x18005893c  test    rbx, rbx
0x18005893f  jz      short loc_180058976
0x180058941  mov     r8, r14
0x180058944  lea     rdx, asc_18007659C; " ("
0x18005894b  lea     rcx, [rsp+940h+var_8D8]
0x180058950  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180058955  mov     rdx, rbx
0x180058958  lea     rcx, [rsp+940h+var_8D8]
0x18005895d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180058962  mov     r8, rsi
0x180058965  lea     rdx, asc_180076728; ")"
0x18005896c  lea     rcx, [rsp+940h+var_8D8]
0x180058971  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180058976  lea     rdx, [rsp+940h+var_8D8]
0x18005897b  lea     rcx, [rsp+940h+var_910]
0x180058980  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058985  test    al, al
0x180058987  jz      loc_180058B6F
0x18005898d  lea     rdx, [rbp+840h+var_678]; unsigned int *
0x180058994  lea     rcx, [rsp+940h+var_910]; this
0x180058999  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x18005899e  test    al, al
0x1800589a0  jz      loc_180058B6F
0x1800589a6  lea     rax, [rbp+840h+var_8A8]
0x1800589aa  mov     [rbp+840h+var_8B8], rax
0x1800589ae  lea     rax, [rbp+840h+var_8A8]
0x1800589b2  mov     [rbp+840h+var_8B0], rax
0x1800589b6  mov     [rbp+840h+var_8A8], r12w
0x1800589bb  mov     ebx, 20h ; ' '
0x1800589c0  mov     rax, [rbp+840h+var_778]
0x1800589c7  cmp     [rbp+840h+var_780], rax
0x1800589ce  jnz     short loc_180058A1C
0x1800589d0  mov     rax, [rbp+840h+var_758]
0x1800589d7  cmp     [rbp+840h+var_760], rax
0x1800589de  jnz     short loc_180058A1C
0x1800589e0  mov     r8d, ebx; unsigned __int64
0x1800589e3  lea     rdx, aAnonymousLogon; "ANONYMOUS LOGON"
0x1800589ea  lea     rcx, [rsp+940h+var_910]; this
0x1800589ef  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x1800589f4  test    al, al
0x1800589f6  jz      loc_180058B65
0x1800589fc  mov     r8d, ebx; unsigned __int64
0x1800589ff  lea     rdx, aAnonymousLogon; "ANONYMOUS LOGON"
0x180058a06  lea     rcx, [rsp+940h+var_910]; this
0x180058a0b  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x180058a10  test    al, al
0x180058a12  jz      loc_180058B65
0x180058a18  mov     ebx, esi
0x180058a1a  jmp     short loc_180058A51
0x180058a1c  lea     rdx, [rbp+840h+var_780]
0x180058a23  lea     rcx, [rsp+940h+var_910]
0x180058a28  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058a2d  test    al, al
0x180058a2f  jz      loc_180058B65
0x180058a35  lea     rdx, [rbp+840h+var_760]
0x180058a3c  lea     rcx, [rsp+940h+var_910]
0x180058a41  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058a46  test    al, al
0x180058a48  jz      loc_180058B65
0x180058a4e  mov     ebx, r12d
0x180058a51  lea     rdx, [rbp+840h+var_740]
0x180058a58  lea     rcx, [rsp+940h+var_910]
0x180058a5d  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058a62  test    al, al
0x180058a64  jz      loc_180058B65
0x180058a6a  mov     cl, [rdi+180h]
0x180058a70  mov     al, cl
0x180058a72  neg     al
0x180058a74  sbb     r8, r8
0x180058a77  and     r8, 0FFFFFFFFFFFFFFFAh
0x180058a7b  add     r8, 14h
0x180058a7f  lea     rax, aSuppliedCreden; "Supplied Credentials"
0x180058a86  lea     rdx, aSingleSignOn; "Single Sign-On"
0x180058a8d  test    cl, cl
0x180058a8f  cmovz   rdx, rax
0x180058a93  lea     rcx, [rbp+840h+var_8B8]
0x180058a97  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180058a9c  lea     rdx, [rbp+840h+var_8B8]
0x180058aa0  lea     rcx, [rsp+940h+var_910]
0x180058aa5  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058aaa  test    al, al
0x180058aac  jz      loc_180058B65
0x180058ab2  mov     [rsp+940h+var_920], r12
0x180058ab7  lea     rax, [rbp+840h+var_888]
0x180058abb  mov     [rbp+840h+var_898], rax
0x180058abf  lea     rax, [rbp+840h+var_888]
0x180058ac3  mov     [rbp+840h+var_890], rax
0x180058ac7  mov     [rbp+840h+var_888], r12w
0x180058acc  xorps   xmm0, xmm0
0x180058acf  movups  xmmword ptr [rsp+940h+var_8F8.Length], xmm0
0x180058ad4  xorps   xmm1, xmm1
0x180058ad7  movups  xmmword ptr [rsp+940h+var_8E8.Length], xmm1
0x180058adc  lea     rax, [rsp+940h+var_920]
0x180058ae1  mov     [rbp+840h+var_838], rax
0x180058ae5  lea     rax, [rsp+940h+var_8F8]
0x180058aea  mov     [rbp+840h+var_830], rax
0x180058aee  lea     rax, [rsp+940h+var_8E8]
0x180058af3  mov     [rbp+840h+var_828], rax
0x180058af7  mov     [rbp+840h+var_820], sil
0x180058afb  lea     rdx, [rbp+840h+var_7E0]
0x180058aff  lea     rcx, [rbp+840h+var_718]
0x180058b06  call    ?GetTargetInfo@AvPairHelper@NtlmHelper@@QEBA?AUNtlmTargetInfo@2@XZ; NtlmHelper::AvPairHelper::GetTargetInfo(void)
0x180058b0b  nop
0x180058b0c  lea     rdx, [rbp+840h+var_7E0]
0x180058b10  lea     rcx, [rsp+940h+var_910]
0x180058b15  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058b1a  test    al, al
0x180058b1c  jnz     loc_180058BD4
0x180058b22  lea     rcx, [rbp+840h+var_7E0]; this
0x180058b26  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180058b2b  nop
0x180058b2c  mov     rcx, [rsp+940h+var_920]
0x180058b31  call    cs:__imp_LsaIFreeHeap
0x180058b37  mov     rcx, [rsp+940h+var_8F8.Buffer]
0x180058b3c  call    cs:__imp_LsaIFreeHeap
0x180058b42  mov     rax, cs:LsaFunctions
0x180058b49  mov     rcx, [rsp+940h+var_8E8.Buffer]
0x180058b4e  mov     rax, [rax+188h]
0x180058b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b5a  nop
0x180058b5b  lea     rcx, [rbp+840h+var_898]
0x180058b5f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180058b64  nop
0x180058b65  lea     rcx, [rbp+840h+var_8B8]
0x180058b69  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180058b6e  nop
0x180058b6f  lea     rcx, [rsp+940h+var_8D8]
0x180058b74  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180058b79  nop
0x180058b7a  lea     rcx, [rsp+940h+var_910]
0x180058b7f  call    ?_Uninit@?$vector@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@V?$allocator@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string_view<ushort,utl::char_traits<ushort>>,utl::allocator<utl::basic_string_view<ushort,utl::char_traits<ushort>>>>::_Uninit(void)
0x180058b84  nop
0x180058b85  lea     rcx, [rsp+940h+var_918]
0x180058b8a  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180058b8f  nop
0x180058b90  lea     rcx, [rbp+840h+var_38]
0x180058b97  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180058b9c  nop
0x180058b9d  lea     rcx, [rbp+840h+var_780]; this
0x180058ba4  call    ??1AuthenticateMessage@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateMessage::~AuthenticateMessage(void)
0x180058ba9  mov     rcx, [rbp+840h+var_30]
0x180058bb0  xor     rcx, rsp; StackCookie
0x180058bb3  call    __security_check_cookie
0x180058bb8  lea     r11, [rsp+940h+var_20]
0x180058bc0  mov     rbx, [r11+38h]
0x180058bc4  mov     rsi, [r11+40h]
0x180058bc8  mov     rsp, r11
0x180058bcb  pop     r15
0x180058bcd  pop     r14
0x180058bcf  pop     r12
0x180058bd1  pop     rdi
0x180058bd2  pop     rbp
0x180058bd3  retn
0x180058bd4  lea     rdx, [rbp+840h+var_7C0]
0x180058bdb  lea     rcx, [rsp+940h+var_910]
0x180058be0  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058be5  test    al, al
0x180058be7  jnz     short loc_180058C27
0x180058be9  lea     rcx, [rbp+840h+var_7E0]; this
0x180058bed  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180058bf2  nop
0x180058bf3  mov     rcx, [rsp+940h+var_920]
0x180058bf8  call    cs:__imp_LsaIFreeHeap
0x180058bfe  mov     rcx, [rsp+940h+var_8F8.Buffer]
0x180058c03  call    cs:__imp_LsaIFreeHeap
0x180058c09  mov     rax, cs:LsaFunctions
0x180058c10  mov     rcx, [rsp+940h+var_8E8.Buffer]
0x180058c15  mov     rax, [rax+188h]
0x180058c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c21  nop
0x180058c22  jmp     loc_180058B5B
0x180058c27  mov     rdx, r15
0x180058c2a  lea     rcx, [rsp+940h+var_8E8]
0x180058c2f  call    NtLmDuplicateUnicodeString
0x180058c34  lea     rdx, [rsp+940h+var_8E8]; struct _UNICODE_STRING *
0x180058c39  lea     rcx, [rsp+940h+var_910]; this
0x180058c3e  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x180058c43  test    al, al
0x180058c45  jnz     short loc_180058C85
0x180058c47  lea     rcx, [rbp+840h+var_7E0]; this
0x180058c4b  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180058c50  nop
0x180058c51  mov     rcx, [rsp+940h+var_920]
0x180058c56  call    cs:__imp_LsaIFreeHeap
0x180058c5c  mov     rcx, [rsp+940h+var_8F8.Buffer]
0x180058c61  call    cs:__imp_LsaIFreeHeap
0x180058c67  mov     rax, cs:LsaFunctions
0x180058c6e  mov     rcx, [rsp+940h+var_8E8.Buffer]
0x180058c73  mov     rax, [rax+188h]
0x180058c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c7f  nop
0x180058c80  jmp     loc_180058B5B
0x180058c85  lea     rdx, [rsp+940h+var_8F8]
0x180058c8a  lea     rcx, [rsp+940h+var_920]
0x180058c8f  call    cs:__imp_LsaIGetNetworkInfo
0x180058c95  test    eax, eax
0x180058c97  js      loc_180058D65
0x180058c9d  mov     rdx, [rsp+940h+var_920]
0x180058ca2  lea     rcx, [rbp+840h+var_878]
0x180058ca6  call    ?IpToString@NtlmLogging@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAE@Z; NtlmLogging::IpToString(uchar * const)
0x180058cab  mov     rdx, rax
0x180058cae  lea     rcx, [rbp+840h+var_898]
0x180058cb2  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180058cb7  lea     rcx, [rbp+840h+var_878]
0x180058cbb  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180058cc0  lea     rdx, [rbp+840h+var_898]
0x180058cc4  lea     rcx, [rsp+940h+var_910]
0x180058cc9  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058cce  test    al, al
0x180058cd0  jnz     short loc_180058D10
0x180058cd2  lea     rcx, [rbp+840h+var_7E0]; this
0x180058cd6  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180058cdb  nop
0x180058cdc  mov     rcx, [rsp+940h+var_920]
0x180058ce1  call    cs:__imp_LsaIFreeHeap
0x180058ce7  mov     rcx, [rsp+940h+var_8F8.Buffer]
0x180058cec  call    cs:__imp_LsaIFreeHeap
0x180058cf2  mov     rax, cs:LsaFunctions
  ... truncated ...
```
