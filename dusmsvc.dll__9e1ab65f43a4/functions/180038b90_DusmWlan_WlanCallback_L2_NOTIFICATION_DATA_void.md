# DusmWlan::WlanCallback(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x180038b90`
- end: `0x180038ed3`
- name: `?WlanCallback@DusmWlan@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `835`
- prototype: `void __stdcall(PWLAN_NOTIFICATION_DATA, PVOID)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004298`
- `0x1800062a0`
- `0x18000e828`
- `0x180013114`
- `0x180013444`
- `0x18001bf4c`
- `0x18001db50`
- `0x18002f510`
- `0x18003683c`
- `0x180038b90`

## string_xrefs

- `0x180038da3`: `wlan_notification_acm_connection_complete`

## pseudocode

```c
void __fastcall DusmWlan::WlanCallback(PWLAN_NOTIFICATION_DATA a1, PVOID a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 (__fastcall **v10)(); // rax
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  _DWORD *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  _DWORD *pData; // r14
  _DWORD *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  wil *v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  int v30; // ebx
  __int64 v31; // rcx
  int v32; // edi
  _DWORD *v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  wil *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  int v39; // edi
  const wil::ResultException *v40; // rbx
  _DWORD *v41; // r8
  __int64 v42; // r9
  __m256i v43; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v44; // [rsp+70h] [rbp-B8h]
  __int64 v45; // [rsp+78h] [rbp-B0h]
  __m256i *v46; // [rsp+88h] [rbp-A0h]
  const WCHAR *v47; // [rsp+90h] [rbp-98h] BYREF
  const wchar_t *v48; // [rsp+98h] [rbp-90h] BYREF
  const wil::ResultException *v49; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE v50[56]; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v51; // [rsp+E8h] [rbp-40h]
  _BYTE v52[56]; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v53; // [rsp+130h] [rbp+8h] BYREF
  __int64 v54; // [rsp+140h] [rbp+18h] BYREF
  __int64 p_InterfaceGuid; // [rsp+148h] [rbp+20h] BYREF

  if ( !a1 || a1->NotificationSource != 8 )
    return;
  v3 = a1->NotificationCode - 10;
  if ( !(_DWORD)v3 )
  {
    pData = a1->pData;
    v22 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v3, a2) + 8);
    if ( *v22 > 5u )
    {
      v53 = (__int64)"wlan_notification_acm_connection_complete";
      v54 = (__int64)(pData + 1);
      p_InterfaceGuid = (__int64)&a1->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        (int)v22,
        (int)&unk_180059EB8,
        v23,
        v24,
        &p_InterfaceGuid,
        (const WCHAR **)&v54,
        (const wchar_t **)&v53);
    }
    if ( pData && !pData[140] )
    {
      try
      {
        v25 = std::wstring::wstring((__int64)v52, (__int64)(pData + 1));
        *(GUID *)v43.m256i_i8 = a1->InterfaceGuid;
        *(_OWORD *)&v43.m256i_u64[2] = 0;
        *(_OWORD *)&v43.m256i_u64[2] = *(_OWORD *)v25;
        v44 = *(_QWORD *)(v25 + 16);
        v45 = *(_QWORD *)(v25 + 24);
        *(_WORD *)v25 = 0;
        *(_QWORD *)(v25 + 16) = 0;
        *(_QWORD *)(v25 + 24) = 7;
        v51 = 0;
        v51 = std::_Func_impl_no_alloc__DusmWlan::WlanCallback_::_36_::_lambda_3__void_::_Func_impl_no_alloc__DusmWlan::WlanCallback_::_36_::_lambda_3__void___DusmWlan::WlanCallback_::_36_::_lambda_3__0_(
                v50,
                &v43);
        DusmAsync::SubmitOrderedWork((__int64)v50);
        std::function<long (void)>::~function<long (void)>((__int64)v50, v26);
        std::wstring::_Tidy_deallocate(&v43.m256i_u64[2]);
        std::wstring::_Tidy_deallocate(v52);
      }
      catch ( const wil::ResultException *v49 )
      {
        if ( (wil::ResultFromCaughtException(v27) & 0x1FFF0000) == 0x70000 )
          v39 = (unsigned __int16)wil::ResultFromCaughtException(v36);
        else
          v39 = wil::ResultFromCaughtException(v36);
        v40 = v49;
        v41 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v38, v37) + 8);
        if ( *v41 > 5u )
        {
          v47 = (const WCHAR *)*((_QWORD *)v40 + 6);
          LODWORD(v53) = *((_DWORD *)v40 + 22);
          v48 = (const wchar_t *)*((_QWORD *)v40 + 10);
          LODWORD(v54) = *((_DWORD *)v40 + 8);
          LODWORD(p_InterfaceGuid) = v39;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            (int)v41,
            (int)&byte_180059E1B,
            (__int64)v41,
            v42,
            (__int64)&p_InterfaceGuid,
            (__int64)&v54,
            &v48,
            (__int64)&v53,
            &v47);
        }
        return;
      }
      catch ( ... )
      {
        v28 = wil::ResultFromCaughtException(v27);
        v30 = v28;
        v31 = v28 & 0x1FFF0000;
        v32 = (unsigned __int16)v28;
        if ( (_DWORD)v31 != 458752 )
          v32 = v28;
        v33 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v31, v29) + 8);
        if ( *v33 > 5u )
        {
          LODWORD(v53) = v30;
          LODWORD(v54) = v32;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (int)v33,
            (int)word_180059D42,
            v34,
            v35,
            (__int64)&v54,
            (__int64)&v53);
        }
        return;
      }
    }
    return;
  }
  v4 = (unsigned int)(v3 - 3);
  if ( !(_DWORD)v4 )
  {
    v18 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v4, a2) + 8);
    if ( *v18 > 5u )
    {
      v53 = (__int64)"wlan_notification_acm_interface_arrival";
      v54 = (__int64)&a1->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        (int)v18,
        (int)&word_180059F1E,
        v19,
        v20,
        &v54,
        (const wchar_t **)&v53);
    }
    v10 = off_18004CC48;
    goto LABEL_11;
  }
  v5 = (unsigned int)(v4 - 1);
  if ( !(_DWORD)v5 )
  {
    v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v5, a2) + 8);
    if ( *v15 > 5u )
    {
      v53 = (__int64)"wlan_notification_acm_interface_removal";
      v54 = (__int64)&a1->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        (int)v15,
        (int)&byte_180059F77,
        v16,
        v17,
        &v54,
        (const wchar_t **)&v53);
    }
    v10 = off_18004CBE8;
