# LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete(long,_GUID const &,std::deque<std::unique_ptr<LPA::Es10bStoredNotificationStruct,std::default_delete<LPA::Es10bStoredNotificationStruct>>,std::allocator<std::unique_ptr<LPA::Es10bStoredNotificationStruct,std::default_delete<LPA::Es10bStoredNotificationStruct>>>> &,ulong)

- ea: `0x18008d320`
- end: `0x18008d662`
- name: `?OnEs10bRetrieveNotificationsListComplete@EsimManager@LPA@@EEAAXJAEBU_GUID@@AEAV?$deque@V?$unique_ptr@UEs10bStoredNotificationStruct@LPA@@U?$default_delete@UEs10bStoredNotificationStruct@LPA@@@std@@@std@@V?$allocator@V?$unique_ptr@UEs10bStoredNotificationStruct@LPA@@U?$default_delete@UEs10bStoredNotificationStruct@LPA@@@std@@@std@@@2@@std@@K@Z`
- size: `834`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800037f4`
- `0x180004a7c`
- `0x180005268`
- `0x180071564`
- `0x180071840`
- `0x180083fcc`
- `0x1800879f0`
- `0x180088378`
- `0x180088af0`
- `0x180088b48`
- `0x18008aeb4`
- `0x18008c4e0`
- `0x18008d320`
- `0x180092d70`
- `0x180095fd0`
- `0x180096544`
- `0x180097224`
- `0x1800975e0`

## string_xrefs

- `0x18008d372`: `LpaServiceEsimManager`
- `0x18008d423`: `LpaServiceEsimManager`
- `0x18008d52d`: `LpaServiceEsimManager`
- `0x18008d368`: `LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete`
- `0x18008d40e`: `LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete`
- `0x18008d518`: `LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete`

## pseudocode

```c
void __fastcall LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete(
        _QWORD *a1,
        int a2,
        const struct _GUID *a3,
        __int64 a4,
        int a5)
{
  LPA::EsimManager **v5; // rbx
  const struct _GUID *v8; // r13
  int v10; // r8d
  int v11; // r9d
  const char *v12; // rcx
  int v13; // edi
  LPA::EsimManager *v14; // r15
  __int64 v15; // rbx
  __int64 EsimId; // rax
  int v17; // r8d
  int v18; // r9d
  LPA::EsimManager *v19; // rcx
  int v20; // edi
  __int64 v21; // rbx
  _QWORD **v22; // r13
  _QWORD *i; // rdi
  __int64 v24; // rax
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // r14
  const char *v27; // [rsp+50h] [rbp-31h] BYREF
  __int64 v28; // [rsp+58h] [rbp-29h] BYREF
  const char *v29; // [rsp+60h] [rbp-21h] BYREF
  const char *v30; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v31[3]; // [rsp+70h] [rbp-11h] BYREF
  _QWORD v32[2]; // [rsp+88h] [rbp+7h] BYREF
  __int64 v33; // [rsp+98h] [rbp+17h]
  LPA::EsimManager *v34; // [rsp+E0h] [rbp+5Fh] BYREF
  int v35; // [rsp+E8h] [rbp+67h] BYREF
  const struct _GUID *v36; // [rsp+F0h] [rbp+6Fh]

  v36 = a3;
  v5 = (LPA::EsimManager **)(a1 + 29);
  v8 = a3;
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    a1 + 29,
    &v34,
    &a5);
  v12 = "LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete";
  v13 = -1;
  v35 = -1;
  if ( *v5 == v34 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v34) = a5;
      v27 = "LpaServiceEsimManager";
      v30 = (const char *)v8;
      LODWORD(v28) = a2;
      v29 = "LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)"LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete",
        (unsigned int)&unk_18012DC30,
        v10,
        v11,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v34,
        (__int64)&v30);
    }
    v14 = (LPA::EsimManager *)(a1 - 1);
  }
  else
  {
    v14 = (LPA::EsimManager *)(a1 - 1);
    v13 = *(_DWORD *)(*((_QWORD *)v34 + 5) + 224LL);
    v35 = v13;
    LPA::EsimManager::CompleteOperation((LPA::EsimManager *)(a1 - 1));
  }
  if ( a2 < 0 && (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v34) = v13;
    v29 = "LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete";
    v27 = (const char *)v8;
    v30 = "LpaServiceEsimManager";
    LODWORD(v28) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (_DWORD)v12,
      (unsigned int)&dword_18012DBDC,
      v10,
      v11,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v34);
  }
  LPA::EsimManager::TryFindEsimRecordBySlotId(v14, &v28, &v35, v8);
  v15 = v28;
  if ( a1[25] != v28 )
  {
    EsimId = LPA::EsimManager::EsimRecord::GetEsimId(*(_QWORD *)(v28 + 48));
    v34 = (LPA::EsimManager *)EsimId;
    v19 = (LPA::EsimManager *)EsimId;
    if ( a2 >= 0 && EsimId )
    {
      v20 = *(_DWORD *)(a4 + 32);
      v35 = v20;
      if ( !v20 )
      {
        v21 = EsimId;
        v22 = (_QWORD **)a1[27];
        for ( i = *v22; i != v22 && !(unsigned __int8)std::wstring::_Equal(i + 2, v21); i = (_QWORD *)*i )
          ;
        v15 = v28;
        if ( i != (_QWORD *)a1[27] )
          std::list<std::wstring>::erase(a1 + 27, &v27, i);
        v8 = v36;
        v20 = v35;
        v19 = v34;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v35 = v20;
        v27 = "LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete";
        v34 = v19;
        v29 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v19,
          (unsigned int)&word_18012DB76,
          v17,
          v18,
          (__int64)&v29,
          (__int64)&v27,
          (__int64)&v34,
          (__int64)&v35);
      }
      if ( !a1[28] )
        LPA::EsimManager::UpdateServiceTriggerEvent(v19, 0);
    }
    *(_BYTE *)(*(_QWORD *)(v15 + 48) + 9LL) = 0;
    if ( a2 < 0 )
      goto LABEL_31;
    if ( LPA::EsimManager::EsimRecord::IsBusy(*(LPA::EsimManager::EsimRecord **)(v15 + 48)) )
      goto LABEL_31;
    v24 = *(_QWORD *)(a4 + 32);
    if ( !v24 )
      goto LABEL_31;
    v33 = *(_QWORD *)(a4 + 24);
    v31[2] = v33 + v24;
    v31[0] = *(_QWORD *)a4;
    v32[0] = v31[0];
    v31[1] = 0;
    v32[1] = 0;
    std::sort_std::_Deque_iterator_std::_Deque_val_std::_Deque_simple_types_std::unique_ptr_LPA::Es10bStoredNotificationStruct_std::default_delete_LPA::Es10bStoredNotificationStruct___________LPA::EsimManager::OnEs10bRetrieveNotificationsListComplete_::_52_::_lambda_1___(
      v32,
      v31);
    v25 = *(_QWORD *)(a4 + 24);
    v26 = v25 + *(_QWORD *)(a4 + 32);
    while ( v25 != v26 )
    {
      LPA::EsimManager::EsimRecord::AddEs10bStoredNotification(
        *(_QWORD *)(v15 + 48),
        *(_QWORD *)(*(_QWORD *)(a4 + 8) + 8 * ((*(_QWORD *)(a4 + 16) - 1LL) & (v25 >> 1))) + 8 * (v25 & 1));
      ++v25;
    }
    std::deque<std::unique_ptr<LPA::Es10bStoredNotificationStruct>>::_Tidy(a4);
    if ( (int)LPA::EsimManager::ProcessNextStoredEs10bNotification(
                v14,
                v8,
                *(struct LPA::EsimManager::EsimRecord **)(v15 + 48)) < 0 )
