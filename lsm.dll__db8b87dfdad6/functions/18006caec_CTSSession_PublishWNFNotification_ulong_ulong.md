# CTSSession::PublishWNFNotification(ulong,ulong)

- ea: `0x18006caec`
- end: `0x18006cd8a`
- name: `?PublishWNFNotification@CTSSession@@AEAAXKK@Z`
- size: `670`
- prototype: `void __fastcall(CTSSession *__hidden this, unsigned int, unsigned int)`
- caller_count: `11`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032424`
- `0x1800332b0`
- `0x18006731c`
- `0x18006a6d0`
- `0x18006aaa0`
- `0x18006b480`
- `0x18006bc3c`
- `0x18006beac`
- `0x18006c4b0`
- `0x18006c810`
- `0x18006e6a0`

## callees

- `0x1800074c0`
- `0x180010fb0`
- `0x18001ce00`
- `0x180025070`
- `0x18002cee4`
- `0x180048504`
- `0x18004bf44`
- `0x180055764`
- `0x1800564d0`
- `0x1800652c0`
- `0x18006572c`
- `0x180065778`
- `0x18006caec`
- `0x18006f284`
- `0x18006f41c`
- `0x18006f7e4`
- `0x180094058`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18006cca3`
- `ntdll!RtlPublishWnfStateData` at `0x18006cca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cd58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cd58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006cb5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006cb5f`

## string_xrefs

- `0x18006cb8a`: `CoTaskMemAlloc failed: 0x%x in %s`

## pseudocode

```c
void __fastcall CTSSession::PublishWNFNotification(CTSSession *this, unsigned int a2, unsigned int a3)
{
  __int64 v5; // rbx
  char *v6; // rax
  __int64 v7; // rcx
  char *v8; // rdi
  int v9; // eax
  unsigned int v10; // esi
  const char *v11; // rdx
  const char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  char *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // esi
  const char *v21; // rdx
  const char *v22; // rax
  int v23; // [rsp+20h] [rbp-60h]
  _BYTE v24[16]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v25[56]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v26; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v28; // [rsp+B0h] [rbp+30h] BYREF
  char v29; // [rsp+B8h] [rbp+38h] BYREF
  const char *v30; // [rsp+C8h] [rbp+48h] BYREF

  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v24, (CTSSession *)((char *)this + 1856));
  v28 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::start_and_watch_errors(
    &v28,
    v25);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>(&v28);
  v5 = v26;
  v28 = v26;
  if ( v26 )
    _InterlockedIncrement((volatile signed __int32 *)(v26 + 272));
  tip2::test_watcher<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::~test_watcher<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>(v25);
  v29 = 0;
  v6 = (char *)CoTaskMemAlloc(0x1000u);
  v8 = v6;
  v30 = v6;
  if ( v6 )
    memset_0(v6, 0, 0x1000u);
  if ( v8 )
  {
    v9 = wil::wnf_query_nothrow<_RDP_SESSION_STATE_LIST>(v7, &v29, v8);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v13 = *(unsigned int *)v8;
      if ( (unsigned int)v13 < 0x155 )
      {
        if ( v29 )
        {
          v16 = 3 * v13;
          *(_DWORD *)&v8[4 * v16 + 4] = a3;
          *(_DWORD *)&v8[4 * v16 + 8] = a2;
          *(_DWORD *)&v8[4 * v16 + 12] = *(_DWORD *)&v8[12 * (unsigned int)(v13 - 1) + 12] + 1;
          ++*(_DWORD *)v8;
        }
        else
        {
          v14 = 4096;
          v15 = v8;
          do
          {
            *v15++ = 0;
            --v14;
          }
          while ( v14 );
          *(_DWORD *)v8 = 1;
          *((_DWORD *)v8 + 1) = a3;
          *((_DWORD *)v8 + 2) = a2;
          *((_DWORD *)v8 + 3) = 1;
        }
      }
      else
      {
        memmove_0(v8 + 4, v8 + 16, 0xFF0u);
        *((_DWORD *)v8 + 1021) = a3;
        *((_DWORD *)v8 + 1022) = a2;
        *((_DWORD *)v8 + 1023) = *((_DWORD *)v8 + 1020) + 1;
        *(_DWORD *)v8 = 341;
      }
      v17 = RtlPublishWnfStateData(WNF_RDP_ALL_SESSIONS_STATE, 0, v8, 4096);
      v20 = v17 | 0x10000000;
      if ( v17 >= 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          v30 = "Successfully published WTS event via WNF";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (_DWORD)retaddr,
            (unsigned int)&dword_1800C3904,
            v18,
            v19,
            (__int64)&v30);
        }
        if ( v5 )
        {
          wil::EnterCriticalSection(&v30, v5 + 200);
          tip2::details::shared_data<0,0,0>::complete_helper(v5 + 8, 0, 2);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1F6A,
          (unsigned int)"clientcore\\termsrv\\newsvc\\core\\tssession.cpp",
          (const char *)v20,
          0);
        v22 = tip2::details::reason_string(
                (tip2::details *)"WTSNotificationsViaWNFTipTest::reason::wnf_publish_nothrow_failed",
                v21);
        tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::complete_and_fail(
          &v28,
          1,
          v22);
        _DbgPrintMessage(8, "wnf_publish_nothrow failed: 0x%x in %s", v20, "CTSSession::PublishWNFNotification");
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F40,
        (unsigned int)"clientcore\\termsrv\\newsvc\\core\\tssession.cpp",
        (const char *)(unsigned int)v9,
        v23);
      v12 = tip2::details::reason_string(
              (tip2::details *)"WTSNotificationsViaWNFTipTest::reason::wnf_query_nothrow_failed",
              v11);
      tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::complete_and_fail(
        &v28,
        0,
        v12);
      _DbgPrintMessage(8, "wnf_query_nothrow failed: 0x%x in %s", v10, "CTSSession::PublishWNFNotification");
    }
  }
  else
  {
    _DbgPrintMessage(8, "CoTaskMemAlloc failed: 0x%x in %s", 2147942414LL, "CTSSession::PublishWNFNotification");
  }
  if ( v8 )
    CoTaskMemFree(v8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>(&v28);
  CAutoLock::Unlock((CAutoLock *)v24);
}

```