LABEL_11:
    v43.m256i_i64[0] = (__int64)v10;
    *(GUID *)&v43.m256i_u64[1] = a1->InterfaceGuid;
    v46 = &v43;
    DusmAsync::SubmitOrderedWork((__int64)&v43);
    std::function<long (void)>::~function<long (void)>((__int64)&v43, v11);
    return;
  }
  v6 = (unsigned int)(v5 - 1);
  if ( (_DWORD)v6 )
  {
    if ( (_DWORD)v6 != 6 )
      return;
    v7 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v6, a2) + 8);
    if ( *v7 > 5u )
    {
      v53 = (__int64)"wlan_notification_acm_disconnected";
      v54 = (__int64)&a1->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        (int)v7,
        (int)&byte_180059DBF,
        v8,
        v9,
        &v54,
        (const wchar_t **)&v53);
    }
    v10 = off_18004CBB8;
    goto LABEL_11;
  }
  v12 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v6, a2) + 8);
  if ( *v12 > 5u )
  {
    v53 = (__int64)"wlan_notification_acm_profile_change";
    v54 = (__int64)&a1->InterfaceGuid;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      (int)v12,
      (int)byte_180059E61,
      v13,
      v14,
      &v54,
      (const wchar_t **)&v53);
  }
  DusmCache::FlushCostCache();
}

