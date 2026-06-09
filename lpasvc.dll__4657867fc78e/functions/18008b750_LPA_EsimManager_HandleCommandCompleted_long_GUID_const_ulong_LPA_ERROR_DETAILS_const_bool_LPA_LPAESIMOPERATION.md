# LPA::EsimManager::HandleCommandCompleted(long,_GUID const &,ulong,LPA_ERROR_DETAILS const *,bool,LPA::LPAESIMOPERATIONINTERNAL)

- ea: `0x18008b750`
- end: `0x18008bcbb`
- name: `?HandleCommandCompleted@EsimManager@LPA@@AEAAXJAEBU_GUID@@KPEBULPA_ERROR_DETAILS@@_NW4LPAESIMOPERATIONINTERNAL@2@@Z`
- size: `1387`
- prototype: ``
- caller_count: `10`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008cdf0`
- `0x18008d670`
- `0x18008d6a0`
- `0x18008d6d0`
- `0x18008e550`
- `0x18008e580`
- `0x18008e750`
- `0x18008e920`
- `0x18008ed30`
- `0x18008efb0`

## callees

- `0x1800018b4`
- `0x180003f84`
- `0x180004a7c`
- `0x18000517c`
- `0x18005fa50`
- `0x1800709e4`
- `0x180071840`
- `0x180071a8c`
- `0x180081618`
- `0x180087e78`
- `0x180087ffc`
- `0x180088378`
- `0x180088b48`
- `0x18008ae98`
- `0x18008b750`
- `0x18008c8d8`
- `0x1800925e4`
- `0x180093f80`
- `0x180094488`
- `0x180094924`
- `0x180095414`
- `0x180095738`
- `0x180095df0`
- `0x180095fd0`
- `0x180101010`

## string_xrefs

- `0x18008b78a`: `LpaServiceEsimManager`
- `0x18008b89b`: `LpaServiceEsimManager`
- `0x18008b94e`: `LpaServiceEsimManager`
- `0x18008b992`: `LpaServiceEsimManager`
- `0x18008ba77`: `LpaServiceEsimManager`
- `0x18008bc4c`: `LpaServiceEsimManager`
- `0x18008b783`: `LPA::EsimManager::HandleCommandCompleted`
- `0x18008b890`: `LPA::EsimManager::HandleCommandCompleted`
- `0x18008b943`: `LPA::EsimManager::HandleCommandCompleted`
- `0x18008b98b`: `LPA::EsimManager::HandleCommandCompleted`
- `0x18008ba6c`: `LPA::EsimManager::HandleCommandCompleted`
- `0x18008bc41`: `LPA::EsimManager::HandleCommandCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LPA::EsimManager::HandleCommandCompleted(
        LPA::EsimManager *a1,
        int a2,
        const struct _GUID *a3,
        int a4,
        struct LPA_ERROR_DETAILS *a5,
        char a6,
        unsigned int a7)
{
  struct LPA_ERROR_DETAILS *v11; // rdi
  int v12; // eax
  LPA::EsimManager::OperationEntry *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rbx
  __int16 *v17; // rdx
  int v18; // edi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rbx
  const struct LPA_ESIM_DETAILS *EsimDetails; // rax
  int v24; // r8d
  int v25; // r9d
  struct LPA::EsimManager::EsimRecord *v26; // rcx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  unsigned int v30; // r13d
  __int64 (__fastcall *v31)(); // rcx
  __int64 (__fastcall ***v32)(_QWORD, const struct _GUID *, _QWORD, _QWORD *, int *); // rdi
  __int64 (__fastcall *v33)(_QWORD, const struct _GUID *, _QWORD, _QWORD *, int *); // rbx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  int v36; // ebx
  __int64 v37; // rsi
  __int64 (__fastcall *v38)(__int64, const struct _GUID *, _QWORD, __int64, int *); // rdi
  __int64 v39; // rax
  unsigned int v40; // edx
  int v41; // edi
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // [rsp+38h] [rbp-69h]
  int v46; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v47; // [rsp+74h] [rbp-2Dh] BYREF
  _QWORD v48[2]; // [rsp+78h] [rbp-29h] BYREF
  const char *v49; // [rsp+88h] [rbp-19h] BYREF
  __int64 v50; // [rsp+90h] [rbp-11h] BYREF
  const char *v51; // [rsp+98h] [rbp-9h] BYREF
  std::_Ref_count_base *v52; // [rsp+A0h] [rbp-1h]
  int v53; // [rsp+A8h] [rbp+7h] BYREF
  int v54[13]; // [rsp+ACh] [rbp+Bh] BYREF
  int v55; // [rsp+F0h] [rbp+4Fh] BYREF
  int v56; // [rsp+108h] [rbp+67h] BYREF

  v56 = a4;
  v11 = a5;
  if ( (unsigned int)CallbackContext > 4 )
  {
    if ( a5 )
    {
      v55 = *((_DWORD *)a5 + 2);
      v47 = *((_DWORD *)a5 + 1);
      v12 = *(_DWORD *)a5;
    }
    else
    {
      v55 = 0;
      v47 = 0;
      v12 = 0;
    }
    v53 = v12;
    v54[0] = a4;
    LODWORD(v50) = a7;
    v46 = a2;
    v49 = (const char *)a3;
    v51 = "LPA::EsimManager::HandleCommandCompleted";
    v48[0] = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"LPA::EsimManager::HandleCommandCompleted",
      (unsigned int)byte_18012EE99,
      (_DWORD)a3,
      a4,
      (__int64)v48,
      (__int64)&v51,
      (__int64)&v49,
      (__int64)&v46,
      (__int64)&v50,
      (__int64)v54,
      (__int64)&v53,
      (__int64)&v47,
      (__int64)&v55);
  }
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    (char *)a1 + 240,
    &v50,
    &v56);
  v16 = v50;
  if ( *((_QWORD *)a1 + 30) == v50 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_13;
    v17 = &word_18012EE3E;
    goto LABEL_12;
  }
  v13 = *(LPA::EsimManager::OperationEntry **)(v50 + 40);
  if ( !v13 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_13;
    v17 = (__int16 *)byte_18012EDE3;
LABEL_12:
    v51 = "LPA::EsimManager::HandleCommandCompleted";
    v49 = "LpaServiceEsimManager";
    v48[0] = a3;
    v55 = a4;
    v46 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (_DWORD)v13,
      (_DWORD)v17,
      v14,
      v15,
      (__int64)&v49,
      (__int64)&v51,
      (__int64)&v46,
      (__int64)&v55,
      (__int64)v48);