## disassembly

```asm
0x18006caec  mov     [rsp-28h+arg_10], rbx
0x18006caf1  push    rbp
0x18006caf2  push    rsi
0x18006caf3  push    rdi
0x18006caf4  push    r14
0x18006caf6  push    r15
0x18006caf8  mov     rbp, rsp
0x18006cafb  sub     rsp, 80h
0x18006cb02  mov     r14d, r8d
0x18006cb05  mov     r15d, edx
0x18006cb08  lea     rdx, [rcx+740h]; struct CResource *
0x18006cb0f  lea     rcx, [rbp+var_50]; this
0x18006cb13  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006cb18  nop
0x18006cb19  mov     [rbp+arg_0], 0
0x18006cb21  lea     rdx, [rbp+var_40]
0x18006cb25  lea     rcx, [rbp+arg_0]
0x18006cb29  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::start_and_watch_errors(void)
0x18006cb2e  lea     rcx, [rbp+arg_0]
0x18006cb32  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>(void)
0x18006cb37  mov     rbx, [rbp+var_8]
0x18006cb3b  mov     [rbp+arg_0], rbx
0x18006cb3f  test    rbx, rbx
0x18006cb42  jz      short loc_18006CB4B
0x18006cb44  lock inc dword ptr [rbx+110h]
0x18006cb4b  lea     rcx, [rbp+var_40]
0x18006cb4f  call    ??1?$test_watcher@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::~test_watcher<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>(void)
0x18006cb54  mov     [rbp+arg_8], 0
0x18006cb58  mov     esi, 1000h
0x18006cb5d  mov     ecx, esi; cb
0x18006cb5f  call    cs:__imp_CoTaskMemAlloc
0x18006cb65  mov     rdi, rax
0x18006cb68  mov     [rbp+arg_18], rax
0x18006cb6c  test    rax, rax
0x18006cb6f  jz      short loc_18006CB7F
0x18006cb71  mov     r8d, esi; Size
0x18006cb74  xor     edx, edx; Val
0x18006cb76  mov     rcx, rax; void *
0x18006cb79  call    memset_0
0x18006cb7e  nop
0x18006cb7f  test    rdi, rdi
0x18006cb82  jnz     short loc_18006CBA7
0x18006cb84  mov     r8d, 8007000Eh
0x18006cb8a  lea     rdx, aCotaskmemalloc; "CoTaskMemAlloc failed: 0x%x in %s"
0x18006cb91  lea     r9, aCtssessionPubl; "CTSSession::PublishWNFNotification"
0x18006cb98  mov     ecx, 8; int
0x18006cb9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006cba2  jmp     loc_18006CD50
0x18006cba7  mov     r8, rdi
0x18006cbaa  lea     rdx, [rbp+arg_8]
0x18006cbae  call    ??$wnf_query_nothrow@U_RDP_SESSION_STATE_LIST@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAU_RDP_SESSION_STATE_LIST@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<_RDP_SESSION_STATE_LIST>(_WNF_STATE_NAME const &,bool *,_RDP_SESSION_STATE_LIST *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18006cbb3  mov     esi, eax
0x18006cbb5  mov     rcx, [rbp+28h]; this
0x18006cbb9  test    eax, eax
0x18006cbbb  jns     short loc_18006CBF7
0x18006cbbd  mov     r9d, eax; char *
0x18006cbc0  lea     r8, aClientcoreTerm_5; "clientcore\\termsrv\\newsvc\\core\\tsse"...
0x18006cbc7  mov     edx, 1F40h; void *
0x18006cbcc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006cbd1  lea     rcx, aWtsnotificatio_0; "WTSNotificationsViaWNFTipTest::reason::"...
0x18006cbd8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18006cbdd  mov     r8, rax
0x18006cbe0  xor     edx, edx
0x18006cbe2  lea     rcx, [rbp+arg_0]
0x18006cbe6  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::complete_and_fail(ushort,char const *)
0x18006cbeb  mov     r8d, esi
0x18006cbee  lea     rdx, aWnfQueryNothro; "wnf_query_nothrow failed: 0x%x in %s"
0x18006cbf5  jmp     short loc_18006CB91
0x18006cbf7  mov     ecx, [rdi]
0x18006cbf9  mov     esi, 155h
0x18006cbfe  cmp     ecx, esi
0x18006cc00  jb      short loc_18006CC35
0x18006cc02  lea     rdx, [rdi+10h]; Src
0x18006cc06  lea     rcx, [rdi+4]; void *
0x18006cc0a  mov     r8d, 0FF0h; Size
0x18006cc10  call    memmove_0
0x18006cc15  mov     [rdi+0FF4h], r14d
0x18006cc1c  mov     [rdi+0FF8h], r15d
0x18006cc23  mov     eax, [rdi+0FF0h]
0x18006cc29  inc     eax
0x18006cc2b  mov     [rdi+0FFCh], eax
0x18006cc31  mov     [rdi], esi
0x18006cc33  jmp     short loc_18006CC88
0x18006cc35  cmp     [rbp+arg_8], 0
0x18006cc39  jnz     short loc_18006CC66
0x18006cc3b  mov     ecx, 1000h
0x18006cc40  mov     rax, rdi
0x18006cc43  mov     byte ptr [rax], 0
0x18006cc46  inc     rax
0x18006cc49  sub     rcx, 1
0x18006cc4d  jnz     short loc_18006CC43
0x18006cc4f  mov     dword ptr [rdi], 1
0x18006cc55  mov     [rdi+4], r14d
0x18006cc59  mov     [rdi+8], r15d
0x18006cc5d  mov     dword ptr [rdi+0Ch], 1
0x18006cc64  jmp     short loc_18006CC88
0x18006cc66  lea     rdx, [rcx+rcx*2]
0x18006cc6a  mov     [rdi+rdx*4+4], r14d
0x18006cc6f  mov     [rdi+rdx*4+8], r15d
0x18006cc74  dec     ecx
0x18006cc76  inc     rcx
0x18006cc79  lea     rax, [rcx+rcx*2]
0x18006cc7d  mov     ecx, [rdi+rax*4]
0x18006cc80  inc     ecx
0x18006cc82  mov     [rdi+rdx*4+0Ch], ecx
0x18006cc86  inc     dword ptr [rdi]
0x18006cc88  mov     qword ptr [rsp+80h+var_60], 0; int
0x18006cc91  mov     r9d, 1000h
0x18006cc97  mov     r8, rdi
0x18006cc9a  xor     edx, edx
0x18006cc9c  mov     rcx, cs:WNF_RDP_ALL_SESSIONS_STATE
0x18006cca3  call    cs:__imp_RtlPublishWnfStateData
0x18006cca9  mov     esi, eax
0x18006ccab  or      esi, 10000000h
0x18006ccb1  mov     rcx, [rbp+28h]; this
0x18006ccb5  jge     short loc_18006CCF7
0x18006ccb7  mov     r9d, esi; char *
0x18006ccba  lea     r8, aClientcoreTerm_5; "clientcore\\termsrv\\newsvc\\core\\tsse"...
0x18006ccc1  mov     edx, 1F6Ah; void *
0x18006ccc6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006cccb  lea     rcx, aWtsnotificatio_1; "WTSNotificationsViaWNFTipTest::reason::"...
0x18006ccd2  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18006ccd7  mov     r8, rax
0x18006ccda  mov     edx, 1
0x18006ccdf  lea     rcx, [rbp+arg_0]
0x18006cce3  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::complete_and_fail(ushort,char const *)
0x18006cce8  mov     r8d, esi
0x18006cceb  lea     rdx, aWnfPublishNoth; "wnf_publish_nothrow failed: 0x%x in %s"
0x18006ccf2  jmp     loc_18006CB91
0x18006ccf7  mov     eax, cs:dword_1800DA020
0x18006ccfd  cmp     eax, 4
0x18006cd00  jbe     short loc_18006CD22
0x18006cd02  lea     rax, aSuccessfullyPu; "Successfully published WTS event via WN"...
0x18006cd09  mov     [rbp+arg_18], rax
0x18006cd0d  lea     rax, [rbp+arg_18]
0x18006cd11  mov     qword ptr [rsp+80h+var_60], rax
0x18006cd16  lea     rdx, dword_1800C3904
0x18006cd1d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006cd22  test    rbx, rbx
0x18006cd25  jz      short loc_18006CD50
0x18006cd27  lea     rdx, [rbx+0C8h]
0x18006cd2e  lea     rcx, [rbp+arg_18]
0x18006cd32  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18006cd37  xor     edx, edx
0x18006cd39  lea     r8d, [rdx+2]
0x18006cd3d  lea     rcx, [rbx+8]
0x18006cd41  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x18006cd46  lea     rcx, [rbp+arg_18]
0x18006cd4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18006cd4f  nop
0x18006cd50  test    rdi, rdi
0x18006cd53  jz      short loc_18006CD5F
0x18006cd55  mov     rcx, rdi; pv
0x18006cd58  call    cs:__imp_CoTaskMemFree
0x18006cd5e  nop
0x18006cd5f  lea     rcx, [rbp+arg_0]
0x18006cd63  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>(void)
0x18006cd68  nop
0x18006cd69  lea     rcx, [rbp+var_50]; this
0x18006cd6d  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006cd72  nop
0x18006cd73  mov     rbx, [rsp+80h+arg_10]
0x18006cd7b  add     rsp, 80h
0x18006cd82  pop     r15
0x18006cd84  pop     r14
0x18006cd86  pop     rdi
0x18006cd87  pop     rsi
0x18006cd88  pop     rbp
0x18006cd89  retn
```
