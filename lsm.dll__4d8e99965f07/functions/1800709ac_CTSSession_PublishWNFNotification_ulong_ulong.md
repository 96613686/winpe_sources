# CTSSession::PublishWNFNotification(ulong,ulong)

- ea: `0x1800709ac`
- end: `0x180070c5d`
- name: `?PublishWNFNotification@CTSSession@@AEAAXKK@Z`
- size: `689`
- prototype: `void __fastcall(CTSSession *__hidden this, unsigned int, unsigned int)`
- caller_count: `11`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034508`
- `0x1800353d0`
- `0x18006b024`
- `0x18006e510`
- `0x18006e8f0`
- `0x18006f300`
- `0x18006faec`
- `0x18006fd5c`
- `0x180070360`
- `0x1800706d0`
- `0x180072640`

## callees

- `0x1800077a0`
- `0x1800129d0`
- `0x180014b20`
- `0x18002701c`
- `0x18002ed70`
- `0x18004b720`
- `0x18004f354`
- `0x180058fc8`
- `0x180059d70`
- `0x180068f08`
- `0x180069380`
- `0x1800693d0`
- `0x1800709ac`
- `0x180073268`
- `0x180073408`
- `0x1800737f4`
- `0x1800995a8`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180070b69`
- `ntdll!RtlPublishWnfStateData` at `0x180070b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070a1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070a1f`

## string_xrefs

