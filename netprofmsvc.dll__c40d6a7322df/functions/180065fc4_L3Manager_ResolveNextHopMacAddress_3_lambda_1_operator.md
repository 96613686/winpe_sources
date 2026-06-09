# _L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()

- ea: `0x180065fc4`
- end: `0x180066a88`
- name: `_L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()`
- size: `2756`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800901e0`

## callees

- `0x18000494c`
- `0x180009990`
- `0x18000aa14`
- `0x18000b048`
- `0x18000b620`
- `0x18000b6b8`
- `0x18002a2b4`
- `0x18002bd40`
- `0x18002ce40`
- `0x1800307cc`
- `0x180038b94`
- `0x18003e790`
- `0x1800449fc`
- `0x180065fc4`
- `0x180086290`
- `0x180093180`
- `0x180097c74`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba31`
- `0x18010ac38`
- `0x18010acdc`
- `0x18010cc60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800669f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066a1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800669f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066a1f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180066a34`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180066a34`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x1800660db`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x1800664fa`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x1800660db`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x1800664fa`

## string_xrefs

- `0x1800660f2`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`
- `0x180066511`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // ebx
  int v5; // edx
  unsigned __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d
  _QWORD *v9; // r9
  unsigned int i; // edi
  unsigned int v11; // eax
  __int64 v12; // rcx
  void **v13; // rax
  UCHAR *v14; // rax
  _QWORD *v15; // r9
  UCHAR *v16; // rax
  UCHAR *v17; // rax
  UCHAR *v18; // rax
  _QWORD *v19; // r9
  unsigned int j; // edi
  _QWORD *v21; // r9
  unsigned int v22; // eax
  int v23; // edx
  unsigned int v24; // ebx
  int v25; // edx
  __int64 v26; // rcx
  void **v27; // rax
  void **v28; // rax
  _QWORD *v29; // r9
  UCHAR *v30; // rax
  _QWORD *v31; // r9
  UCHAR *v32; // rax
  _QWORD *v33; // r9
  _QWORD *v34; // r9
  UCHAR *v35; // rax
  __int64 v36; // r14
  __int64 v37; // rdi
  char *v38; // rbx
  __int64 v39; // rbx
  __int64 result; // rax
  const char *v41; // r9
  UCHAR **v42; // [rsp+20h] [rbp-1F8h]
  char v43; // [rsp+20h] [rbp-1F8h]
  char v44; // [rsp+28h] [rbp-1F0h]
  __int16 PhysicalAddressLength; // [rsp+30h] [rbp-1E8h]
  UCHAR *v46; // [rsp+38h] [rbp-1E0h]
  NL_NEIGHBOR_STATE State; // [rsp+50h] [rbp-1C8h] BYREF
  int v48; // [rsp+54h] [rbp-1C4h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-1C0h] BYREF
  int v50; // [rsp+60h] [rbp-1B8h] BYREF
  char v51; // [rsp+65h] [rbp-1B3h]
  void **v52; // [rsp+68h] [rbp-1B0h]
  char v53; // [rsp+70h] [rbp-1A8h] BYREF
  char v54[24]; // [rsp+118h] [rbp-100h] BYREF
  _MIB_IPNET_ROW2 Row; // [rsp+130h] [rbp-E8h] BYREF
  _QWORD v56[3]; // [rsp+190h] [rbp-88h] BYREF
  unsigned __int64 v57; // [rsp+1A8h] [rbp-70h]
  void *v58[2]; // [rsp+1B0h] [rbp-68h] BYREF
  __int64 v59; // [rsp+1C0h] [rbp-58h]
  unsigned __int64 v60; // [rsp+1C8h] [rbp-50h]
  UCHAR *PhysicalAddress; // [rsp+1D0h] [rbp-48h] BYREF
  UCHAR *v62; // [rsp+1D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
  {
    v42 = &PhysicalAddress;
    McGenEventWrite_EventWriteTransfer(&NLASVC_EVT_GUID_Context, StartLinkResolver, a3, 1);
  }
  v51 = 1;
  try
  {
    ctl::ctSockaddr::writeAddress();
    memset_0(&Row, 0, sizeof(Row));
    Row.InterfaceLuid.Value = a1[20];
    Row.Address.Ipv4 = (SOCKADDR_IN)*((_OWORD *)a1 + 1);
    *(_OWORD *)(&Row.Address.si_family + 6) = *(_OWORD *)((char *)a1 + 28);
    v4 = 0;
    v50 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent>::GetImpl'::`2'::impl) )
    {
      if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
      {
        v9 = v56;
        if ( v57 > 7 )
          v9 = (_QWORD *)v56[0];
        McTemplateU0jz_EventWriteTransfer(v6, StartIpAddressResolution, a1 + 18, v9);
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= 8 )
          goto LABEL_26;
        if ( !L3Manager::s_singleInstance )
        {
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            LODWORD(lpCriticalSection) = Row.State;
            v18 = (UCHAR *)v56;
            if ( v57 > 7 )
              v18 = (UCHAR *)v56[0];
            PhysicalAddress = v18;
            v48 = 8;
            State = i;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
              v6,
              (unsigned int)&unk_180192BD0,
              v7,
              v8,
              (__int64)&State,
              (__int64)&v48,
              (__int64)&PhysicalAddress,
              (__int64)&lpCriticalSection);
          }
          LOBYTE(v4) = -57;
          v50 = 1223;
          goto LABEL_47;
        }
        v11 = ResolveIpNetEntry2(&Row, 0);
        v4 = v11;
        LODWORD(v6) = (_DWORD)retaddr;
        if ( v11 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x7A6,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
            (const char *)v11,
            (unsigned int)v42);
        v50 = v4;
        if ( v4 )
        {
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            LODWORD(lpCriticalSection) = v4;
            v17 = (UCHAR *)v56;
            if ( v57 > 7 )
              v17 = (UCHAR *)v56[0];
            PhysicalAddress = v17;
            v48 = 8;
            State = i;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
              v6,
              (unsigned int)&unk_180192A98,
              v7,
              v8,
              (__int64)&State,
              (__int64)&v48,
              (__int64)&PhysicalAddress,
              (__int64)&lpCriticalSection);
          }
          if ( v4 == 67 && i )
            goto LABEL_26;
        }
        else
        {
          LODWORD(v6) = Row.State;
          if ( Row.State )
          {
            LODWORD(v6) = Row.State - 1;
            if ( Row.State != NlnsIncomplete )
            {
              LODWORD(v6) = Row.State - 2;
              if ( Row.State != NlnsProbe )
              {
                LODWORD(v6) = Row.State - 3;
                if ( (unsigned int)(Row.State - 3) >= 2 )
                {
                  PhysicalAddress = Row.PhysicalAddress;
                  v62 = &Row.PhysicalAddress[Row.PhysicalAddressLength];
                  HexStringFromBytes<wil::details::pointer_range<unsigned char *>>(v58, &PhysicalAddress);
                  if ( (unsigned int)dword_1801BD288 > 4 )
                  {
                    v13 = v58;
                    if ( v60 > 7 )
                      v13 = (void **)v58[0];
                    v52 = v13;
                    State = Row.State;
                    v14 = (UCHAR *)v56;
                    if ( v57 > 7 )
                      v14 = (UCHAR *)v56[0];
                    PhysicalAddress = v14;
                    v48 = 8;
                    LODWORD(lpCriticalSection) = i;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                      v12,
                      byte_180192C6D);
                  }
                  std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v58);
LABEL_26:
                  if ( !v4 )
                  {
                    if ( (Microsoft_Windows_NlaSvcEnableBits & 8) == 0 )
                      goto LABEL_109;
                    v15 = v56;
                    if ( v57 > 7 )
                      LODWORD(v15) = v56[0];
                    v46 = Row.PhysicalAddress;
                    PhysicalAddressLength = Row.PhysicalAddressLength;
                    v44 = Row.State;
                    v43 = 0;
                    goto LABEL_55;
                  }
LABEL_47:
                  if ( (Microsoft_Windows_NlaSvcEnableBits & 0x10) != 0 )
                  {
                    v19 = v56;
                    if ( v57 > 7 )
                      LODWORD(v19) = v56[0];
                    McTemplateU0jzq_EventWriteTransfer(v6, v5, (_DWORD)a1 + 144, (_DWORD)v19, v4);
                  }
                  if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
                  {
                    v15 = v56;
                    if ( v57 > 7 )
                      LODWORD(v15) = v56[0];
                    v46 = 0;
                    PhysicalAddressLength = 0;
                    v44 = 7;
                    v43 = v4;
LABEL_55:
                    McTemplateU0jzqqhbr4_EventWriteTransfer(
                      v6,
                      v5,
                      (_DWORD)a1 + 144,
                      (_DWORD)v15,
                      v43,
                      v44,
                      PhysicalAddressLength,
                      (__int64)v46);
                    goto LABEL_109;
                  }
                  goto LABEL_109;
                }
              }
            }
          }
          v4 = 1237;
          v50 = 1237;
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            LODWORD(lpCriticalSection) = Row.State;
            v16 = (UCHAR *)v56;
            if ( v57 > 7 )
              v16 = (UCHAR *)v56[0];
            PhysicalAddress = v16;
            v48 = 8;
            State = i;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
              v6,
              (unsigned int)byte_180192CE1,
              v7,
              v8,
              (__int64)&State,
              (__int64)&v48,
              (__int64)&PhysicalAddress,
              (__int64)&lpCriticalSection);
          }
        }
      }
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 8 )
        goto LABEL_109;
      if ( !L3Manager::s_singleInstance )
        break;
      if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
      {
        v21 = v56;
        if ( v57 > 7 )
          v21 = (_QWORD *)v56[0];
        McTemplateU0jz_EventWriteTransfer(v6, StartIpAddressResolution, a1 + 18, v21);
      }
      v22 = ResolveIpNetEntry2(&Row, 0);
      v24 = v22;
      v6 = (unsigned __int64)retaddr;
      if ( v22 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x7F4,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
          (const char *)v22,
          (unsigned int)v42);
      v50 = v24;
      if ( v24 )
      {
        if ( (unsigned int)dword_1801BD288 > 4 )
        {
          LODWORD(lpCriticalSection) = v24;
          v32 = (UCHAR *)v56;
          if ( v57 > 7 )
            v32 = (UCHAR *)v56[0];
          PhysicalAddress = v32;
          v48 = 8;
          State = j;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v6,
            (unsigned int)&byte_180192947,
            v7,
            v8,
            (__int64)&State,
            (__int64)&v48,
            (__int64)&PhysicalAddress,
            (__int64)&lpCriticalSection);
        }
        if ( (Microsoft_Windows_NlaSvcEnableBits & 0x10) != 0 )
        {
          v33 = v56;
          if ( v57 > 7 )
            LODWORD(v33) = v56[0];
          McTemplateU0jzq_EventWriteTransfer(v6, v23, (_DWORD)a1 + 144, (_DWORD)v33, v24);
        }
        if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
        {
          v34 = v56;
          if ( v57 > 7 )
            LODWORD(v34) = v56[0];
          McTemplateU0jzqqhbr4_EventWriteTransfer(v6, v23, (_DWORD)a1 + 144, (_DWORD)v34, v24, 7, 0, 0);
        }
        if ( v24 == 67 && j )
          goto LABEL_109;
      }
      else
      {
        v6 = (unsigned int)Row.State;
        if ( Row.State )
        {
          v6 = (unsigned int)(Row.State - 1);
          if ( Row.State != NlnsIncomplete )
          {
            v6 = (unsigned int)(Row.State - 2);
            if ( Row.State != NlnsProbe )
            {
              v6 = (unsigned int)(Row.State - 3);
              if ( (unsigned int)v6 >= 2 )
              {
                PhysicalAddress = Row.PhysicalAddress;
                v62 = &Row.PhysicalAddress[Row.PhysicalAddressLength];
                HexStringFromBytes<wil::details::pointer_range<unsigned char *>>(v58, &PhysicalAddress);
                if ( (unsigned int)dword_1801BD288 > 4 )
                {
                  v27 = v58;
                  if ( v60 > 7 )
                    v27 = (void **)v58[0];
                  PhysicalAddress = (UCHAR *)v27;
                  LODWORD(lpCriticalSection) = Row.State;
                  v28 = (void **)v56;
                  if ( v57 > 7 )
                    v28 = (void **)v56[0];
                  v52 = v28;
                  v48 = 8;
                  State = j;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                    v26,
                    word_180192AFA);
                }
                if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
                {
                  v29 = v56;
                  if ( v57 > 7 )
                    LODWORD(v29) = v56[0];
                  McTemplateU0jzqqhbr4_EventWriteTransfer(
                    v26,
                    v25,
                    (_DWORD)a1 + 144,
                    (_DWORD)v29,
                    0,
                    Row.State,
                    Row.PhysicalAddressLength,
                    (__int64)Row.PhysicalAddress);
                }
                std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v58);
                goto LABEL_109;
              }
            }
          }
        }
        v50 = 1237;
        if ( (unsigned int)dword_1801BD288 > 4 )
        {
          LODWORD(lpCriticalSection) = Row.State;
          v30 = (UCHAR *)v56;
          if ( v57 > 7 )
            v30 = (UCHAR *)v56[0];
          PhysicalAddress = v30;
          v48 = 8;
          State = j;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v6,
            (unsigned int)&word_180192B6E,
            v7,
            v8,
            (__int64)&State,
            (__int64)&v48,
            (__int64)&PhysicalAddress,
            (__int64)&lpCriticalSection);
        }
        if ( (Microsoft_Windows_NlaSvcEnableBits & 8) != 0 )
        {
          v31 = v56;
          if ( v57 > 7 )
            LODWORD(v31) = v56[0];
          McTemplateU0jzqqhbr4_EventWriteTransfer(v6, v23, (_DWORD)a1 + 144, (_DWORD)v31, 213, Row.State, 0, 0);
        }
      }
    }
    if ( (unsigned int)dword_1801BD288 > 4 )
    {
      LODWORD(lpCriticalSection) = Row.State;
      v35 = (UCHAR *)v56;
      if ( v57 > 7 )
        v35 = (UCHAR *)v56[0];
      PhysicalAddress = v35;
      v48 = 8;
      State = j;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&word_180192A36,
        v7,
        v8,
        (__int64)&State,
        (__int64)&v48,
        (__int64)&PhysicalAddress,
        (__int64)&lpCriticalSection);
    }
    v50 = 1223;
