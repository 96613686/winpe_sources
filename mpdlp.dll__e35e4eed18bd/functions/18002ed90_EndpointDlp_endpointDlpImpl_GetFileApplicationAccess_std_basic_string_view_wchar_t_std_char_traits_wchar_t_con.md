# EndpointDlp::endpointDlpImpl::GetFileApplicationAccess(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &,ulong,unsigned __int64,ulong,EndpointDlp::Client::ExtendedAttributes const &,ulong,std::optional<EndpointDlp::Client::FileAccessInfo> &)

- ea: `0x18002ed90`
- end: `0x18002f796`
- name: `?GetFileApplicationAccess@endpointDlpImpl@EndpointDlp@@QEBAJAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@K_KKAEBUExtendedAttributes@Client@2@KAEAV?$optional@UFileAccessInfo@Client@EndpointDlp@@@4@@Z`
- size: `2566`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ec38`
- `0x1800857d0`

## callees

- `0x1800058a4`
- `0x180017190`
- `0x1800225f4`
- `0x1800263e8`
- `0x180026a60`
- `0x18002ed90`
- `0x1800301a0`
- `0x180033520`
- `0x180034420`
- `0x1800398a0`
- `0x180039ecc`
- `0x1800542e8`
- `0x180054db0`
- `0x180055140`
- `0x1800555bc`
- `0x1800a1d18`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180119428`
- `0x1801710ec`
- `0x1801780fc`
- `0x18023a290`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18002f18b`
- `KERNEL32!AcquireSRWLockShared` at `0x18002f1ba`
- `KERNEL32!AcquireSRWLockShared` at `0x18002f51d`
- `KERNEL32!AcquireSRWLockShared` at `0x18002f18b`
- `KERNEL32!AcquireSRWLockShared` at `0x18002f1ba`
- `KERNEL32!AcquireSRWLockShared` at `0x18002f51d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002f1b1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002f1e1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002f546`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002f1b1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002f1e1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002f546`
- `ADVAPI32!EventWriteTransfer` at `0x18002ef0a`
- `ADVAPI32!EventWriteTransfer` at `0x18002ef0a`

## string_xrefs