- `0x180070a50`: `CoTaskMemAlloc failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          v30 = "Successfully published WTS event via WNF";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (_DWORD)retaddr,
            (unsigned int)&dword_1800C8A8C,
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
0x1800709ac  mov     [rsp-28h+arg_10], rbx
0x1800709b1  push    rbp
0x1800709b2  push    rsi
0x1800709b3  push    rdi
0x1800709b4  push    r14
0x1800709b6  push    r15
0x1800709b8  mov     rbp, rsp
0x1800709bb  sub     rsp, 80h
0x1800709c2  mov     r14d, r8d
0x1800709c5  mov     r15d, edx
0x1800709c8  lea     rdx, [rcx+740h]; struct CResource *
0x1800709cf  lea     rcx, [rbp+var_50]; this
0x1800709d3  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800709d8  nop
0x1800709d9  mov     [rbp+arg_0], 0
0x1800709e1  lea     rdx, [rbp+var_40]
0x1800709e5  lea     rcx, [rbp+arg_0]
0x1800709e9  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::start_and_watch_errors(void)
0x1800709ee  lea     rcx, [rbp+arg_0]
0x1800709f2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>(void)
0x1800709f7  mov     rbx, [rbp+var_8]
0x1800709fb  mov     [rbp+arg_0], rbx
0x1800709ff  test    rbx, rbx
0x180070a02  jz      short loc_180070A0B
0x180070a04  lock inc dword ptr [rbx+110h]
0x180070a0b  lea     rcx, [rbp+var_40]
0x180070a0f  call    ??1?$test_watcher@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::~test_watcher<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>(void)
0x180070a14  mov     [rbp+arg_8], 0
0x180070a18  mov     esi, 1000h
0x180070a1d  mov     ecx, esi; cb
0x180070a1f  call    cs:__imp_CoTaskMemAlloc
0x180070a26  nop     dword ptr [rax+rax+00h]
0x180070a2b  mov     rdi, rax
0x180070a2e  mov     [rbp+arg_18], rax
0x180070a32  test    rax, rax
0x180070a35  jz      short loc_180070A45
0x180070a37  mov     r8d, esi; Size
0x180070a3a  xor     edx, edx; Val
0x180070a3c  mov     rcx, rax; void *
0x180070a3f  call    memset_0
0x180070a44  nop
0x180070a45  test    rdi, rdi
0x180070a48  jnz     short loc_180070A6D
0x180070a4a  mov     r8d, 8007000Eh
0x180070a50  lea     rdx, aCotaskmemalloc; "CoTaskMemAlloc failed: 0x%x in %s"
0x180070a57  lea     r9, aCtssessionPubl; "CTSSession::PublishWNFNotification"
0x180070a5e  mov     ecx, 8; int
0x180070a63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180070a68  jmp     loc_180070C1C
0x180070a6d  mov     r8, rdi
0x180070a70  lea     rdx, [rbp+arg_8]
0x180070a74  call    ??$wnf_query_nothrow@U_RDP_SESSION_STATE_LIST@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAU_RDP_SESSION_STATE_LIST@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<_RDP_SESSION_STATE_LIST>(_WNF_STATE_NAME const &,bool *,_RDP_SESSION_STATE_LIST *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180070a79  mov     esi, eax
0x180070a7b  mov     rcx, [rbp+28h]; this
0x180070a7f  test    eax, eax
0x180070a81  jns     short loc_180070ABD
0x180070a83  mov     r9d, eax; char *
0x180070a86  lea     r8, aClientcoreTerm_5; "clientcore\\termsrv\\newsvc\\core\\tsse"...
0x180070a8d  mov     edx, 1F40h; void *
0x180070a92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070a97  lea     rcx, aWtsnotificatio_0; "WTSNotificationsViaWNFTipTest::reason::"...
0x180070a9e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180070aa3  mov     r8, rax
0x180070aa6  xor     edx, edx
0x180070aa8  lea     rcx, [rbp+arg_0]
0x180070aac  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::complete_and_fail(ushort,char const *)
0x180070ab1  mov     r8d, esi
0x180070ab4  lea     rdx, aWnfQueryNothro; "wnf_query_nothrow failed: 0x%x in %s"
0x180070abb  jmp     short loc_180070A57
0x180070abd  mov     ecx, [rdi]
0x180070abf  mov     esi, 155h
0x180070ac4  cmp     ecx, esi
0x180070ac6  jb      short loc_180070AFB
0x180070ac8  lea     rdx, [rdi+10h]; Src
0x180070acc  lea     rcx, [rdi+4]; void *
0x180070ad0  mov     r8d, 0FF0h; Size
0x180070ad6  call    memmove_0
0x180070adb  mov     [rdi+0FF4h], r14d
0x180070ae2  mov     [rdi+0FF8h], r15d
0x180070ae9  mov     eax, [rdi+0FF0h]
0x180070aef  inc     eax
0x180070af1  mov     [rdi+0FFCh], eax
0x180070af7  mov     [rdi], esi
0x180070af9  jmp     short loc_180070B4E
0x180070afb  cmp     [rbp+arg_8], 0
0x180070aff  jnz     short loc_180070B2C
0x180070b01  mov     ecx, 1000h
0x180070b06  mov     rax, rdi
0x180070b09  mov     byte ptr [rax], 0
0x180070b0c  inc     rax
0x180070b0f  sub     rcx, 1
0x180070b13  jnz     short loc_180070B09
0x180070b15  mov     dword ptr [rdi], 1
0x180070b1b  mov     [rdi+4], r14d
0x180070b1f  mov     [rdi+8], r15d
0x180070b23  mov     dword ptr [rdi+0Ch], 1
0x180070b2a  jmp     short loc_180070B4E
0x180070b2c  lea     rdx, [rcx+rcx*2]
0x180070b30  mov     [rdi+rdx*4+4], r14d
0x180070b35  mov     [rdi+rdx*4+8], r15d
0x180070b3a  dec     ecx
0x180070b3c  inc     rcx
0x180070b3f  lea     rax, [rcx+rcx*2]
0x180070b43  mov     ecx, [rdi+rax*4]
0x180070b46  inc     ecx
0x180070b48  mov     [rdi+rdx*4+0Ch], ecx
0x180070b4c  inc     dword ptr [rdi]
0x180070b4e  mov     qword ptr [rsp+80h+var_60], 0; int
0x180070b57  mov     r9d, 1000h
0x180070b5d  mov     r8, rdi
0x180070b60  xor     edx, edx
0x180070b62  mov     rcx, cs:WNF_RDP_ALL_SESSIONS_STATE
0x180070b69  call    cs:__imp_RtlPublishWnfStateData
0x180070b70  nop     dword ptr [rax+rax+00h]
0x180070b75  mov     esi, eax
0x180070b77  or      esi, 10000000h
0x180070b7d  mov     rcx, [rbp+28h]; this
0x180070b81  jge     short loc_180070BC3
0x180070b83  mov     r9d, esi; char *
0x180070b86  lea     r8, aClientcoreTerm_5; "clientcore\\termsrv\\newsvc\\core\\tsse"...
0x180070b8d  mov     edx, 1F6Ah; void *
0x180070b92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070b97  lea     rcx, aWtsnotificatio_1; "WTSNotificationsViaWNFTipTest::reason::"...
0x180070b9e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180070ba3  mov     r8, rax
0x180070ba6  mov     edx, 1
0x180070bab  lea     rcx, [rbp+arg_0]
0x180070baf  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>>::complete_and_fail(ushort,char const *)
0x180070bb4  mov     r8d, esi
0x180070bb7  lea     rdx, aWnfPublishNoth; "wnf_publish_nothrow failed: 0x%x in %s"
0x180070bbe  jmp     loc_180070A57
0x180070bc3  mov     eax, cs:dword_1800DF020
0x180070bc9  cmp     eax, 4
0x180070bcc  jbe     short loc_180070BEE
0x180070bce  lea     rax, aSuccessfullyPu; "Successfully published WTS event via WN"...
0x180070bd5  mov     [rbp+arg_18], rax
0x180070bd9  lea     rax, [rbp+arg_18]
0x180070bdd  mov     qword ptr [rsp+80h+var_60], rax
0x180070be2  lea     rdx, dword_1800C8A8C
0x180070be9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180070bee  test    rbx, rbx
0x180070bf1  jz      short loc_180070C1C
0x180070bf3  lea     rdx, [rbx+0C8h]
0x180070bfa  lea     rcx, [rbp+arg_18]
0x180070bfe  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070c03  xor     edx, edx
0x180070c05  lea     r8d, [rdx+2]
0x180070c09  lea     rcx, [rbx+8]
0x180070c0d  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x180070c12  lea     rcx, [rbp+arg_18]
0x180070c16  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180070c1b  nop
0x180070c1c  test    rdi, rdi
0x180070c1f  jz      short loc_180070C31
0x180070c21  mov     rcx, rdi; pv
0x180070c24  call    cs:__imp_CoTaskMemFree
0x180070c2b  nop     dword ptr [rax+rax+00h]
0x180070c30  nop
0x180070c31  lea     rcx, [rbp+arg_0]
0x180070c35  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WTSNotificationsViaWNFTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WTSNotificationsViaWNFTipTest,_tip_WTSNotificationsViaWNFTipTest>,wil::err_returncode_policy>(void)
0x180070c3a  nop
0x180070c3b  lea     rcx, [rbp+var_50]; this
0x180070c3f  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180070c44  nop
0x180070c45  mov     rbx, [rsp+80h+arg_10]
0x180070c4d  add     rsp, 80h
0x180070c54  pop     r15
0x180070c56  pop     r14
0x180070c58  pop     rdi
0x180070c59  pop     rsi
0x180070c5a  pop     rbp
0x180070c5b  retn
```