LABEL_109:
    v36 = Row.PhysicalAddressLength;
    v37 = *a1;
    *(_OWORD *)v58 = 0;
    v59 = 0;
    if ( Row.PhysicalAddressLength )
    {
      std::vector<unsigned char>::_Buy_nonzero(v58, Row.PhysicalAddressLength);
      v38 = (char *)v58[0];
      memmove_0(v58[0], Row.PhysicalAddress, (unsigned int)v36);
      v58[1] = &v38[v36];
      PhysicalAddress = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&PhysicalAddress);
    }
    v39 = _L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()_::_3_::_lambda_2_::_lambda_2__0(
            (unsigned int)&v53,
            v37,
            (int)a1 + 160,
            (int)a1 + 168,
            (__int64)(a1 + 1),
            (__int64)&v50,
            (__int64)v58);
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, v37 + 1976);
    if ( *(_BYTE *)(v37 + 2240) )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      if ( *(_DWORD *)(v37 + 1968) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back___L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()_::_3_::_lambda_2___(
          v37 + 2120,
          v39);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back___L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()_::_3_::_lambda_2___(
          v37 + 2200,
          v39);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      _InterlockedIncrement64((volatile signed __int64 *)(v37 + 2104));
      SubmitThreadpoolWork(*(PTP_WORK *)(v37 + 2096));
    }
    std::vector<unsigned char>::_Tidy(v54);
    std::vector<unsigned char>::_Tidy(v58);
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v56);
    result = _L3Manager::ResolveNextHopMacAddress_::_3_::_lambda_1_::operator()_::_3_::_lambda_1_::operator()();
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x864,
             (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
             v41);
  }
  return result;
}