- `0x18002ee2c`: `Invalid argument for DlpGetFileApplicationAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall EndpointDlp::endpointDlpImpl::GetFileApplicationAccess(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        int a5,
        _BYTE *a6,
        int a7,
        __int64 a8,
        char a9,
        __int64 a10)
{
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // r13
  struct EndpointDlp::TraceLoggingProvider *v14; // rax
  _DWORD *v15; // rcx
  int RuleIdsFromBlob; // r15d
  struct EndpointDlp::TraceLoggingProvider *v18; // rax
  int v19; // r8d
  int v20; // r9d
  _DWORD *v21; // rcx
  __int64 UserSidForCurrentProcess; // rax
  int v23; // ebx
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  __m128i si128; // xmm0
  const struct std::nothrow_t *v27; // rdx
  void *v28; // rcx
  char AnyFileUserScopeUnlocked; // r15
  char IsUserInScopeForFileSourceMonitoringUnlocked; // al
  bool v31; // zf
  __int64 v32; // r15
  __int64 RuleIdsFromExt; // rbx
  __int128 *v34; // rdx
  char v35; // cl
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // r8
  int v40; // ecx
  int v41; // esi
  __int64 v42; // rcx
  _QWORD *v43; // rax
  unsigned int FileApplicationAccessByRuleIds; // esi
  const struct std::nothrow_t *v45; // rdx
  void *v46; // rcx
  const struct std::nothrow_t *v47; // rdx
  void *v48; // rcx
  wil::ResultException *v49; // rbx
  int v50; // edi
  struct EndpointDlp::TraceLoggingProvider *v51; // rax
  _DWORD *v52; // rcx
  struct EndpointDlp::TraceLoggingProvider *v53; // rax
  _DWORD *v54; // rbx
  char v55; // [rsp+60h] [rbp-1C8h]
  char v56; // [rsp+60h] [rbp-1C8h]
  int v57; // [rsp+64h] [rbp-1C4h]
  int v58; // [rsp+68h] [rbp-1C0h] BYREF
  const wchar_t *v59; // [rsp+70h] [rbp-1B8h] BYREF
  const wchar_t *v60; // [rsp+78h] [rbp-1B0h] BYREF
  __int128 v61; // [rsp+80h] [rbp-1A8h] BYREF
  __m128i v62; // [rsp+90h] [rbp-198h]
  __int64 v63; // [rsp+A0h] [rbp-188h]
  __int64 v64; // [rsp+A8h] [rbp-180h]
  __int64 v65; // [rsp+B0h] [rbp-178h]
  __int128 *v66; // [rsp+C0h] [rbp-168h]
  __int128 v67; // [rsp+C8h] [rbp-160h] BYREF
  char v68; // [rsp+D8h] [rbp-150h]
  wil::ResultException *v69; // [rsp+E0h] [rbp-148h] BYREF
  std::exception *v70; // [rsp+E8h] [rbp-140h] BYREF
  __int128 v71; // [rsp+F0h] [rbp-138h] BYREF
  __int64 v72; // [rsp+100h] [rbp-128h]
  _QWORD v73[2]; // [rsp+108h] [rbp-120h] BYREF
  __int64 v74; // [rsp+118h] [rbp-110h]
  unsigned __int64 v75; // [rsp+120h] [rbp-108h]
  __int64 v76; // [rsp+128h] [rbp-100h] BYREF
  unsigned __int64 v77; // [rsp+130h] [rbp-F8h]
  __int64 v78; // [rsp+138h] [rbp-F0h]
  int v79; // [rsp+140h] [rbp-E8h]
  char v80; // [rsp+144h] [rbp-E4h]
  char v81; // [rsp+148h] [rbp-E0h]
  __int128 v82; // [rsp+150h] [rbp-D8h] BYREF
  __m128i v83; // [rsp+160h] [rbp-C8h]
  _QWORD v84[2]; // [rsp+170h] [rbp-B8h] BYREF
  char v85; // [rsp+180h] [rbp-A8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+190h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1A0h] [rbp-88h] BYREF
  char *v88; // [rsp+1B0h] [rbp-78h]
  int v89; // [rsp+1B8h] [rbp-70h]
  int v90; // [rsp+1BCh] [rbp-6Ch]
  int *v91; // [rsp+1C0h] [rbp-68h]
  __int64 v92; // [rsp+1C8h] [rbp-60h]
  const wchar_t *v93; // [rsp+1D0h] [rbp-58h]
  __int64 v94; // [rsp+1D8h] [rbp-50h]

  v60 = (const wchar_t *)a2;
  v11 = a1;
  v12 = a8;
  v66 = (__int128 *)a8;
  v64 = a1;
  v65 = a2;
  v13 = a8;
  v63 = a8;
  *(_QWORD *)&EventDescriptor.Id = a10;
  v58 = 0;
  v57 = 0;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    v14 = EndpointDlp::TraceLoggingProvider::Instance();
    v15 = *(_DWORD **)v14;
    if ( **(_DWORD **)v14 > 2u )
    {
      v58 = -2147024809;
      v93 = L"Invalid argument for DlpGetFileApplicationAccess";
      v94 = 98;
      v91 = &v58;
      v92 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *((_QWORD *)v15 + 1);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v88 = &byte_1802C0A37;
      v89 = 36;
      v90 = 1;
      EventWriteTransfer(*((_QWORD *)v15 + 4), &EventDescriptor, 0, 0, 4u, &UserData);
    }
    return 2147942487LL;
  }
  v81 = 0;
  if ( !*(_BYTE *)(a8 + 64) )
    goto LABEL_11;
  RuleIdsFromBlob = EndpointDlp::endpointDlpImpl::GetRuleIdsFromBlob(
                      a1,
                      *(_QWORD *)(a8 + 56),
                      *(_DWORD *)(a8 + 48),
                      a2,
                      (__int64)&v76);
  v57 = RuleIdsFromBlob;
  if ( RuleIdsFromBlob < 0 || !v81 )
  {
    v18 = EndpointDlp::TraceLoggingProvider::Instance();
    v21 = *(_DWORD **)v18;
    if ( **(_DWORD **)v18 > 2u )
    {
      v59 = L"GetRuleIdsFromBlob: Failed to extract ruleIds from the blob";
      v58 = RuleIdsFromBlob;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v21,
        (unsigned int)&word_1802BFC3E,
        v19,
        v20,
        (__int64)&v58,
        (__int64)&v59);
    }
    if ( !v81 )
    {
LABEL_11:
      v62 = 0u;
      v61 = 0u;
      v76 = 0;
      v77 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v78 = 0;
      v79 = 0;
      v80 = 0;
      v81 = 1;
      std::vector<std::wstring>::_Tidy(&v61);
    }
  }
  if ( *(_BYTE *)(a4 + 32) && *(_QWORD *)(a4 + 16) )
  {
    UserSidForCurrentProcess = std::wstring::wstring(&v82, a4);
    v23 = 1;
  }
  else
  {
    UserSidForCurrentProcess = EndpointDlp::endpointDlpImpl::endpointDlpGetUserSidForCurrentProcess(v11, &v61);
    v23 = 2;
  }
  v58 = v23;
  std::wstring::wstring(v73, UserSidForCurrentProcess);
  if ( (v23 & 2) != 0 )
  {
    LOBYTE(v23) = v23 & 0xFD;
    if ( v62.m128i_i64[1] > 7uLL )
    {
      v24 = (const struct std::nothrow_t *)(2 * v62.m128i_i64[1] + 2);
      v25 = (void *)v61;
      if ( (unsigned __int64)v24 >= 0x1000 )
      {
        v24 = (const struct std::nothrow_t *)(2 * v62.m128i_i64[1] + 41);
        v25 = *(void **)(v61 - 8);
        if ( (unsigned __int64)(v61 - (_QWORD)v25 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v25, v24);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v62 = si128;
    LOWORD(v61) = 0;
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  if ( (v23 & 1) != 0 )
  {
    if ( v83.m128i_i64[1] > 7uLL )
    {
      v27 = (const struct std::nothrow_t *)(2 * v83.m128i_i64[1] + 2);
      v28 = (void *)v82;
      if ( (unsigned __int64)v27 >= 0x1000 )
      {
        v27 = (const struct std::nothrow_t *)(2 * v83.m128i_i64[1] + 41);
        v28 = *(void **)(v82 - 8);
        if ( (unsigned __int64)(v82 - (_QWORD)v28 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v28, v27);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v83 = si128;
    LOWORD(v82) = 0;
  }
  AnyFileUserScopeUnlocked = 0;
  v55 = 0;
  if ( v74 )
  {
    AcquireSRWLockShared((PSRWLOCK)(v11 + 368));
    v59 = (const wchar_t *)(v11 + 368);
    AnyFileUserScopeUnlocked = EndpointDlp::endpointDlpImpl::GetAnyFileUserScopeUnlocked(v11, v73);
    if ( v11 != -368 )
      ReleaseSRWLockShared((PSRWLOCK)(v11 + 368));
    AcquireSRWLockShared((PSRWLOCK)(v11 + 368));
    v59 = (const wchar_t *)(v11 + 368);
    IsUserInScopeForFileSourceMonitoringUnlocked = EndpointDlp::endpointDlpImpl::IsUserInScopeForFileSourceMonitoringUnlocked(
                                                     v11,
                                                     v73);
    v56 = IsUserInScopeForFileSourceMonitoringUnlocked;
    if ( v11 != -368 )
    {
      ReleaseSRWLockShared((PSRWLOCK)(v11 + 368));
      IsUserInScopeForFileSourceMonitoringUnlocked = v56;
    }
    v55 = IsUserInScopeForFileSourceMonitoringUnlocked;
  }
  v71 = 0;
  v72 = 0;
  if ( (AnyFileUserScopeUnlocked & 1) != 0 )
  {
    v31 = (AnyFileUserScopeUnlocked & 4) == 0;
    v32 = (__int64)v60;
    if ( !v31 )
    {
      EndpointDlp::Common::GetFileExtensions(&v82, v60);
      try
      {
        RuleIdsFromExt = EndpointDlp::endpointDlpImpl::GetRuleIdsFromExt(
                           v11,
                           (unsigned int)&v61,
                           (unsigned int)v73,
                           (unsigned int)&v82,
                           1);
        if ( &v71 != (__int128 *)RuleIdsFromExt )
        {
          std::vector<std::wstring>::_Tidy(&v71);
          v71 = *(_OWORD *)RuleIdsFromExt;
          v72 = *(_QWORD *)(RuleIdsFromExt + 16);
          *(_QWORD *)RuleIdsFromExt = 0;
          *(_QWORD *)(RuleIdsFromExt + 8) = 0;
          *(_QWORD *)(RuleIdsFromExt + 16) = 0;
        }
        std::vector<std::wstring>::_Tidy(&v61);
      }
      catch ( wil::ResultException *v69 )
      {
        v49 = v69;
        v50 = *((_DWORD *)v69 + 8);
        v57 = v50;
        v51 = EndpointDlp::TraceLoggingProvider::Instance();
        v52 = *(_DWORD **)v51;
        if ( **(_DWORD **)v51 > 2u )
        {
          v59 = (const wchar_t *)*((_QWORD *)v49 + 6);
          v60 = L"GetRuleIdsFromExt: Failed to extract extension based ruleIds from the extension";
          v58 = v50;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            (int)v52,
            (int)&byte_1802C07E1,
            (__int64)&v58,
            (__int64)&v60,
            (__int64)&v59);
        }
        std::vector<std::wstring>::_Assign_counted_range<std::wstring const *>(&v71, 0, 0);
        v13 = v63;
        v12 = v63;
        v32 = v65;
        v11 = v64;
      }
      catch ( std::exception *v70 )
      {
        v57 = -2147418113;
        v53 = EndpointDlp::TraceLoggingProvider::Instance();
        v54 = *(_DWORD **)v53;
        if ( **(_DWORD **)v53 > 2u )
        {
          v59 = (const wchar_t *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v70 + 8LL))(v70);
          v60 = L"GetRuleIdsFromExt: Failed to extract extension based ruleIds from the extension";
          v58 = -2147418113;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
            (int)v54,
            (int)&byte_1802C1109,
            (__int64)&v58,
            (__int64)&v60,
            (__int64)&v59);
        }
        std::vector<std::wstring>::_Assign_counted_range<std::wstring const *>(&v71, 0, 0);
        v13 = v63;
        v12 = v63;
        v32 = v65;
        v11 = v64;
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v82);
    }
  }
  else
  {
    v32 = (__int64)v60;
  }
  if ( v74 )
  {
    if ( v55 )
    {
      v34 = v66;
      v35 = *((_BYTE *)v66 + 16);
      if ( v35 || *(_BYTE *)(v13 + 40) )
      {
        v61 = 0;
        v62.m128i_i64[0] = 0;
        v66 = &v67;
        v68 = 0;
        if ( *(_BYTE *)(v12 + 40) )
        {
          v67 = 0;
          v36 = *(_QWORD *)(v12 + 32);
          if ( v36 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
            v35 = *((_BYTE *)v34 + 16);
          }
          v67 = *(_OWORD *)(v12 + 24);
          v68 = 1;
        }
        v59 = (const wchar_t *)&v82;
        v83.m128i_i8[0] = 0;
        if ( v35 )
        {
          v82 = 0;
          v37 = *(_QWORD *)(v12 + 8);
          if ( v37 )
            _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
          v82 = *(_OWORD *)v12;
          v83.m128i_i8[0] = 1;
        }
        v38 = std::wstring::wstring(&UserData, v32);
        EndpointDlp::endpointDlpImpl::GetRuleIdsFromFileSourceMonitoringEAs(
          v11,
          (unsigned int)&v61,
          (unsigned int)v73,
          v38,
          (__int64)&v82,
          (__int64)&v67);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&UserData);
        std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(
          &v71,
          *((_QWORD *)&v71 + 1),
          v61,
          (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 5);
        std::vector<std::wstring>::_Tidy(&v61);
      }
    }
  }
  v39 = (__int64)(*((_QWORD *)&v71 + 1) - v71) >> 5;
  if ( v39 )
  {
    v31 = v80 == 0;
    _mm_lfence();
    if ( v31 )
      std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(
        &v76,
        v77,
        v71,
        (__int64)(*((_QWORD *)&v71 + 1) - v71) >> 5);
    else
      std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(&v76, v71, v39);
    v40 = v79;
    if ( !v79 )
    {
      if ( (unsigned __int64)((__int64)(v77 - v76) >> 5) > 1 )
        v40 = 2;
      v79 = v40;
    }
  }
  if ( !v81 )
    std::_Throw_bad_optional_access();
  v41 = 0;
  AcquireSRWLockShared((PSRWLOCK)(v11 + 368));
  v42 = *(_QWORD *)(v11 + 400);
  if ( v42 )
    v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 104LL))(v42);
  if ( v11 != -368 )
    ReleaseSRWLockShared((PSRWLOCK)(v11 + 368));
  v85 = 0;
  if ( v74 )
  {
    v43 = v73;
    if ( v75 > 7 )
      v43 = (_QWORD *)v73[0];
    v84[0] = v43;
    v84[1] = v74;
    v85 = 1;
  }
  v61 = *a3;
  v62.m128i_i8[0] = 1;
  FileApplicationAccessByRuleIds = EndpointDlp::endpointDlpImpl::GetFileApplicationAccessByRuleIds(
                                     (const wchar_t *)v11,
                                     v32,
                                     (const wchar_t *)&v76,
                                     v79,
                                     (__int64)v84,
                                     (__int64)&v61,
                                     a5,
                                     a6,
                                     a7,
                                     a9,
                                     v41,
                                     *(__int64 *)&EventDescriptor.Id);
  std::vector<std::wstring>::_Tidy(&v71);
  if ( v57 < 0 )
  {
    if ( v75 <= 7 )
    {
LABEL_78:
      v74 = 0;
      v75 = 7;
      LOWORD(v73[0]) = 0;
      if ( v81 )
        std::vector<std::wstring>::_Tidy(&v76);
      return (unsigned int)v57;
    }
    v45 = (const struct std::nothrow_t *)(2 * v75 + 2);
    v46 = (void *)v73[0];
    if ( (unsigned __int64)v45 < 0x1000
      || (v45 = (const struct std::nothrow_t *)(2 * v75 + 41),
          v46 = *(void **)(v73[0] - 8LL),
          (unsigned __int64)(v73[0] - (_QWORD)v46 - 8LL) <= 0x1F) )
    {
      operator delete(v46, v45);
      goto LABEL_78;
    }
LABEL_91:
    invoke_watson(0, 0, 0, 0, 0);
  }
  if ( v75 > 7 )
  {
    v47 = (const struct std::nothrow_t *)(2 * v75 + 2);
    v48 = (void *)v73[0];
    if ( (unsigned __int64)v47 >= 0x1000 )
    {
      v47 = (const struct std::nothrow_t *)(2 * v75 + 41);
      v48 = *(void **)(v73[0] - 8LL);
      if ( (unsigned __int64)(v73[0] - (_QWORD)v48 - 8LL) > 0x1F )
        goto LABEL_91;
    }
    operator delete(v48, v47);
  }
  v74 = 0;
  v75 = 7;
  LOWORD(v73[0]) = 0;
  if ( v81 )
    std::vector<std::wstring>::_Tidy(&v76);
  return FileApplicationAccessByRuleIds;
}

```

