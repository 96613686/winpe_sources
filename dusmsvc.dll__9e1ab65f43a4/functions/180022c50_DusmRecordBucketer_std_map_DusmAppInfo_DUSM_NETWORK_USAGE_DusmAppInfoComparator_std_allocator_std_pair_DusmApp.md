# DusmRecordBucketer<std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,DusmAppInfoExtractor>::DedupUsageFromWnsService(DUSM_NETWORK_USAGE const &)

- ea: `0x180022c50`
- end: `0x180022d89`
- name: `?DedupUsageFromWnsService@?$DusmRecordBucketer@V?$map@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@VDusmAppInfoExtractor@@@@QEAAXAEBUDUSM_NETWORK_USAGE@@@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022d90`

## callees

- `0x180005198`
- `0x180007c90`
- `0x18000e828`
- `0x180013114`
- `0x180013444`
- `0x1800216a4`
- `0x18002178c`
- `0x180022c50`
- `0x180043f48`

## string_xrefs

- `0x180022c75`: `WpnService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DusmRecordBucketer<std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,DusmAppInfoExtractor>::DedupUsageFromWnsService(
        _QWORD *a1,
        __int64 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  __int64 v13; // [rsp+48h] [rbp-31h] BYREF
  __int64 v14; // [rsp+50h] [rbp-29h] BYREF
  __int64 v15; // [rsp+58h] [rbp-21h] BYREF
  __int64 v16; // [rsp+60h] [rbp-19h] BYREF
  __int64 v17; // [rsp+70h] [rbp-9h]
  _BYTE v18[32]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v19; // [rsp+98h] [rbp+1Fh]

  std::wstring::wstring((__int64)v18, (__int64)L"WpnService");
  v19 = 1;
  std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Find_lower_bound<DusmAppInfo>(
    (__int64)a1,
    &v16,
    (__int64)v18);
  v4 = v17;
  if ( !std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Lower_bound_duplicate<DusmAppInfo>(
          v5,
          v17,
          (__int64)v18)
    || v4 == *a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  }
  else
  {
    if ( (unsigned __int64)a2[1] > *(_QWORD *)(v4 + 80) || (unsigned __int64)*a2 > *(_QWORD *)(v4 + 72) )
    {
      v8 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v7, v6) + 8);
      if ( *v8 > 5u )
      {
        v12 = *(_QWORD *)(v4 + 72);
        v13 = *a2;
        v14 = *(_QWORD *)(v4 + 80);
        v15 = a2[1];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (int)v8,
          (int)byte_180057845,
          v9,
          v10,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v13,
          (__int64)&v12);
      }
    }
    *(_QWORD *)(v4 + 80) = (*(_QWORD *)(v4 + 80) - a2[1]) & -(__int64)((unsigned __int64)a2[1] < *(_QWORD *)(v4 + 80));
    *(_QWORD *)(v4 + 72) = (*(_QWORD *)(v4 + 72) - *a2) & -(__int64)((unsigned __int64)*a2 < *(_QWORD *)(v4 + 72));
  }
  return std::wstring::_Tidy_deallocate(v18);
}

```

## disassembly