```

## disassembly

```asm
0x180065fc4  mov     r11, rsp
0x180065fc7  push    rbx
0x180065fc8  push    rsi
0x180065fc9  push    rdi
0x180065fca  push    r14
0x180065fcc  sub     rsp, 1F8h
0x180065fd3  mov     rax, cs:__security_cookie
0x180065fda  xor     rax, rsp
0x180065fdd  mov     [rsp+218h+var_38], rax
0x180065fe5  mov     rsi, rcx
0x180065fe8  mov     r14d, 8
0x180065fee  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, r14b
0x180065ff5  jz      short loc_180066017
0x180065ff7  lea     rax, [r11-48h]
0x180065ffb  mov     qword ptr [rsp+218h+var_1F8], rax; unsigned int
0x180066000  lea     r9d, [r14-7]
0x180066004  lea     rdx, StartLinkResolver
0x18006600b  lea     rcx, NLASVC_EVT_GUID_Context
0x180066012  call    McGenEventWrite_EventWriteTransfer
0x180066017  mov     [rsp+218h+var_1B3], 1
0x18006601c  lea     rcx, [rsi+8]
0x180066020  lea     rdx, [rsp+218h+var_88]
0x180066028  call    ?writeAddress@ctSockaddr@ctl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ctl::ctSockaddr::writeAddress(void)
0x18006602d  nop
0x18006602e  xor     edx, edx; Val
0x180066030  lea     r8d, [rdx+58h]; Size
0x180066034  lea     rcx, [rsp+218h+Row]; void *
0x18006603c  call    memset_0
0x180066041  mov     rax, [rsi+0A0h]
0x180066048  mov     qword ptr [rsp+218h+Row.InterfaceLuid], rax
0x180066050  movups  xmm0, xmmword ptr [rsi+10h]
0x180066054  movaps  xmmword ptr [rsp+218h+Row.Address], xmm0
0x18006605c  movups  xmm1, xmmword ptr [rsi+1Ch]
0x180066060  movups  xmmword ptr [rsp+218h+Row.Address+0Ch], xmm1
0x180066068  xor     ebx, ebx
0x18006606a  mov     [rsp+218h+var_1B8], ebx
0x18006606e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent>::GetImpl(void)'::`2'::impl
0x180066075  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_NLANoisyEvent>::__private_IsEnabled(void)
0x18006607a  test    al, al
0x18006607c  jz      loc_1800664A1
0x180066082  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, r14b
0x180066089  jz      short loc_1800660B8
0x18006608b  lea     r9, [rsp+218h+var_88]
0x180066093  cmp     [rsp+218h+var_70], 7
0x18006609c  cmova   r9, [rsp+218h+var_88]
0x1800660a5  lea     r8, [rsi+90h]
0x1800660ac  lea     rdx, StartIpAddressResolution
0x1800660b3  call    McTemplateU0jz_EventWriteTransfer
0x1800660b8  xor     edi, edi
0x1800660ba  cmp     edi, r14d
0x1800660bd  jnb     loc_180066233
0x1800660c3  cmp     cs:?s_singleInstance@L3Manager@@0V?$shared_ptr@VL3Manager@@@std@@A, 0; std::shared_ptr<L3Manager> L3Manager::s_singleInstance
0x1800660cb  jz      loc_18006639D
0x1800660d1  xor     edx, edx; SourceAddress
0x1800660d3  lea     rcx, [rsp+218h+Row]; Row
0x1800660db  call    cs:__imp_ResolveIpNetEntry2
0x1800660e1  mov     ebx, eax
0x1800660e3  mov     rcx, [rsp+218h]; this
0x1800660eb  test    eax, eax
0x1800660ed  jz      short loc_180066103
0x1800660ef  mov     r9d, eax; char *
0x1800660f2  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x1800660f9  mov     edx, 7A6h; void *
0x1800660fe  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180066103  mov     [rsp+218h+var_1B8], ebx
0x180066107  test    ebx, ebx
0x180066109  jnz     loc_180066317
0x18006610f  mov     ecx, [rsp+218h+Row.State]
0x180066116  test    ecx, ecx
0x180066118  jz      loc_180066290
0x18006611e  sub     ecx, 1
0x180066121  jz      loc_180066290
0x180066127  sub     ecx, 1
0x18006612a  jz      loc_180066290
0x180066130  sub     ecx, 1
0x180066133  jz      loc_180066290
0x180066139  cmp     ecx, 1
0x18006613c  jz      loc_180066290
0x180066142  lea     rax, [rsp+218h+Row.PhysicalAddress]
0x18006614a  mov     [rsp+218h+var_48], rax
0x180066152  mov     eax, [rsp+218h+Row.PhysicalAddressLength]
0x180066159  lea     rcx, [rsp+218h+Row.PhysicalAddress]
0x180066161  add     rcx, rax
0x180066164  mov     [rsp+218h+var_40], rcx
0x18006616c  lea     rdx, [rsp+218h+var_48]
0x180066174  lea     rcx, [rsp+218h+var_68]
0x18006617c  call    ??$HexStringFromBytes@V?$pointer_range@PEAE@details@wil@@@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$pointer_range@PEAE@details@wil@@@Z; HexStringFromBytes<wil::details::pointer_range<uchar *>>(wil::details::pointer_range<uchar *> const &)
0x180066181  mov     eax, cs:dword_1801BD288
0x180066187  cmp     eax, 4
0x18006618a  jbe     loc_180066226
0x180066190  lea     rax, [rsp+218h+var_68]
0x180066198  cmp     [rsp+218h+var_50], 7
0x1800661a1  cmova   rax, [rsp+218h+var_68]
0x1800661aa  mov     [rsp+218h+var_1B0], rax
0x1800661af  mov     eax, [rsp+218h+Row.State]
0x1800661b6  mov     [rsp+218h+var_1C8], eax
0x1800661ba  lea     rax, [rsp+218h+var_88]
0x1800661c2  cmp     [rsp+218h+var_70], 7
0x1800661cb  cmova   rax, [rsp+218h+var_88]
0x1800661d4  mov     [rsp+218h+var_48], rax
0x1800661dc  mov     [rsp+218h+var_1C4], r14d
0x1800661e1  mov     dword ptr [rsp+218h+lpCriticalSection], edi
0x1800661e5  lea     rax, [rsp+218h+var_1B0]
0x1800661ea  mov     [rsp+218h+var_1D8], rax
0x1800661ef  lea     rax, [rsp+218h+var_1C8]
0x1800661f4  mov     [rsp+218h+var_1E0], rax
0x1800661f9  lea     rax, [rsp+218h+var_48]
0x180066201  mov     [rsp+218h+var_1E8], rax
0x180066206  lea     rax, [rsp+218h+var_1C4]
0x18006620b  mov     [rsp+218h+var_1F0], rax
0x180066210  lea     rax, [rsp+218h+lpCriticalSection]
0x180066215  mov     qword ptr [rsp+218h+var_1F8], rax
0x18006621a  lea     rdx, byte_180192C6D
0x180066221  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@_W@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@_W@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066226  lea     rcx, [rsp+218h+var_68]; void *
0x18006622e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x180066233  test    ebx, ebx
0x180066235  jnz     loc_18006641E
0x18006623b  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, r14b
0x180066242  jz      loc_180066907
0x180066248  lea     r9, [rsp+218h+var_88]
0x180066250  cmp     [rsp+218h+var_70], 7
0x180066259  cmova   r9, [rsp+218h+var_88]
0x180066262  lea     rax, [rsp+218h+Row.PhysicalAddress]
0x18006626a  mov     [rsp+218h+var_1E0], rax
0x18006626f  movzx   eax, word ptr [rsp+218h+Row.PhysicalAddressLength]
0x180066277  mov     word ptr [rsp+218h+var_1E8], ax
0x18006627c  mov     eax, [rsp+218h+Row.State]
0x180066283  mov     dword ptr [rsp+218h+var_1F0], eax
0x180066287  mov     [rsp+218h+var_1F8], ebx
0x18006628b  jmp     loc_180066490
0x180066290  mov     ebx, 4D5h
0x180066295  mov     [rsp+218h+var_1B8], ebx
0x180066299  mov     eax, cs:dword_1801BD288
0x18006629f  cmp     eax, 4
0x1800662a2  jbe     loc_180066396
0x1800662a8  mov     eax, [rsp+218h+Row.State]
0x1800662af  mov     dword ptr [rsp+218h+lpCriticalSection], eax
0x1800662b3  lea     rax, [rsp+218h+var_88]
0x1800662bb  cmp     [rsp+218h+var_70], 7
0x1800662c4  cmova   rax, [rsp+218h+var_88]
0x1800662cd  mov     [rsp+218h+var_48], rax
0x1800662d5  mov     [rsp+218h+var_1C4], r14d
0x1800662da  mov     [rsp+218h+var_1C8], edi
0x1800662de  lea     rax, [rsp+218h+lpCriticalSection]
0x1800662e3  mov     [rsp+218h+var_1E0], rax
0x1800662e8  lea     rax, [rsp+218h+var_48]
0x1800662f0  mov     [rsp+218h+var_1E8], rax
0x1800662f5  lea     rax, [rsp+218h+var_1C4]
0x1800662fa  mov     [rsp+218h+var_1F0], rax
0x1800662ff  lea     rax, [rsp+218h+var_1C8]
0x180066304  mov     qword ptr [rsp+218h+var_1F8], rax
0x180066309  lea     rdx, byte_180192CE1
0x180066310  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180066315  jmp     short loc_180066396
0x180066317  mov     eax, cs:dword_1801BD288
0x18006631d  cmp     eax, 4
0x180066320  jbe     short loc_180066388
0x180066322  mov     dword ptr [rsp+218h+lpCriticalSection], ebx
0x180066326  lea     rax, [rsp+218h+var_88]
0x18006632e  cmp     [rsp+218h+var_70], 7
0x180066337  cmova   rax, [rsp+218h+var_88]
0x180066340  mov     [rsp+218h+var_48], rax
0x180066348  mov     [rsp+218h+var_1C4], r14d
0x18006634d  mov     [rsp+218h+var_1C8], edi
0x180066351  lea     rax, [rsp+218h+lpCriticalSection]
0x180066356  mov     [rsp+218h+var_1E0], rax
0x18006635b  lea     rax, [rsp+218h+var_48]
0x180066363  mov     [rsp+218h+var_1E8], rax
0x180066368  lea     rax, [rsp+218h+var_1C4]
0x18006636d  mov     [rsp+218h+var_1F0], rax
0x180066372  lea     rax, [rsp+218h+var_1C8]
0x180066377  mov     qword ptr [rsp+218h+var_1F8], rax
0x18006637c  lea     rdx, unk_180192A98
0x180066383  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180066388  cmp     ebx, 43h ; 'C'
0x18006638b  jnz     short loc_180066396
0x18006638d  cmp     edi, 1
0x180066390  jnb     loc_180066233
0x180066396  inc     edi
0x180066398  jmp     loc_1800660BA
0x18006639d  mov     eax, cs:dword_1801BD288
0x1800663a3  cmp     eax, 4
0x1800663a6  jbe     short loc_180066415
0x1800663a8  mov     eax, [rsp+218h+Row.State]
0x1800663af  mov     dword ptr [rsp+218h+lpCriticalSection], eax
0x1800663b3  lea     rax, [rsp+218h+var_88]
0x1800663bb  cmp     [rsp+218h+var_70], 7
0x1800663c4  cmova   rax, [rsp+218h+var_88]
0x1800663cd  mov     [rsp+218h+var_48], rax
0x1800663d5  mov     [rsp+218h+var_1C4], r14d
0x1800663da  mov     [rsp+218h+var_1C8], edi
0x1800663de  lea     rax, [rsp+218h+lpCriticalSection]
0x1800663e3  mov     [rsp+218h+var_1E0], rax
0x1800663e8  lea     rax, [rsp+218h+var_48]
0x1800663f0  mov     [rsp+218h+var_1E8], rax
0x1800663f5  lea     rax, [rsp+218h+var_1C4]
0x1800663fa  mov     [rsp+218h+var_1F0], rax
0x1800663ff  lea     rax, [rsp+218h+var_1C8]
0x180066404  mov     qword ptr [rsp+218h+var_1F8], rax
0x180066409  lea     rdx, unk_180192BD0
0x180066410  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180066415  mov     ebx, 4C7h
0x18006641a  mov     [rsp+218h+var_1B8], ebx
0x18006641e  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, 10h
0x180066425  jz      short loc_180066451
0x180066427  lea     r9, [rsp+218h+var_88]
0x18006642f  cmp     [rsp+218h+var_70], 7
0x180066438  cmova   r9, [rsp+218h+var_88]
0x180066441  lea     r8, [rsi+90h]
0x180066448  mov     [rsp+218h+var_1F8], ebx
0x18006644c  call    McTemplateU0jzq_EventWriteTransfer
0x180066451  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, r14b
0x180066458  jz      loc_180066907
0x18006645e  lea     r9, [rsp+218h+var_88]
0x180066466  cmp     [rsp+218h+var_70], 7
0x18006646f  cmova   r9, [rsp+218h+var_88]
0x180066478  xor     eax, eax
0x18006647a  mov     [rsp+218h+var_1E0], rax
0x18006647f  mov     word ptr [rsp+218h+var_1E8], ax
0x180066484  mov     dword ptr [rsp+218h+var_1F0], 7
0x18006648c  mov     [rsp+218h+var_1F8], ebx
0x180066490  lea     r8, [rsi+90h]
0x180066497  call    McTemplateU0jzqqhbr4_EventWriteTransfer
0x18006649c  jmp     loc_180066907
0x1800664a1  xor     edi, edi
0x1800664a3  cmp     edi, r14d
0x1800664a6  jnb     loc_180066907
0x1800664ac  cmp     cs:?s_singleInstance@L3Manager@@0V?$shared_ptr@VL3Manager@@@std@@A, 0; std::shared_ptr<L3Manager> L3Manager::s_singleInstance
0x1800664b4  jz      loc_180066886
0x1800664ba  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, r14b
0x1800664c1  jz      short loc_1800664F0
0x1800664c3  lea     r9, [rsp+218h+var_88]
0x1800664cb  cmp     [rsp+218h+var_70], 7
0x1800664d4  cmova   r9, [rsp+218h+var_88]
0x1800664dd  lea     r8, [rsi+90h]
0x1800664e4  lea     rdx, StartIpAddressResolution
0x1800664eb  call    McTemplateU0jz_EventWriteTransfer
0x1800664f0  xor     edx, edx; SourceAddress
0x1800664f2  lea     rcx, [rsp+218h+Row]; Row
0x1800664fa  call    cs:__imp_ResolveIpNetEntry2
0x180066500  mov     ebx, eax
0x180066502  mov     rcx, [rsp+218h]; this
0x18006650a  test    eax, eax
0x18006650c  jz      short loc_180066522
0x18006650e  mov     r9d, eax; char *
0x180066511  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180066518  mov     edx, 7F4h; void *
0x18006651d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180066522  mov     [rsp+218h+var_1B8], ebx
0x180066526  test    ebx, ebx
0x180066528  jnz     loc_180066786
0x18006652e  mov     ecx, [rsp+218h+Row.State]
0x180066535  test    ecx, ecx
0x180066537  jz      loc_1800666AF
0x18006653d  sub     ecx, 1
0x180066540  jz      loc_1800666AF
0x180066546  sub     ecx, 1
0x180066549  jz      loc_1800666AF
0x18006654f  sub     ecx, 1
0x180066552  jz      loc_1800666AF
0x180066558  cmp     ecx, 1
0x18006655b  jz      loc_1800666AF
0x180066561  lea     rax, [rsp+218h+Row.PhysicalAddress]
0x180066569  mov     [rsp+218h+var_48], rax
0x180066571  mov     eax, [rsp+218h+Row.PhysicalAddressLength]
0x180066578  lea     rcx, [rsp+218h+Row.PhysicalAddress]
0x180066580  add     rcx, rax
0x180066583  mov     [rsp+218h+var_40], rcx
0x18006658b  lea     rdx, [rsp+218h+var_48]
0x180066593  lea     rcx, [rsp+218h+var_68]
0x18006659b  call    ??$HexStringFromBytes@V?$pointer_range@PEAE@details@wil@@@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$pointer_range@PEAE@details@wil@@@Z; HexStringFromBytes<wil::details::pointer_range<uchar *>>(wil::details::pointer_range<uchar *> const &)
0x1800665a0  mov     eax, cs:dword_1801BD288
0x1800665a6  cmp     eax, 4
0x1800665a9  jbe     loc_180066645
0x1800665af  lea     rax, [rsp+218h+var_68]
0x1800665b7  cmp     [rsp+218h+var_50], 7
0x1800665c0  cmova   rax, [rsp+218h+var_68]
0x1800665c9  mov     [rsp+218h+var_48], rax
0x1800665d1  mov     eax, [rsp+218h+Row.State]
0x1800665d8  mov     dword ptr [rsp+218h+lpCriticalSection], eax
0x1800665dc  lea     rax, [rsp+218h+var_88]
0x1800665e4  cmp     [rsp+218h+var_70], 7
0x1800665ed  cmova   rax, [rsp+218h+var_88]
0x1800665f6  mov     [rsp+218h+var_1B0], rax
0x1800665fb  mov     [rsp+218h+var_1C4], r14d
0x180066600  mov     [rsp+218h+var_1C8], edi
0x180066604  lea     rax, [rsp+218h+var_48]
0x18006660c  mov     [rsp+218h+var_1D8], rax
0x180066611  lea     rax, [rsp+218h+lpCriticalSection]
0x180066616  mov     [rsp+218h+var_1E0], rax
0x18006661b  lea     rax, [rsp+218h+var_1B0]
0x180066620  mov     [rsp+218h+var_1E8], rax
0x180066625  lea     rax, [rsp+218h+var_1C4]
0x18006662a  mov     [rsp+218h+var_1F0], rax
0x18006662f  lea     rax, [rsp+218h+var_1C8]
0x180066634  mov     qword ptr [rsp+218h+var_1F8], rax
0x180066639  lea     rdx, word_180192AFA
0x180066640  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@_W@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@_W@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066645  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, r14b
  ... truncated ...
```