LABEL_13:
    if ( v16 != *((_QWORD *)a1 + 30) )
    {
      v18 = *(_DWORD *)(*(_QWORD *)(v16 + 40) + 224LL);
      v55 = v18;
      LPA::EsimManager::TryFindEsimRecordBySlotId(a1, v48, &v55, a3);
      v22 = v48[0];
      if ( v48[0] == *((_QWORD *)a1 + 26) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v55 = v18;
          v46 = a4;
          v48[0] = "LPA::EsimManager::HandleCommandCompleted";
          v51 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)&dword_18012ECAC,
            v20,
            v21,
            (__int64)&v51,
            (__int64)v48,
            (__int64)&v46,
            (__int64)&v55);
        }
      }
      else
      {
        EsimDetails = LPA::EsimManager::EsimRecord::GetEsimDetails(*(LPA::EsimManager::EsimRecord **)(v48[0] + 48LL));
        if ( (unsigned int)CallbackContext > 3 )
        {
          v46 = a4;
          if ( EsimDetails )
            LODWORD(EsimDetails) = *((_DWORD *)EsimDetails + 170);
          LODWORD(v50) = (_DWORD)EsimDetails;
          v48[0] = "LPA::EsimManager::HandleCommandCompleted";
          v51 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)CallbackContext,
            (unsigned int)&word_18012ED46,
            v24,
            v25,
            (__int64)&v51,
            (__int64)v48,
            (__int64)&v50,
            (__int64)&v46);
        }
        LPA::EsimManager::EsimRecord::SetOperationCompleted(*(_QWORD *)(v22 + 48), a7);
        LPA::EsimManager::ProcessAndBroadcastChanges(a1, 0);
        LPA::EsimManager::TryFindEsimRecordBySlotId(a1, v48, &v55, a3);
        if ( v48[0] != *((_QWORD *)a1 + 26)
          && !LPA::EsimManager::EsimRecord::IsProcessingEs10bNotifications(*(LPA::EsimManager::EsimRecord **)(v48[0] + 48LL)) )
        {
          if ( LPA::EsimManager::RetrieveEs10bNotificationsList(a1, a3, v26) < 0 )
          {
            if ( (unsigned int)CallbackContext > 3 )
            {
              v48[0] = a3;
              v55 = a2;
              v51 = "LPA::EsimManager::HandleCommandCompleted";
              v49 = "LpaServiceEsimManager";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
                v27,
                (unsigned int)word_18012ECFA,
                v28,
                v29,
                (__int64)&v49,
                (__int64)&v51,
                (__int64)&v55,
                (__int64)v48);
            }
          }
          else
          {
            LPA::EsimManager::CalculateNumberOfBackgroundTasks(a1);
          }
        }
      }
    }
    return;
  }
  v30 = *((_DWORD *)v13 + 56);
  v47 = v30;
  LPA::EsimManager::OperationEntry::SetResult(v13, a2);
  LPA::EsimManager::OperationEntry::SetErrorDetails(*(LPA::EsimManager::OperationEntry **)(v16 + 40), v11);
  if ( !a6 )
    goto LABEL_44;
  v55 = 0;
  v31 = *(__int64 (__fastcall **)())(*(_QWORD *)(v16 + 40) + 40LL);
  if (  LPA::EsimManagerCompletionHandler::`vcall'{72,{flat}} == v31 )
  {
    v32 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, _QWORD, _QWORD *, int *))*((_QWORD *)a1 + 18);
    v33 = **v32;
    v34 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)a1 + 88, &v51);
    v35 = std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(
            v48,
            v34);
    v36 = v33(v32, a3, v30, v35, &v55);
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
    if ( v36 >= 0 )
    {
LABEL_32:
      LOBYTE(v45) = 0;
      LPA::EsimManager::TransferOperationToNewTransactionId(
        (_DWORD)a1,
        (unsigned int)&v50,
        (_DWORD)a3,
        0,
        0,
        0,
        0,
        v45,
        v55);
      return;
    }
    goto LABEL_44;
  }
  if (  LPA::EsimManagerCompletionHandler::`vcall'{88,{flat}} == v31 )
  {
    LPA::EsimManager::AttemptToGetEuiccConfiguredData(a1, a3, &v47);
  }
  else if (  LPA::EsimManagerCompletionHandler::`vcall'{32,{flat}} == v31 )
  {
    LPA::EsimManager::AttemptToGetEuiccInfo2(a1, a3, &v47);
  }
  v37 = *((_QWORD *)a1 + 18);
  v38 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, __int64, int *))(*(_QWORD *)(v37 + 16) + 32LL);
  std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)a1 + 88, &v51);
  v39 = std::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>(v48);
  v41 = v38(v37 + 16, a3, v30, v39, &v55);
  v44 = (int)v52;
  if ( v52 )
    std::_Ref_count_base::_Decref(v52);
  if ( v41 >= 0 )
    goto LABEL_32;
  if ( !*(_BYTE *)(*(_QWORD *)(v16 + 40) + 89LL) )
    goto LABEL_44;
  if ( (unsigned int)CallbackContext > 3 )
  {
    v48[0] = a3;
    v46 = a2;
    v51 = "LPA::EsimManager::HandleCommandCompleted";
    v49 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v44,
      (unsigned int)&byte_18012ED97,
      v42,
      v43,
      (__int64)&v49,
      (__int64)&v51,
      (__int64)&v46,
      (__int64)v48);
  }
  if ( (int)LPA::EsimManager::OperationEntry::StartTransactionTimer(*(struct _TP_TIMER ***)(v16 + 40), v40) < 0 )
LABEL_44:
    LPA::EsimManager::CompleteOperation(a1);
}

```

## disassembly

```asm
0x18008b750  mov     [rsp-8+arg_8], rbx
0x18008b755  mov     [rsp-8+arg_18], r9d
0x18008b75a  push    rbp
0x18008b75b  push    rsi
0x18008b75c  push    rdi
0x18008b75d  push    r12
0x18008b75f  push    r13
0x18008b761  push    r14
0x18008b763  push    r15
0x18008b765  lea     rbp, [rsp-0Fh]
0x18008b76a  sub     rsp, 0B0h
0x18008b771  mov     esi, r9d
0x18008b774  mov     r15, r8
0x18008b777  mov     r12d, edx
0x18008b77a  mov     r14, rcx
0x18008b77d  mov     eax, cs:CallbackContext
0x18008b783  lea     rcx, aLpaEsimmanager_46; "LPA::EsimManager::HandleCommandComplete"...
0x18008b78a  lea     rdx, aLpaserviceesim; "LpaServiceEsimManager"
0x18008b791  mov     rdi, [rbp+3Fh+arg_20]
0x18008b795  cmp     eax, 4
0x18008b798  jbe     loc_18008B83C
0x18008b79e  test    rdi, rdi
0x18008b7a1  jz      short loc_18008B7B3
0x18008b7a3  mov     eax, [rdi+8]
0x18008b7a6  mov     [rbp+3Fh+arg_0], eax
0x18008b7a9  mov     eax, [rdi+4]
0x18008b7ac  mov     [rbp+3Fh+var_6C], eax
0x18008b7af  mov     eax, [rdi]
0x18008b7b1  jmp     short loc_18008B7C3
0x18008b7b3  mov     [rbp+3Fh+arg_0], 0
0x18008b7ba  mov     [rbp+3Fh+var_6C], 0
0x18008b7c1  xor     eax, eax
0x18008b7c3  mov     [rbp+3Fh+var_38], eax
0x18008b7c6  mov     [rbp+3Fh+var_34], esi
0x18008b7c9  mov     eax, [rbp+3Fh+arg_30]
0x18008b7cc  mov     dword ptr [rbp+3Fh+var_50], eax
0x18008b7cf  mov     [rbp+3Fh+var_70], r12d
0x18008b7d3  mov     [rbp+3Fh+var_58], r15
0x18008b7d7  mov     [rbp+3Fh+var_48], rcx
0x18008b7db  mov     [rbp+3Fh+var_68], rdx
0x18008b7df  lea     rax, [rbp+3Fh+arg_0]
0x18008b7e3  mov     [rsp+0E0h+var_80], rax
0x18008b7e8  lea     rax, [rbp+3Fh+var_6C]
0x18008b7ec  mov     [rsp+0E0h+var_88], rax
0x18008b7f1  lea     rax, [rbp+3Fh+var_38]
0x18008b7f5  mov     [rsp+0E0h+var_90], rax
0x18008b7fa  lea     rax, [rbp+3Fh+var_34]
0x18008b7fe  mov     [rsp+0E0h+var_98], rax
0x18008b803  lea     rax, [rbp+3Fh+var_50]
0x18008b807  mov     [rsp+0E0h+var_A0], rax
0x18008b80c  lea     rax, [rbp+3Fh+var_70]
0x18008b810  mov     [rsp+0E0h+var_A8], rax
0x18008b815  lea     rax, [rbp+3Fh+var_58]
0x18008b819  mov     [rsp+0E0h+var_B0], rax
0x18008b81e  lea     rax, [rbp+3Fh+var_48]
0x18008b822  mov     [rsp+0E0h+var_B8], rax
0x18008b827  lea     rax, [rbp+3Fh+var_68]
0x18008b82b  mov     [rsp+0E0h+var_C0], rax
0x18008b830  lea     rdx, byte_18012EE99
0x18008b837  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008b83c  lea     r13, [r14+0F0h]
0x18008b843  lea     r8, [rbp+3Fh+arg_18]
0x18008b847  lea     rdx, [rbp+3Fh+var_50]
0x18008b84b  mov     rcx, r13
0x18008b84e  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18008b853  mov     rbx, [rbp+3Fh+var_50]
0x18008b857  cmp     [r13+0], rbx
0x18008b85b  jnz     short loc_18008B871
0x18008b85d  mov     eax, cs:CallbackContext
0x18008b863  cmp     eax, 2
0x18008b866  jbe     short loc_18008B8E3
0x18008b868  lea     rdx, word_18012EE3E
0x18008b86f  jmp     short loc_18008B890
0x18008b871  mov     rcx, [rbx+28h]; this
0x18008b875  test    rcx, rcx
0x18008b878  jnz     loc_18008BAB7
0x18008b87e  mov     eax, cs:CallbackContext
0x18008b884  cmp     eax, 2
0x18008b887  jbe     short loc_18008B8E3
0x18008b889  lea     rdx, byte_18012EDE3
0x18008b890  lea     rax, aLpaEsimmanager_46; "LPA::EsimManager::HandleCommandComplete"...
0x18008b897  mov     [rbp+3Fh+var_48], rax
0x18008b89b  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008b8a2  mov     [rbp+3Fh+var_58], rax
0x18008b8a6  lea     rax, [rbp+3Fh+var_68]
0x18008b8aa  mov     [rsp+0E0h+var_A0], rax
0x18008b8af  lea     rax, [rbp+3Fh+arg_0]
0x18008b8b3  mov     [rsp+0E0h+var_A8], rax
0x18008b8b8  lea     rax, [rbp+3Fh+var_70]
0x18008b8bc  mov     [rsp+0E0h+var_B0], rax
0x18008b8c1  lea     rax, [rbp+3Fh+var_48]
0x18008b8c5  mov     [rsp+0E0h+var_B8], rax
0x18008b8ca  lea     rax, [rbp+3Fh+var_58]
0x18008b8ce  mov     [rsp+0E0h+var_C0], rax
0x18008b8d3  mov     [rbp+3Fh+var_68], r15
0x18008b8d7  mov     [rbp+3Fh+arg_0], esi
0x18008b8da  mov     [rbp+3Fh+var_70], r12d
0x18008b8de  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008b8e3  cmp     rbx, [r13+0]
0x18008b8e7  jz      loc_18008BCA0
0x18008b8ed  mov     rax, [rbx+28h]
0x18008b8f1  mov     edi, [rax+0E0h]
0x18008b8f7  mov     [rbp+3Fh+arg_0], edi
0x18008b8fa  mov     r9, r15
0x18008b8fd  lea     r8, [rbp+3Fh+arg_0]
0x18008b901  lea     rdx, [rbp+3Fh+var_68]
0x18008b905  mov     rcx, r14
0x18008b908  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008b90d  mov     rbx, [rbp+3Fh+var_68]
0x18008b911  cmp     rbx, [r14+0D0h]
0x18008b918  jz      loc_18008BA57
0x18008b91e  mov     rcx, [rbx+30h]; this
0x18008b922  call    ?GetEsimDetails@EsimRecord@EsimManager@LPA@@QEBAPEBULPA_ESIM_DETAILS@@XZ; LPA::EsimManager::EsimRecord::GetEsimDetails(void)
0x18008b927  mov     ecx, cs:CallbackContext
0x18008b92d  cmp     ecx, 3
0x18008b930  jbe     short loc_18008B98B
0x18008b932  mov     [rbp+3Fh+var_70], esi
0x18008b935  test    rax, rax
0x18008b938  jz      short loc_18008B940
0x18008b93a  mov     eax, [rax+2A8h]
0x18008b940  mov     dword ptr [rbp+3Fh+var_50], eax
0x18008b943  lea     rdi, aLpaEsimmanager_46; "LPA::EsimManager::HandleCommandComplete"...
0x18008b94a  mov     [rbp+3Fh+var_68], rdi
0x18008b94e  lea     rsi, aLpaserviceesim; "LpaServiceEsimManager"
0x18008b955  mov     [rbp+3Fh+var_48], rsi
0x18008b959  lea     rax, [rbp+3Fh+var_70]
0x18008b95d  mov     [rsp+0E0h+var_A8], rax
0x18008b962  lea     rax, [rbp+3Fh+var_50]
0x18008b966  mov     [rsp+0E0h+var_B0], rax
0x18008b96b  lea     rax, [rbp+3Fh+var_68]
0x18008b96f  mov     [rsp+0E0h+var_B8], rax
0x18008b974  lea     rax, [rbp+3Fh+var_48]
0x18008b978  mov     [rsp+0E0h+var_C0], rax
0x18008b97d  lea     rdx, word_18012ED46
0x18008b984  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008b989  jmp     short loc_18008B999
0x18008b98b  lea     rdi, aLpaEsimmanager_46; "LPA::EsimManager::HandleCommandComplete"...
0x18008b992  lea     rsi, aLpaserviceesim; "LpaServiceEsimManager"
0x18008b999  mov     edx, [rbp+3Fh+arg_30]
0x18008b99c  mov     rcx, [rbx+30h]
0x18008b9a0  call    ?SetOperationCompleted@EsimRecord@EsimManager@LPA@@QEAAXW4LPAESIMOPERATIONINTERNAL@3@J@Z; LPA::EsimManager::EsimRecord::SetOperationCompleted(LPA::LPAESIMOPERATIONINTERNAL,long)
0x18008b9a5  xor     edx, edx; bool
0x18008b9a7  mov     rcx, r14; this
0x18008b9aa  call    ?ProcessAndBroadcastChanges@EsimManager@LPA@@AEAAX_N@Z; LPA::EsimManager::ProcessAndBroadcastChanges(bool)
0x18008b9af  mov     r9, r15
0x18008b9b2  lea     r8, [rbp+3Fh+arg_0]
0x18008b9b6  lea     rdx, [rbp+3Fh+var_68]
0x18008b9ba  mov     rcx, r14
0x18008b9bd  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008b9c2  mov     rax, [rbp+3Fh+var_68]
0x18008b9c6  cmp     rax, [r14+0D0h]
0x18008b9cd  jz      loc_18008BCA0
0x18008b9d3  mov     rcx, [rax+30h]; this
0x18008b9d7  call    ?IsProcessingEs10bNotifications@EsimRecord@EsimManager@LPA@@QEBA_NXZ; LPA::EsimManager::EsimRecord::IsProcessingEs10bNotifications(void)
0x18008b9dc  test    al, al
0x18008b9de  jnz     loc_18008BCA0
0x18008b9e4  mov     r8, rcx; struct LPA::EsimManager::EsimRecord *
0x18008b9e7  mov     rdx, r15; struct _GUID *
0x18008b9ea  mov     rcx, r14; this
0x18008b9ed  call    ?RetrieveEs10bNotificationsList@EsimManager@LPA@@AEAAJAEBU_GUID@@PEAVEsimRecord@12@@Z; LPA::EsimManager::RetrieveEs10bNotificationsList(_GUID const &,LPA::EsimManager::EsimRecord *)
0x18008b9f2  test    eax, eax
0x18008b9f4  js      short loc_18008BA03
0x18008b9f6  mov     rcx, r14; this
0x18008b9f9  call    ?CalculateNumberOfBackgroundTasks@EsimManager@LPA@@AEAAXXZ; LPA::EsimManager::CalculateNumberOfBackgroundTasks(void)
0x18008b9fe  jmp     loc_18008BCA0
0x18008ba03  mov     eax, cs:CallbackContext
0x18008ba09  cmp     eax, 3
0x18008ba0c  jbe     loc_18008BCA0
0x18008ba12  mov     [rbp+3Fh+var_68], r15
0x18008ba16  mov     [rbp+3Fh+arg_0], r12d
0x18008ba1a  mov     [rbp+3Fh+var_48], rdi
0x18008ba1e  mov     [rbp+3Fh+var_58], rsi
0x18008ba22  lea     rax, [rbp+3Fh+var_68]
0x18008ba26  mov     [rsp+0E0h+var_A8], rax
0x18008ba2b  lea     rax, [rbp+3Fh+arg_0]
0x18008ba2f  mov     [rsp+0E0h+var_B0], rax
0x18008ba34  lea     rax, [rbp+3Fh+var_48]
0x18008ba38  mov     [rsp+0E0h+var_B8], rax
0x18008ba3d  lea     rax, [rbp+3Fh+var_58]
0x18008ba41  mov     [rsp+0E0h+var_C0], rax
0x18008ba46  lea     rdx, word_18012ECFA
0x18008ba4d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008ba52  jmp     loc_18008BCA0
0x18008ba57  mov     eax, cs:CallbackContext
0x18008ba5d  cmp     eax, 2
0x18008ba60  jbe     loc_18008BCA0
0x18008ba66  mov     [rbp+3Fh+arg_0], edi
0x18008ba69  mov     [rbp+3Fh+var_70], esi
0x18008ba6c  lea     rax, aLpaEsimmanager_46; "LPA::EsimManager::HandleCommandComplete"...
0x18008ba73  mov     [rbp+3Fh+var_68], rax
0x18008ba77  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008ba7e  mov     [rbp+3Fh+var_48], rax
0x18008ba82  lea     rax, [rbp+3Fh+arg_0]
0x18008ba86  mov     [rsp+0E0h+var_A8], rax
0x18008ba8b  lea     rax, [rbp+3Fh+var_70]
0x18008ba8f  mov     [rsp+0E0h+var_B0], rax
0x18008ba94  lea     rax, [rbp+3Fh+var_68]
0x18008ba98  mov     [rsp+0E0h+var_B8], rax
0x18008ba9d  lea     rax, [rbp+3Fh+var_48]
0x18008baa1  mov     [rsp+0E0h+var_C0], rax
0x18008baa6  lea     rdx, dword_18012ECAC
0x18008baad  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008bab2  jmp     loc_18008BCA0
0x18008bab7  mov     r13d, [rcx+0E0h]
0x18008babe  mov     [rbp+3Fh+var_6C], r13d
0x18008bac2  mov     edx, r12d; int
0x18008bac5  call    ?SetResult@OperationEntry@EsimManager@LPA@@QEAAXJ@Z; LPA::EsimManager::OperationEntry::SetResult(long)
0x18008baca  mov     rdx, rdi; struct LPA_ERROR_DETAILS *
0x18008bacd  mov     rcx, [rbx+28h]; this
0x18008bad1  call    ?SetErrorDetails@OperationEntry@EsimManager@LPA@@QEAAXPEBULPA_ERROR_DETAILS@@@Z; LPA::EsimManager::OperationEntry::SetErrorDetails(LPA_ERROR_DETAILS const *)
0x18008bad6  xor     esi, esi
0x18008bad8  cmp     [rbp+3Fh+arg_28], sil
0x18008badc  jz      loc_18008BC94
0x18008bae2  mov     [rbp+3Fh+arg_0], esi
0x18008bae5  mov     rax, [rbx+28h]
0x18008bae9  mov     rcx, [rax+28h]
0x18008baed  lea     rax, ??_9EsimManagerCompletionHandler@LPA@@$BEI@AA; [thunk]: LPA::EsimManagerCompletionHandler::`vcall'{72,{flat}}
0x18008baf4  cmp     rax, rcx
0x18008baf7  jnz     loc_18008BB8B
0x18008bafd  mov     rdi, [r14+90h]
0x18008bb04  mov     rax, [rdi]
0x18008bb07  mov     rbx, [rax]
0x18008bb0a  lea     rcx, [r14+58h]
0x18008bb0e  lea     rdx, [rbp+3Fh+var_48]
0x18008bb12  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18008bb17  nop
0x18008bb18  mov     rdx, rax
0x18008bb1b  lea     rcx, [rbp+3Fh+var_68]
0x18008bb1f  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$weak_ptr@V?$streambuf_state_manager@D@details@streams@Concurrency@@@std@@QEAA@AEBV?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@1@@Z; std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>> const &)
0x18008bb24  lea     rcx, [rbp+3Fh+arg_0]
0x18008bb28  mov     [rsp+0E0h+var_C0], rcx
0x18008bb2d  mov     r9, rax
0x18008bb30  mov     r8d, r13d
0x18008bb33  mov     rdx, r15
0x18008bb36  mov     rcx, rdi
0x18008bb39  mov     rax, rbx
0x18008bb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bb41  mov     ebx, eax
0x18008bb43  mov     rcx, [rbp+3Fh+var_40]; this
0x18008bb47  test    rcx, rcx
0x18008bb4a  jz      short loc_18008BB51
0x18008bb4c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008bb51  test    ebx, ebx
0x18008bb53  js      loc_18008BC94
0x18008bb59  mov     eax, [rbp+3Fh+arg_0]
0x18008bb5c  mov     dword ptr [rsp+0E0h+var_A0], eax
0x18008bb60  mov     byte ptr [rsp+0E0h+var_A8], sil
0x18008bb65  mov     byte ptr [rsp+0E0h+var_B0], sil
0x18008bb6a  mov     byte ptr [rsp+0E0h+var_B8], sil
0x18008bb6f  mov     byte ptr [rsp+0E0h+var_C0], sil
0x18008bb74  xor     r9d, r9d
0x18008bb77  mov     r8, r15
0x18008bb7a  lea     rdx, [rbp+3Fh+var_50]
0x18008bb7e  mov     rcx, r14
0x18008bb81  call    ?TransferOperationToNewTransactionId@EsimManager@LPA@@AEAAXAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBU_GUID@@_N2222K@Z; LPA::EsimManager::TransferOperationToNewTransactionId(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &,_GUID const &,bool,bool,bool,bool,bool,ulong)
0x18008bb86  jmp     loc_18008BCA0
0x18008bb8b  lea     rax, ??_9EsimManagerCompletionHandler@LPA@@$BFI@AA; [thunk]: LPA::EsimManagerCompletionHandler::`vcall'{88,{flat}}
0x18008bb92  cmp     rax, rcx
0x18008bb95  jnz     short loc_18008BBA8
0x18008bb97  lea     r8, [rbp+3Fh+var_6C]; unsigned int *
0x18008bb9b  mov     rdx, r15; struct _GUID *
0x18008bb9e  mov     rcx, r14; this
0x18008bba1  call    ?AttemptToGetEuiccConfiguredData@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK@Z; LPA::EsimManager::AttemptToGetEuiccConfiguredData(_GUID const &,ulong const &)
0x18008bba6  jmp     short loc_18008BBC3
0x18008bba8  lea     rax, ??_9EsimManagerCompletionHandler@LPA@@$BCA@AA; [thunk]: LPA::EsimManagerCompletionHandler::`vcall'{32,{flat}}
0x18008bbaf  cmp     rax, rcx
0x18008bbb2  jnz     short loc_18008BBC3
0x18008bbb4  lea     r8, [rbp+3Fh+var_6C]; unsigned int *
0x18008bbb8  mov     rdx, r15; struct _GUID *
0x18008bbbb  mov     rcx, r14; this
0x18008bbbe  call    ?AttemptToGetEuiccInfo2@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK@Z; LPA::EsimManager::AttemptToGetEuiccInfo2(_GUID const &,ulong const &)
0x18008bbc3  mov     rsi, [r14+90h]
0x18008bbca  mov     rax, [rsi+10h]
0x18008bbce  mov     rdi, [rax+20h]
0x18008bbd2  lea     rcx, [r14+58h]
0x18008bbd6  lea     rdx, [rbp+3Fh+var_48]
0x18008bbda  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18008bbdf  nop
0x18008bbe0  mov     rdx, rax
0x18008bbe3  lea     rcx, [rbp+3Fh+var_68]
0x18008bbe7  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UApduHelperEs10cCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x18008bbec  lea     rcx, [rbp+3Fh+arg_0]
0x18008bbf0  mov     [rsp+0E0h+var_C0], rcx
0x18008bbf5  mov     r9, rax
0x18008bbf8  mov     r8d, r13d
0x18008bbfb  mov     rdx, r15
0x18008bbfe  lea     rcx, [rsi+10h]
0x18008bc02  mov     rax, rdi
0x18008bc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc0a  mov     edi, eax
0x18008bc0c  mov     rcx, [rbp+3Fh+var_40]; this
0x18008bc10  xor     esi, esi
0x18008bc12  test    rcx, rcx
0x18008bc15  jz      short loc_18008BC1C
0x18008bc17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008bc1c  test    edi, edi
0x18008bc1e  jns     loc_18008BB59
0x18008bc24  mov     rax, [rbx+28h]
0x18008bc28  cmp     [rax+59h], sil
0x18008bc2c  jz      short loc_18008BC94
  ... truncated ...
```