```asm
0x180022c50  push    rbp
0x180022c52  push    rbx
0x180022c53  push    rsi
0x180022c54  push    rdi
0x180022c55  lea     rbp, [rsp-3Fh]
0x180022c5a  sub     rsp, 0B8h
0x180022c61  mov     rax, cs:__security_cookie
0x180022c68  xor     rax, rsp
0x180022c6b  mov     [rbp+57h+var_30], rax
0x180022c6f  mov     rdi, rdx
0x180022c72  mov     rsi, rcx
0x180022c75  lea     rdx, aWpnservice; "WpnService"
0x180022c7c  lea     rcx, [rbp+57h+var_58]
0x180022c80  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022c85  mov     [rbp+57h+var_38], 1
0x180022c8d  lea     r8, [rbp+57h+var_58]
0x180022c91  lea     rdx, [rbp+57h+var_70]
0x180022c95  mov     rcx, rsi
0x180022c98  call    ??$_Find_lower_bound@UDusmAppInfo@@@?$_Tree@V?$_Tmap_traits@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@1@AEBUDusmAppInfo@@@Z; std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Find_lower_bound<DusmAppInfo>(DusmAppInfo const &)
0x180022c9d  lea     r8, [rbp+57h+var_58]
0x180022ca1  mov     rbx, [rbp+57h+var_60]
0x180022ca5  mov     rdx, rbx
0x180022ca8  call    ??$_Lower_bound_duplicate@UDusmAppInfo@@@?$_Tree@V?$_Tmap_traits@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@PEAX@1@AEBUDusmAppInfo@@@Z; std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Lower_bound_duplicate<DusmAppInfo>(std::_Tree_node<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>,void *> * const,DusmAppInfo const &)
0x180022cad  test    al, al
0x180022caf  jz      loc_180022D62
0x180022cb5  cmp     rbx, [rsi]
0x180022cb8  jz      loc_180022D62
0x180022cbe  mov     rax, [rbx+50h]
0x180022cc2  cmp     [rdi+8], rax
0x180022cc6  ja      short loc_180022CD1
0x180022cc8  mov     rax, [rbx+48h]
0x180022ccc  cmp     [rdi], rax
0x180022ccf  jbe     short loc_180022D30
0x180022cd1  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180022cd6  mov     rcx, [rax+8]
0x180022cda  mov     eax, [rcx]
0x180022cdc  cmp     eax, 5
0x180022cdf  jbe     short loc_180022D30
0x180022ce1  mov     rax, [rbx+48h]
0x180022ce5  mov     [rbp+57h+var_90], rax
0x180022ce9  mov     rax, [rdi]
0x180022cec  mov     [rbp+57h+var_88], rax
0x180022cf0  mov     rax, [rbx+50h]
0x180022cf4  mov     [rbp+57h+var_80], rax
0x180022cf8  mov     rax, [rdi+8]
0x180022cfc  mov     [rbp+57h+var_78], rax
0x180022d00  lea     rax, [rbp+57h+var_90]
0x180022d04  mov     [rsp+0D0h+var_98], rax
0x180022d09  lea     rax, [rbp+57h+var_88]
0x180022d0d  mov     [rsp+0D0h+var_A0], rax
0x180022d12  lea     rax, [rbp+57h+var_80]
0x180022d16  mov     [rsp+0D0h+var_A8], rax
0x180022d1b  lea     rax, [rbp+57h+var_78]
0x180022d1f  mov     [rsp+0D0h+var_B0], rax
0x180022d24  lea     rdx, byte_180057845
0x180022d2b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180022d30  mov     rax, [rbx+50h]
0x180022d34  mov     rcx, rax
0x180022d37  sub     rcx, [rdi+8]
0x180022d3b  cmp     [rdi+8], rax
0x180022d3f  sbb     rax, rax
0x180022d42  and     rax, rcx
0x180022d45  mov     [rbx+50h], rax
0x180022d49  mov     rax, [rbx+48h]
0x180022d4d  mov     rcx, rax
0x180022d50  sub     rcx, [rdi]
0x180022d53  cmp     [rdi], rax
0x180022d56  sbb     rax, rax
0x180022d59  and     rax, rcx
0x180022d5c  mov     [rbx+48h], rax
0x180022d60  jmp     short loc_180022D68
0x180022d62  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022d67  nop
0x180022d68  lea     rcx, [rbp+57h+var_58]
0x180022d6c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d71  mov     rcx, [rbp+57h+var_30]
0x180022d75  xor     rcx, rsp; StackCookie
0x180022d78  call    __security_check_cookie
0x180022d7d  add     rsp, 0B8h
0x180022d84  pop     rdi
0x180022d85  pop     rsi
0x180022d86  pop     rbx
0x180022d87  pop     rbp
0x180022d88  retn
```