## disassembly

```asm
0x18002ed90  mov     [rsp+arg_10], r8
0x18002ed95  push    rbx
0x18002ed96  push    rsi
0x18002ed97  push    rdi
0x18002ed98  push    r12
0x18002ed9a  push    r13
0x18002ed9c  push    r14
0x18002ed9e  push    r15
0x18002eda0  sub     rsp, 1F0h
0x18002eda7  mov     rax, cs:__security_cookie
0x18002edae  xor     rax, rsp
0x18002edb1  mov     [rsp+228h+var_48], rax
0x18002edb9  mov     rbx, r9
0x18002edbc  mov     [rsp+228h+var_1B0], rdx
0x18002edc1  mov     r14, rcx
0x18002edc4  mov     rsi, [rsp+228h+arg_38]
0x18002edcc  mov     [rsp+228h+var_168], rsi
0x18002edd4  mov     [rsp+228h+var_180], rcx
0x18002eddc  mov     [rsp+228h+var_178], rdx
0x18002ede4  mov     r13, rsi
0x18002ede7  mov     [rsp+228h+var_188], rsi
0x18002edef  mov     rax, [rsp+228h+arg_48]
0x18002edf7  mov     qword ptr [rsp+228h+EventDescriptor.Id], rax
0x18002edff  xor     edi, edi
0x18002ee01  mov     [rsp+228h+var_1C0], edi
0x18002ee05  mov     [rsp+228h+var_1C4], edi
0x18002ee09  cmp     [rdx+8], rdi
0x18002ee0d  jnz     loc_18002EF1A
0x18002ee13  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x18002ee18  mov     rcx, [rax]
0x18002ee1b  cmp     dword ptr [rcx], 2
0x18002ee1e  jbe     loc_18002EF10
0x18002ee24  mov     [rsp+228h+var_1C0], 80070057h
0x18002ee2c  lea     rax, aInvalidArgumen_12; "Invalid argument for DlpGetFileApplicat"...
0x18002ee33  mov     [rsp+228h+var_58], rax
0x18002ee3b  mov     [rsp+228h+var_50], 62h ; 'b'
0x18002ee47  lea     rax, [rsp+228h+var_1C0]
0x18002ee4c  mov     [rsp+228h+var_68], rax
0x18002ee54  mov     [rsp+228h+var_60], 4
0x18002ee60  mov     dword ptr [rsp+228h+EventDescriptor.Id], 0B000000h
0x18002ee6b  movzx   eax, cs:word_1802C0A2D
0x18002ee72  mov     dword ptr [rsp+228h+EventDescriptor.Level], eax
0x18002ee79  mov     [rsp+228h+EventDescriptor.Keyword], rdi
0x18002ee81  mov     rax, [rcx+8]
0x18002ee85  mov     [rsp+228h+var_88.Ptr], rax
0x18002ee8d  movzx   eax, word ptr [rax]
0x18002ee90  mov     [rsp+228h+var_88.Size], eax
0x18002ee97  mov     r12d, 2
0x18002ee9d  mov     dword ptr [rsp+228h+var_88.0Ch], r12d
0x18002eea5  lea     rax, byte_1802C0A37
0x18002eeac  mov     [rsp+228h+var_78], rax
0x18002eeb4  mov     [rsp+228h+var_70], 24h ; '$'
0x18002eebf  mov     ebx, 1
0x18002eec4  mov     [rsp+228h+var_6C], ebx
0x18002eecb  lea     rax, _TraceLoggingMetadataEnd
0x18002eed2  lea     rdx, _TraceLoggingMetadata
0x18002eed9  sub     eax, edx
0x18002eedb  mov     [rsp+228h+var_1C4], eax
0x18002eedf  mov     eax, [rsp+228h+var_1C4]
0x18002eee3  lea     rax, [rsp+228h+var_88]
0x18002eeeb  mov     [rsp+228h+UserData], rax; UserData
0x18002eef0  mov     [rsp+228h+UserDataCount], 4; UserDataCount
0x18002eef8  xor     r9d, r9d; RelatedActivityId
0x18002eefb  xor     r8d, r8d; ActivityId
0x18002eefe  lea     rdx, [rsp+228h+EventDescriptor]; EventDescriptor
0x18002ef06  mov     rcx, [rcx+20h]; RegHandle
0x18002ef0a  call    cs:__imp_EventWriteTransfer
0x18002ef10  mov     eax, 80070057h
0x18002ef15  jmp     loc_18002F72E
0x18002ef1a  mov     [rsp+228h+var_E0], dil
0x18002ef22  cmp     byte ptr [rsi+40h], 0
0x18002ef26  jz      loc_18002EFAE
0x18002ef2c  lea     rax, [rsp+228h+var_100]
0x18002ef34  mov     qword ptr [rsp+228h+UserDataCount], rax
0x18002ef39  mov     r9, rdx
0x18002ef3c  mov     r8d, [rsi+30h]
0x18002ef40  mov     rdx, [rsi+38h]
0x18002ef44  call    ?GetRuleIdsFromBlob@endpointDlpImpl@EndpointDlp@@AEBAJQEAXKAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$optional@URuleInfo@endpointDlpImpl@EndpointDlp@@@4@@Z; EndpointDlp::endpointDlpImpl::GetRuleIdsFromBlob(void * const,ulong,std::wstring_view const &,std::optional<EndpointDlp::endpointDlpImpl::RuleInfo> &)
0x18002ef49  mov     r15d, eax
0x18002ef4c  mov     [rsp+228h+var_1C4], eax
0x18002ef50  test    eax, eax
0x18002ef52  js      short loc_18002EF62
0x18002ef54  cmp     [rsp+228h+var_E0], 0
0x18002ef5c  jnz     loc_18002F03C
0x18002ef62  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x18002ef67  mov     rcx, [rax]
0x18002ef6a  cmp     dword ptr [rcx], 2
0x18002ef6d  jbe     short loc_18002EFA0
0x18002ef6f  lea     rax, aGetruleidsfrom_0; "GetRuleIdsFromBlob: Failed to extract r"...
0x18002ef76  mov     [rsp+228h+var_1B8], rax
0x18002ef7b  mov     [rsp+228h+var_1C0], r15d
0x18002ef80  lea     rax, [rsp+228h+var_1B8]
0x18002ef85  mov     [rsp+228h+UserData], rax
0x18002ef8a  lea     rax, [rsp+228h+var_1C0]
0x18002ef8f  mov     qword ptr [rsp+228h+UserDataCount], rax
0x18002ef94  lea     rdx, word_1802BFC3E
0x18002ef9b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18002efa0  cmp     [rsp+228h+var_E0], 0
0x18002efa8  jnz     loc_18002F03C
0x18002efae  xorps   xmm0, xmm0
0x18002efb1  movdqu  [rsp+228h+var_1A8], xmm0
0x18002efba  mov     dword ptr [rsp+228h+var_198+8], edi
0x18002efc1  mov     byte ptr [rsp+228h+var_198+0Ch], 0
0x18002efc9  xor     eax, eax
0x18002efcb  mov     word ptr [rsp+228h+var_198+0Dh], ax
0x18002efd3  mov     byte ptr [rsp+228h+var_198+0Fh], al
0x18002efda  mov     qword ptr [rsp+228h+var_198], rdi
0x18002efe2  psrldq  xmm0, 8
0x18002efe7  mov     qword ptr [rsp+228h+var_1A8+8], rdi
0x18002efef  mov     rax, qword ptr [rsp+228h+var_1A8]
0x18002eff7  mov     qword ptr [rsp+228h+var_1A8], rdi
0x18002efff  mov     [rsp+228h+var_100], rax
0x18002f007  movq    [rsp+228h+var_F8], xmm0
0x18002f010  mov     [rsp+228h+var_F0], rdi
0x18002f018  mov     [rsp+228h+var_E8], edi
0x18002f01f  mov     [rsp+228h+var_E4], 0
0x18002f027  mov     [rsp+228h+var_E0], 1
0x18002f02f  lea     rcx, [rsp+228h+var_1A8]
0x18002f037  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002f03c  cmp     byte ptr [rbx+20h], 0
0x18002f040  jz      short loc_18002F067
0x18002f042  cmp     qword ptr [rbx+10h], 0
0x18002f047  jz      short loc_18002F067
0x18002f049  mov     rdx, rbx
0x18002f04c  lea     rcx, [rsp+228h+var_D8]
0x18002f054  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002f059  nop
0x18002f05a  mov     ebx, 1
0x18002f05f  mov     r12d, 2
0x18002f065  jmp     short loc_18002F081
0x18002f067  lea     rdx, [rsp+228h+var_1A8]
0x18002f06f  mov     rcx, r14
0x18002f072  call    ?endpointDlpGetUserSidForCurrentProcess@endpointDlpImpl@EndpointDlp@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; EndpointDlp::endpointDlpImpl::endpointDlpGetUserSidForCurrentProcess(void)
0x18002f077  nop
0x18002f078  mov     r12d, 2
0x18002f07e  mov     ebx, r12d
0x18002f081  mov     [rsp+228h+var_1C0], ebx
0x18002f085  mov     rdx, rax
0x18002f088  lea     rcx, [rsp+228h+var_120]
0x18002f090  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002f095  nop
0x18002f096  test    bl, 2
0x18002f099  jz      short loc_18002F101
0x18002f09b  and     ebx, 0FFFFFFFDh
0x18002f09e  mov     rdx, qword ptr [rsp+228h+var_198+8]
0x18002f0a6  cmp     rdx, 7
0x18002f0aa  jbe     short loc_18002F0E6
0x18002f0ac  lea     rdx, ds:2[rdx*2]
0x18002f0b4  mov     rcx, qword ptr [rsp+228h+var_1A8]
0x18002f0bc  mov     rax, rcx
0x18002f0bf  cmp     rdx, 1000h
0x18002f0c6  jb      short loc_18002F0E1
0x18002f0c8  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18002f0cc  mov     rcx, [rcx-8]; void *
0x18002f0d0  sub     rax, rcx
0x18002f0d3  sub     rax, 8
0x18002f0d7  cmp     rax, 1Fh
0x18002f0db  ja      loc_18002F751
0x18002f0e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f0e6  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002f0ee  movdqu  [rsp+228h+var_198], xmm0
0x18002f0f7  mov     word ptr [rsp+228h+var_1A8], di
0x18002f0ff  jmp     short loc_18002F109
0x18002f101  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002f109  test    bl, 1
0x18002f10c  jz      short loc_18002F16F
0x18002f10e  mov     rdx, [rsp+228h+var_C0]
0x18002f116  cmp     rdx, 7
0x18002f11a  jbe     short loc_18002F15E
0x18002f11c  lea     rdx, ds:2[rdx*2]
0x18002f124  mov     rcx, qword ptr [rsp+228h+var_D8]
0x18002f12c  mov     rax, rcx
0x18002f12f  cmp     rdx, 1000h
0x18002f136  jb      short loc_18002F151
0x18002f138  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18002f13c  mov     rcx, [rcx-8]; void *
0x18002f140  sub     rax, rcx
0x18002f143  sub     rax, 8
0x18002f147  cmp     rax, 1Fh
0x18002f14b  ja      loc_18002F766
0x18002f151  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f156  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002f15e  movdqu  xmmword ptr [rsp+160h], xmm0
0x18002f167  mov     word ptr [rsp+228h+var_D8], di
0x18002f16f  mov     r15d, edi
0x18002f172  mov     [rsp+228h+var_1C8], r15b
0x18002f177  cmp     [rsp+228h+var_110], r15
0x18002f17f  jz      short loc_18002F1F0
0x18002f181  lea     rbx, [r14+170h]
0x18002f188  mov     rcx, rbx; SRWLock
0x18002f18b  call    cs:__imp_AcquireSRWLockShared
0x18002f191  mov     [rsp+228h+var_1B8], rbx
0x18002f196  lea     rdx, [rsp+228h+var_120]
0x18002f19e  mov     rcx, r14
0x18002f1a1  call    ?GetAnyFileUserScopeUnlocked@endpointDlpImpl@EndpointDlp@@AEBAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; EndpointDlp::endpointDlpImpl::GetAnyFileUserScopeUnlocked(std::wstring const &)
0x18002f1a6  mov     r15d, eax
0x18002f1a9  test    rbx, rbx
0x18002f1ac  jz      short loc_18002F1B7
0x18002f1ae  mov     rcx, rbx; SRWLock
0x18002f1b1  call    cs:__imp_ReleaseSRWLockShared
0x18002f1b7  mov     rcx, rbx; SRWLock
0x18002f1ba  call    cs:__imp_AcquireSRWLockShared
0x18002f1c0  mov     [rsp+228h+var_1B8], rbx
0x18002f1c5  lea     rdx, [rsp+228h+var_120]
0x18002f1cd  mov     rcx, r14
0x18002f1d0  call    ?IsUserInScopeForFileSourceMonitoringUnlocked@endpointDlpImpl@EndpointDlp@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; EndpointDlp::endpointDlpImpl::IsUserInScopeForFileSourceMonitoringUnlocked(std::wstring const &)
0x18002f1d5  mov     [rsp+228h+var_1C8], al
0x18002f1d9  test    rbx, rbx
0x18002f1dc  jz      short loc_18002F1EC
0x18002f1de  mov     rcx, rbx; SRWLock
0x18002f1e1  call    cs:__imp_ReleaseSRWLockShared
0x18002f1e7  movzx   eax, [rsp+228h+var_1C8]
0x18002f1ec  mov     [rsp+228h+var_1C8], al
0x18002f1f0  xorps   xmm1, xmm1
0x18002f1f3  movdqu  [rsp+228h+var_138], xmm1
0x18002f1fc  mov     [rsp+228h+var_128], rdi
0x18002f204  test    r15b, 1
0x18002f208  jz      loc_18002F2F2
0x18002f20e  test    r15b, 4
0x18002f212  mov     r15, [rsp+228h+var_1B0]
0x18002f217  jz      loc_18002F2F7
0x18002f21d  mov     rdx, r15
0x18002f220  lea     rcx, [rsp+228h+var_D8]
0x18002f228  call    ?GetFileExtensions@Common@EndpointDlp@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@4@@Z; EndpointDlp::Common::GetFileExtensions(std::wstring_view const &)
0x18002f22d  nop
0x18002f22e  mov     byte ptr [rsp+228h+UserDataCount], 1
0x18002f233  lea     r9, [rsp+228h+var_D8]
0x18002f23b  lea     r8, [rsp+228h+var_120]
0x18002f243  lea     rdx, [rsp+228h+var_1A8]
0x18002f24b  mov     rcx, r14
0x18002f24e  call    ?GetRuleIdsFromExt@endpointDlpImpl@EndpointDlp@@AEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@0_N@Z; EndpointDlp::endpointDlpImpl::GetRuleIdsFromExt(std::wstring const &,std::wstring const &,bool)
0x18002f253  mov     rbx, rax
0x18002f256  lea     rax, [rsp+228h+var_138]
0x18002f25e  cmp     rax, rbx
0x18002f261  jz      short loc_18002F29E
0x18002f263  lea     rcx, [rsp+228h+var_138]
0x18002f26b  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002f270  mov     rcx, [rbx]
0x18002f273  mov     qword ptr [rsp+228h+var_138], rcx
0x18002f27b  mov     rcx, [rbx+8]
0x18002f27f  mov     qword ptr [rsp+228h+var_138+8], rcx
0x18002f287  mov     rax, [rbx+10h]
0x18002f28b  mov     [rsp+228h+var_128], rax
0x18002f293  mov     [rbx], rdi
0x18002f296  mov     [rbx+8], rdi
0x18002f29a  mov     [rbx+10h], rdi
0x18002f29e  lea     rcx, [rsp+228h+var_1A8]
0x18002f2a6  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002f2ab  nop
0x18002f2ac  jmp     short loc_18002F2E3
0x18002f2ae  mov     ebx, [rsp+228h+var_1C4]
0x18002f2b2  mov     [rsp+228h+var_1C4], ebx
0x18002f2b6  jmp     short loc_18002F2C0
0x18002f2b8  mov     eax, [rsp+228h+var_1C4]
0x18002f2bc  mov     [rsp+228h+var_1C4], eax
0x18002f2c0  mov     r13, [rsp+228h+var_188]
0x18002f2c8  mov     rsi, r13
0x18002f2cb  mov     r15, [rsp+228h+var_178]
0x18002f2d3  mov     r14, [rsp+228h+var_180]
0x18002f2db  mov     r12d, 2
0x18002f2e1  xor     edi, edi
0x18002f2e3  lea     rcx, [rsp+228h+var_D8]; void *
0x18002f2eb  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18002f2f0  jmp     short loc_18002F2F7
0x18002f2f2  mov     r15, [rsp+228h+var_1B0]
0x18002f2f7  cmp     [rsp+228h+var_110], 0
0x18002f300  jz      loc_18002F474
0x18002f306  cmp     [rsp+228h+var_1C8], 0
0x18002f30b  jz      loc_18002F474
0x18002f311  mov     rdx, [rsp+228h+var_168]
0x18002f319  movzx   ecx, byte ptr [rdx+10h]
0x18002f31d  test    cl, cl
0x18002f31f  jnz     short loc_18002F32B
0x18002f321  cmp     [r13+28h], cl
0x18002f325  jz      loc_18002F474
0x18002f32b  xorps   xmm0, xmm0
0x18002f32e  xor     eax, eax
0x18002f330  movups  [rsp+228h+var_1A8], xmm0
0x18002f338  mov     qword ptr [rsp+228h+var_198], rax
0x18002f340  lea     rax, [rsp+228h+var_160]
0x18002f348  mov     [rsp+228h+var_168], rax
0x18002f350  mov     [rsp+228h+var_150], 0
0x18002f358  cmp     byte ptr [rsi+28h], 0
0x18002f35c  jz      short loc_18002F398
0x18002f35e  movdqu  [rsp+228h+var_160], xmm0
0x18002f367  mov     rax, [rsi+20h]
0x18002f36b  test    rax, rax
0x18002f36e  jz      short loc_18002F378
0x18002f370  lock inc dword ptr [rax+8]
0x18002f374  movzx   ecx, byte ptr [rdx+10h]
0x18002f378  mov     rax, [rsi+18h]
0x18002f37c  mov     qword ptr [rsp+228h+var_160], rax
0x18002f384  mov     rax, [rsi+20h]
0x18002f388  mov     qword ptr [rsp+228h+var_160+8], rax
0x18002f390  mov     [rsp+228h+var_150], 1
0x18002f398  lea     rax, [rsp+228h+var_D8]
0x18002f3a0  mov     [rsp+228h+var_1B8], rax
0x18002f3a5  mov     [rsp+228h+var_C8], 0
0x18002f3ad  test    cl, cl
0x18002f3af  jz      short loc_18002F3E6
  ... truncated ...
```