```

## disassembly

```asm
0x180038b90  mov     [rsp+arg_8], rbx
0x180038b95  push    rsi
0x180038b96  push    rdi
0x180038b97  push    r14
0x180038b99  sub     rsp, 110h
0x180038ba0  mov     rbx, rcx
0x180038ba3  test    rcx, rcx
0x180038ba6  jz      loc_180038EBD
0x180038bac  mov     edi, 8
0x180038bb1  cmp     [rcx], edi
0x180038bb3  jnz     loc_180038EBD
0x180038bb9  mov     ecx, [rcx+4]
0x180038bbc  sub     ecx, 0Ah
0x180038bbf  jz      loc_180038D8B
0x180038bc5  sub     ecx, 3
0x180038bc8  jz      loc_180038D2E
0x180038bce  sub     ecx, 1
0x180038bd1  jz      loc_180038CD1
0x180038bd7  sub     ecx, 1
0x180038bda  jz      loc_180038C76
0x180038be0  cmp     ecx, 6
0x180038be3  jnz     loc_180038EBD
0x180038be9  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180038bee  mov     rcx, [rax+8]; int
0x180038bf2  mov     eax, [rcx]
0x180038bf4  cmp     eax, 5
0x180038bf7  jbe     short loc_180038C3A
0x180038bf9  lea     rax, aWlanNotificati_1; "wlan_notification_acm_disconnected"
0x180038c00  mov     [rsp+128h+arg_0], rax
0x180038c08  lea     rax, [rbx+8]
0x180038c0c  mov     [rsp+128h+arg_10], rax
0x180038c14  lea     rax, [rsp+128h+arg_0]
0x180038c1c  mov     [rsp+128h+var_100], rax; __int64
0x180038c21  lea     rax, [rsp+128h+arg_10]
0x180038c29  mov     [rsp+128h+var_108], rax; __int64
0x180038c2e  lea     rdx, byte_180059DBF
0x180038c35  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180038c3a  lea     rax, off_18004CBB8
0x180038c41  mov     qword ptr [rsp+128h+var_D8], rax
0x180038c46  movups  xmm0, xmmword ptr [rbx+rdi]
0x180038c4a  movdqu  [rsp+128h+var_D8+8], xmm0
0x180038c50  lea     rax, [rsp+128h+var_D8]
0x180038c55  mov     [rsp+128h+var_A0], rax
0x180038c5d  lea     rcx, [rsp+128h+var_D8]
0x180038c62  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x180038c67  lea     rcx, [rsp+128h+var_D8]
0x180038c6c  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180038c71  jmp     loc_180038EBD
0x180038c76  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180038c7b  mov     rcx, [rax+8]; int
0x180038c7f  mov     eax, [rcx]
0x180038c81  cmp     eax, 5
0x180038c84  jbe     short loc_180038CC7
0x180038c86  lea     rax, aWlanNotificati_3; "wlan_notification_acm_profile_change"
0x180038c8d  mov     [rsp+128h+arg_0], rax
0x180038c95  lea     rax, [rbx+8]
0x180038c99  mov     [rsp+128h+arg_10], rax
0x180038ca1  lea     rax, [rsp+128h+arg_0]
0x180038ca9  mov     [rsp+128h+var_100], rax; __int64
0x180038cae  lea     rax, [rsp+128h+arg_10]
0x180038cb6  mov     [rsp+128h+var_108], rax; __int64
0x180038cbb  lea     rdx, byte_180059E61
0x180038cc2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180038cc7  call    ?FlushCostCache@DusmCache@@SAXXZ; DusmCache::FlushCostCache(void)
0x180038ccc  jmp     loc_180038EBD
0x180038cd1  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180038cd6  mov     rcx, [rax+8]; int
0x180038cda  mov     eax, [rcx]
0x180038cdc  cmp     eax, 5
0x180038cdf  jbe     short loc_180038D22
0x180038ce1  lea     rax, aWlanNotificati_0; "wlan_notification_acm_interface_removal"
0x180038ce8  mov     [rsp+128h+arg_0], rax
0x180038cf0  lea     rax, [rbx+8]
0x180038cf4  mov     [rsp+128h+arg_10], rax
0x180038cfc  lea     rax, [rsp+128h+arg_0]
0x180038d04  mov     [rsp+128h+var_100], rax; __int64
0x180038d09  lea     rax, [rsp+128h+arg_10]
0x180038d11  mov     [rsp+128h+var_108], rax; __int64
0x180038d16  lea     rdx, byte_180059F77
0x180038d1d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180038d22  lea     rax, off_18004CBE8
0x180038d29  jmp     loc_180038C41
0x180038d2e  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180038d33  mov     rcx, [rax+8]; int
0x180038d37  mov     eax, [rcx]
0x180038d39  cmp     eax, 5
0x180038d3c  jbe     short loc_180038D7F
0x180038d3e  lea     rax, aWlanNotificati; "wlan_notification_acm_interface_arrival"
0x180038d45  mov     [rsp+128h+arg_0], rax
0x180038d4d  lea     rax, [rbx+8]
0x180038d51  mov     [rsp+128h+arg_10], rax
0x180038d59  lea     rax, [rsp+128h+arg_0]
0x180038d61  mov     [rsp+128h+var_100], rax; __int64
0x180038d66  lea     rax, [rsp+128h+arg_10]
0x180038d6e  mov     [rsp+128h+var_108], rax; __int64
0x180038d73  lea     rdx, word_180059F1E
0x180038d7a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180038d7f  lea     rax, off_18004CC48
0x180038d86  jmp     loc_180038C41
0x180038d8b  mov     r14, [rbx+20h]
0x180038d8f  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180038d94  mov     rcx, [rax+8]; int
0x180038d98  mov     eax, [rcx]
0x180038d9a  lea     rsi, [r14+4]
0x180038d9e  cmp     eax, 5
0x180038da1  jbe     short loc_180038DF9
0x180038da3  lea     rax, aWlanNotificati_2; "wlan_notification_acm_connection_comple"...
0x180038daa  mov     [rsp+128h+arg_0], rax
0x180038db2  mov     [rsp+128h+arg_10], rsi
0x180038dba  lea     rax, [rbx+8]
0x180038dbe  mov     [rsp+128h+arg_18], rax
0x180038dc6  lea     rax, [rsp+128h+arg_0]
0x180038dce  mov     [rsp+128h+var_F8], rax; __int64
0x180038dd3  lea     rax, [rsp+128h+arg_10]
0x180038ddb  mov     [rsp+128h+var_100], rax; __int64
0x180038de0  lea     rax, [rsp+128h+arg_18]
0x180038de8  mov     [rsp+128h+var_108], rax; __int64
0x180038ded  lea     rdx, unk_180059EB8; int
0x180038df4  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x180038df9  test    r14, r14
0x180038dfc  jz      loc_180038EBD
0x180038e02  cmp     dword ptr [r14+230h], 0
0x180038e0a  jnz     loc_180038EBD
0x180038e10  mov     rdx, rsi
0x180038e13  lea     rcx, [rsp+128h+var_38]
0x180038e1b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180038e20  mov     rdx, rax
0x180038e23  movups  xmm0, xmmword ptr [rbx+rdi]
0x180038e27  movdqu  [rsp+128h+var_D8], xmm0
0x180038e2d  xorps   xmm1, xmm1
0x180038e30  movups  [rsp+128h+var_C8], xmm1
0x180038e35  mov     rcx, [rax]
0x180038e38  mov     qword ptr [rsp+128h+var_C8], rcx
0x180038e3d  mov     rcx, [rax+8]
0x180038e41  mov     qword ptr [rsp+128h+var_C8+8], rcx
0x180038e46  mov     rax, [rax+10h]
0x180038e4a  mov     [rsp+128h+var_B8], rax
0x180038e4f  mov     rax, [rdx+18h]
0x180038e53  mov     [rsp+128h+var_B0], rax
0x180038e58  xor     eax, eax
0x180038e5a  mov     [rdx], ax
0x180038e5d  mov     [rdx+10h], rax
0x180038e61  mov     qword ptr [rdx+18h], 7
0x180038e69  mov     [rsp+128h+var_40], rax
0x180038e71  lea     rdx, [rsp+128h+var_D8]
0x180038e76  lea     rcx, [rsp+128h+var_78]
0x180038e7e  call    std___Func_impl_no_alloc__DusmWlan__WlanCallback____36____lambda_3__void____Func_impl_no_alloc__DusmWlan__WlanCallback____36____lambda_3__void___DusmWlan__WlanCallback____36____lambda_3__0_
0x180038e83  mov     [rsp+128h+var_40], rax
0x180038e8b  lea     rcx, [rsp+128h+var_78]
0x180038e93  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x180038e98  lea     rcx, [rsp+128h+var_78]
0x180038ea0  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180038ea5  lea     rcx, [rsp+128h+var_C8]
0x180038eaa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038eaf  lea     rcx, [rsp+128h+var_38]
0x180038eb7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038ebc  nop
0x180038ebd  mov     rbx, [rsp+128h+arg_8]
0x180038ec5  add     rsp, 110h
0x180038ecc  pop     r14
0x180038ece  pop     rdi
0x180038ecf  pop     rsi
0x180038ed0  retn
0x180038ed1  jmp     short loc_180038EBD
```