LABEL_31:
      LPA::EsimManager::EsimRecord::ClearStoredNotifications(*(LPA::EsimManager::EsimRecord **)(v15 + 48));
  }
  LPA::EsimManager::CalculateNumberOfBackgroundTasks(v14);
}

```

## disassembly

```asm
0x18008d320  mov     [rsp-8+arg_18], rbx
0x18008d325  mov     [rsp-8+arg_10], r8
0x18008d32a  push    rbp
0x18008d32b  push    rsi
0x18008d32c  push    rdi
0x18008d32d  push    r12
0x18008d32f  push    r13
0x18008d331  push    r14
0x18008d333  push    r15
0x18008d335  lea     rbp, [rsp-1Fh]
0x18008d33a  sub     rsp, 0A0h
0x18008d341  lea     rbx, [rcx+0E8h]
0x18008d348  mov     r12d, edx
0x18008d34b  mov     r14, rcx
0x18008d34e  lea     rdx, [rbp+4Fh+arg_0]
0x18008d352  mov     r13, r8
0x18008d355  mov     rcx, rbx
0x18008d358  lea     r8, [rbp+4Fh+arg_20]
0x18008d35c  mov     rsi, r9
0x18008d35f  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18008d364  mov     rax, [rbp+4Fh+arg_0]
0x18008d368  lea     rcx, aLpaEsimmanager_30; "LPA::EsimManager::OnEs10bRetrieveNotifi"...
0x18008d36f  or      edi, 0FFFFFFFFh
0x18008d372  lea     rdx, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d379  mov     [rbp+4Fh+arg_8], edi
0x18008d37c  cmp     [rbx], rax
0x18008d37f  jnz     short loc_18008D3E1
0x18008d381  mov     eax, cs:CallbackContext
0x18008d387  cmp     eax, 2
0x18008d38a  jbe     short loc_18008D3DB
0x18008d38c  mov     eax, [rbp+4Fh+arg_20]
0x18008d38f  mov     dword ptr [rbp+4Fh+arg_0], eax
0x18008d392  lea     rax, [rbp+4Fh+var_68]
0x18008d396  mov     [rsp+0D0h+var_90], rax
0x18008d39b  lea     rax, [rbp+4Fh+arg_0]
0x18008d39f  mov     [rsp+0D0h+var_98], rax
0x18008d3a4  lea     rax, [rbp+4Fh+var_78]
0x18008d3a8  mov     [rsp+0D0h+var_A0], rax
0x18008d3ad  lea     rax, [rbp+4Fh+var_70]
0x18008d3b1  mov     [rsp+0D0h+var_A8], rax
0x18008d3b6  lea     rax, [rbp+4Fh+var_80]
0x18008d3ba  mov     [rbp+4Fh+var_80], rdx
0x18008d3be  lea     rdx, unk_18012DC30
0x18008d3c5  mov     [rsp+0D0h+var_B0], rax
0x18008d3ca  mov     [rbp+4Fh+var_68], r13
0x18008d3ce  mov     dword ptr [rbp+4Fh+var_78], r12d
0x18008d3d2  mov     [rbp+4Fh+var_70], rcx
0x18008d3d6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008d3db  lea     r15, [r14-8]
0x18008d3df  jmp     short loc_18008D3FE
0x18008d3e1  mov     rcx, [rax+28h]
0x18008d3e5  lea     r15, [r14-8]
0x18008d3e9  lea     rdx, [rbp+4Fh+arg_0]
0x18008d3ed  mov     edi, [rcx+0E0h]
0x18008d3f3  mov     rcx, r15; this
0x18008d3f6  mov     [rbp+4Fh+arg_8], edi
0x18008d3f9  call    ?CompleteOperation@EsimManager@LPA@@AEAAXAEAV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@@Z; LPA::EsimManager::CompleteOperation(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &)
0x18008d3fe  test    r12d, r12d
0x18008d401  jns     short loc_18008D468
0x18008d403  mov     eax, cs:CallbackContext
0x18008d409  cmp     eax, 2
0x18008d40c  jbe     short loc_18008D468
0x18008d40e  lea     rax, aLpaEsimmanager_30; "LPA::EsimManager::OnEs10bRetrieveNotifi"...
0x18008d415  mov     dword ptr [rbp+4Fh+arg_0], edi
0x18008d418  mov     [rbp+4Fh+var_70], rax
0x18008d41c  lea     rdx, dword_18012DBDC
0x18008d423  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d42a  mov     [rbp+4Fh+var_80], r13
0x18008d42e  mov     [rbp+4Fh+var_68], rax
0x18008d432  lea     rax, [rbp+4Fh+arg_0]
0x18008d436  mov     [rsp+0D0h+var_90], rax
0x18008d43b  lea     rax, [rbp+4Fh+var_80]
0x18008d43f  mov     [rsp+0D0h+var_98], rax
0x18008d444  lea     rax, [rbp+4Fh+var_78]
0x18008d448  mov     [rsp+0D0h+var_A0], rax
0x18008d44d  lea     rax, [rbp+4Fh+var_70]
0x18008d451  mov     [rsp+0D0h+var_A8], rax
0x18008d456  lea     rax, [rbp+4Fh+var_68]
0x18008d45a  mov     [rsp+0D0h+var_B0], rax
0x18008d45f  mov     dword ptr [rbp+4Fh+var_78], r12d
0x18008d463  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18008d468  mov     r9, r13
0x18008d46b  lea     r8, [rbp+4Fh+arg_8]
0x18008d46f  lea     rdx, [rbp+4Fh+var_78]
0x18008d473  mov     rcx, r15
0x18008d476  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008d47b  mov     rbx, [rbp+4Fh+var_78]
0x18008d47f  cmp     [r14+0C8h], rbx
0x18008d486  jz      loc_18008D640
0x18008d48c  mov     rcx, [rbx+30h]
0x18008d490  call    ?GetEsimId@EsimRecord@EsimManager@LPA@@QEBAPEAY0CB@$$CBGXZ; LPA::EsimManager::EsimRecord::GetEsimId(void)
0x18008d495  mov     [rbp+4Fh+arg_0], rax
0x18008d499  mov     rcx, rax
0x18008d49c  test    r12d, r12d
0x18008d49f  js      loc_18008D576
0x18008d4a5  test    rax, rax
0x18008d4a8  jz      loc_18008D576
0x18008d4ae  mov     edi, [rsi+20h]
0x18008d4b1  mov     [rbp+4Fh+arg_8], edi
0x18008d4b4  test    edi, edi
0x18008d4b6  jnz     short loc_18008D50D
0x18008d4b8  mov     rax, [r14+0D8h]
0x18008d4bf  mov     rbx, rcx
0x18008d4c2  mov     r13, rax
0x18008d4c5  mov     rdi, [rax]
0x18008d4c8  cmp     rdi, r13
0x18008d4cb  jz      short loc_18008D4E2
0x18008d4cd  lea     rcx, [rdi+10h]
0x18008d4d1  mov     rdx, rbx
0x18008d4d4  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x18008d4d9  test    al, al
0x18008d4db  jnz     short loc_18008D4E2
0x18008d4dd  mov     rdi, [rdi]
0x18008d4e0  jmp     short loc_18008D4C8
0x18008d4e2  mov     rbx, [rbp+4Fh+var_78]
0x18008d4e6  lea     r13, [r14+0D8h]
0x18008d4ed  cmp     rdi, [r13+0]
0x18008d4f1  jz      short loc_18008D502
0x18008d4f3  mov     r8, rdi
0x18008d4f6  lea     rdx, [rbp+4Fh+var_80]
0x18008d4fa  mov     rcx, r13
0x18008d4fd  call    ?erase@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@@Z; std::list<std::wstring>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x18008d502  mov     r13, [rbp+4Fh+arg_10]
0x18008d506  mov     edi, [rbp+4Fh+arg_8]
0x18008d509  mov     rcx, [rbp+4Fh+arg_0]
0x18008d50d  mov     eax, cs:CallbackContext
0x18008d513  cmp     eax, 4
0x18008d516  jbe     short loc_18008D565
0x18008d518  lea     rax, aLpaEsimmanager_30; "LPA::EsimManager::OnEs10bRetrieveNotifi"...
0x18008d51f  mov     [rbp+4Fh+arg_8], edi
0x18008d522  mov     [rbp+4Fh+var_80], rax
0x18008d526  lea     rdx, word_18012DB76
0x18008d52d  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d534  mov     [rbp+4Fh+arg_0], rcx
0x18008d538  mov     [rbp+4Fh+var_70], rax
0x18008d53c  lea     rax, [rbp+4Fh+arg_8]
0x18008d540  mov     [rsp+0D0h+var_98], rax
0x18008d545  lea     rax, [rbp+4Fh+arg_0]
0x18008d549  mov     [rsp+0D0h+var_A0], rax
0x18008d54e  lea     rax, [rbp+4Fh+var_80]
0x18008d552  mov     [rsp+0D0h+var_A8], rax
0x18008d557  lea     rax, [rbp+4Fh+var_70]
0x18008d55b  mov     [rsp+0D0h+var_B0], rax
0x18008d560  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008d565  cmp     qword ptr [r14+0E0h], 0
0x18008d56d  jnz     short loc_18008D576
0x18008d56f  xor     edx, edx; bool
0x18008d571  call    ?UpdateServiceTriggerEvent@EsimManager@LPA@@AEAAX_N@Z; LPA::EsimManager::UpdateServiceTriggerEvent(bool)
0x18008d576  mov     rax, [rbx+30h]
0x18008d57a  mov     byte ptr [rax+9], 0
0x18008d57e  test    r12d, r12d
0x18008d581  js      loc_18008D637
0x18008d587  mov     rcx, [rbx+30h]; this
0x18008d58b  call    ?IsBusy@EsimRecord@EsimManager@LPA@@QEBA_NXZ; LPA::EsimManager::EsimRecord::IsBusy(void)
0x18008d590  test    al, al
0x18008d592  jnz     loc_18008D637
0x18008d598  mov     rax, [rsi+20h]
0x18008d59c  test    rax, rax
0x18008d59f  jz      loc_18008D637
0x18008d5a5  mov     rcx, [rsi+18h]
0x18008d5a9  lea     rdx, [rbp+4Fh+var_60]
0x18008d5ad  add     rax, rcx
0x18008d5b0  mov     [rbp+4Fh+var_38], rcx
0x18008d5b4  mov     [rbp+4Fh+var_50], rax
0x18008d5b8  lea     rcx, [rbp+4Fh+var_48]
0x18008d5bc  mov     rax, [rsi]
0x18008d5bf  mov     [rbp+4Fh+var_60], rax
0x18008d5c3  mov     [rbp+4Fh+var_48], rax
0x18008d5c7  mov     [rbp+4Fh+var_58], 0
0x18008d5cf  mov     [rbp+4Fh+var_40], 0
0x18008d5d7  call    std__sort_std___Deque_iterator_std___Deque_val_std___Deque_simple_types_std__unique_ptr_LPA__Es10bStoredNotificationStruct_std__default_delete_LPA__Es10bStoredNotificationStruct___________LPA__EsimManager__OnEs10bRetrieveNotificationsListComplete____52____lambda_1___
0x18008d5dc  mov     rdi, [rsi+18h]
0x18008d5e0  mov     r14, [rsi+20h]
0x18008d5e4  add     r14, rdi
0x18008d5e7  cmp     rdi, r14
0x18008d5ea  jz      short loc_18008D61C
0x18008d5ec  mov     rax, [rsi+10h]
0x18008d5f0  mov     rcx, rdi
0x18008d5f3  dec     rax
0x18008d5f6  and     ecx, 1
0x18008d5f9  mov     rdx, rdi
0x18008d5fc  shr     rdx, 1
0x18008d5ff  and     rdx, rax
0x18008d602  mov     rax, [rsi+8]
0x18008d606  mov     rax, [rax+rdx*8]
0x18008d60a  lea     rdx, [rax+rcx*8]
0x18008d60e  mov     rcx, [rbx+30h]
0x18008d612  call    ?AddEs10bStoredNotification@EsimRecord@EsimManager@LPA@@QEAAXAEAV?$unique_ptr@UEs10bStoredNotificationStruct@LPA@@U?$default_delete@UEs10bStoredNotificationStruct@LPA@@@std@@@std@@@Z; LPA::EsimManager::EsimRecord::AddEs10bStoredNotification(std::unique_ptr<LPA::Es10bStoredNotificationStruct> &)
0x18008d617  inc     rdi
0x18008d61a  jmp     short loc_18008D5E7
0x18008d61c  mov     rcx, rsi
0x18008d61f  call    ?_Tidy@?$deque@V?$unique_ptr@UEs10bStoredNotificationStruct@LPA@@U?$default_delete@UEs10bStoredNotificationStruct@LPA@@@std@@@std@@V?$allocator@V?$unique_ptr@UEs10bStoredNotificationStruct@LPA@@U?$default_delete@UEs10bStoredNotificationStruct@LPA@@@std@@@std@@@2@@std@@AEAAXXZ; std::deque<std::unique_ptr<LPA::Es10bStoredNotificationStruct>>::_Tidy(void)
0x18008d624  mov     r8, [rbx+30h]; struct LPA::EsimManager::EsimRecord *
0x18008d628  mov     rdx, r13; struct _GUID *
0x18008d62b  mov     rcx, r15; this
0x18008d62e  call    ?ProcessNextStoredEs10bNotification@EsimManager@LPA@@AEAAJAEBU_GUID@@PEAVEsimRecord@12@@Z; LPA::EsimManager::ProcessNextStoredEs10bNotification(_GUID const &,LPA::EsimManager::EsimRecord *)
0x18008d633  test    eax, eax
0x18008d635  jns     short loc_18008D640
0x18008d637  mov     rcx, [rbx+30h]; this
0x18008d63b  call    ?ClearStoredNotifications@EsimRecord@EsimManager@LPA@@QEAAXXZ; LPA::EsimManager::EsimRecord::ClearStoredNotifications(void)
0x18008d640  mov     rcx, r15; this
0x18008d643  mov     rbx, [rsp+0D0h+arg_18]
0x18008d64b  add     rsp, 0A0h
0x18008d652  pop     r15
0x18008d654  pop     r14
0x18008d656  pop     r13
0x18008d658  pop     r12
0x18008d65a  pop     rdi
0x18008d65b  pop     rsi
0x18008d65c  pop     rbp
0x18008d65d  jmp     ?CalculateNumberOfBackgroundTasks@EsimManager@LPA@@AEAAXXZ; LPA::EsimManager::CalculateNumberOfBackgroundTasks(void)
```
