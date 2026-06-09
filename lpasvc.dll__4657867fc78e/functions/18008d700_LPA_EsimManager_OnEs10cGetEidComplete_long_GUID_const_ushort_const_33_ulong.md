# LPA::EsimManager::OnEs10cGetEidComplete(long,_GUID const &,ushort const (*)[33],ulong)

- ea: `0x18008d700`
- end: `0x18008df7a`
- name: `?OnEs10cGetEidComplete@EsimManager@LPA@@EEAAXJAEBU_GUID@@PEAY0CB@$$CBGK@Z`
- size: `2170`
- prototype: `void(LPA::EsimManager *__hidden this, int, const struct _GUID *, const unsigned __int16 (*)[33], unsigned int)`
- caller_count: `0`
- callee_count: `42`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800041fc`
- `0x180004da0`
- `0x18000517c`
- `0x18000df90`
- `0x180063668`
- `0x1800709e4`
- `0x180071650`
- `0x180071840`
- `0x180071a8c`
- `0x180081618`
- `0x1800817c8`
- `0x180081bdc`
- `0x180083a2c`
- `0x180083bb8`
- `0x180083e38`
- `0x180083f60`
- `0x1800858d4`
- `0x180085904`
- `0x180087e78`
- `0x180087ffc`
- `0x180088b48`
- `0x18008ae98`
- `0x18008aee4`
- `0x18008b70c`
- `0x18008c2d8`
- `0x18008c4e0`
- `0x18008d700`
- `0x1800925e4`
- `0x1800940dc`
- `0x1800944e0`
- `0x1800945bc`
- `0x1800945f0`
- `0x180094684`
- `0x1800955bc`
- `0x180095df0`
- `0x180095f60`
- `0x180095fd0`
- `0x18009733c`
- `0x1800d9b90`
- `0x1800eac08`
- `0x1800f1cd0`
- `0x180101010`

## string_xrefs

- `0x18008d777`: `LpaServiceEsimManager`
- `0x18008d875`: `LpaServiceEsimManager`
- `0x18008dbc2`: `LpaServiceEsimManager`
- `0x18008dc98`: `LpaServiceEsimManager`
- `0x18008dcf8`: `LpaServiceEsimManager`
- `0x18008dd6f`: `LpaServiceEsimManager`
- `0x18008de4c`: `LpaServiceEsimManager`
- `0x18008deef`: `LpaServiceEsimManager`
- `0x18008d770`: `LPA::EsimManager::OnEs10cGetEidComplete`
- `0x18008d86e`: `LPA::EsimManager::OnEs10cGetEidComplete`
- `0x18008dbbb`: `LPA::EsimManager::OnEs10cGetEidComplete`
- `0x18008dc8d`: `LPA::EsimManager::OnEs10cGetEidComplete`
- `0x18008dcf1`: `LPA::EsimManager::OnEs10cGetEidComplete`
- `0x18008dd68`: `LPA::EsimManager::OnEs10cGetEidComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall LPA::EsimManager::OnEs10cGetEidComplete(
        LPA::EsimManager *this,
        signed int a2,
        const struct _GUID *a3,
        wchar_t *a4,
        unsigned int a5)
{
  _QWORD *v9; // rbx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  LPA::EsimManager *v14; // r13
  char v15; // r15
  const char *v16; // rbx
  wchar_t *v17; // rsi
  signed int v18; // r8d
  int v19; // r9d
  LPA::EsimManager::EsimRecord *v20; // rdi
  LPA::EsimManager::EsimRecord *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  __int128 v26; // xmm6
  __int64 v27; // r14
  __int64 (__fastcall *v28)(__int64, const struct _GUID *, _QWORD, __int64, unsigned int *); // rsi
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rbx
  __int64 v32; // rax
  const char *v33; // rdi
  __int64 v34; // rbx
  const struct LPA_ESIM_INFO *EsimInfo; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  LPA::EsimManager::EsimRecord *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  int v43; // eax
  int v44; // [rsp+40h] [rbp-99h]
  unsigned int v45; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v46; // [rsp+5Ch] [rbp-7Dh] BYREF
  bool v47; // [rsp+60h] [rbp-79h] BYREF
  const char *v48; // [rsp+68h] [rbp-71h] BYREF
  _QWORD v49[2]; // [rsp+70h] [rbp-69h] BYREF
  __int64 v50; // [rsp+80h] [rbp-59h] BYREF
  LPA::EsimManager::EsimRecord *v51; // [rsp+88h] [rbp-51h] BYREF
  const char *EsimDetails; // [rsp+90h] [rbp-49h] BYREF
  std::_Ref_count_base *v53; // [rsp+98h] [rbp-41h]
  unsigned int v54; // [rsp+A0h] [rbp-39h] BYREF
  wchar_t *String2; // [rsp+A8h] [rbp-31h] BYREF
  const char *v56; // [rsp+B0h] [rbp-29h] BYREF
  std::_Ref_count_base *v57[2]; // [rsp+B8h] [rbp-21h] BYREF
  LPA::EsimManager::EsimRecord *v58; // [rsp+C8h] [rbp-11h] BYREF

  String2 = a4;
  v56 = (const char *)this;
  v9 = (_QWORD *)((char *)this + 224);
  v48 = (char *)this + 224;
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    (char *)this + 224,
    &v50,
    &a5);
  v13 = v50;
  if ( *v9 == v50 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v48 = (const char *)a4;
      EsimDetails = (const char *)a3;
      v46 = a5;
      v45 = a2;
      String2 = (wchar_t *)"LPA::EsimManager::OnEs10cGetEidComplete";
      v51 = (LPA::EsimManager::EsimRecord *)"LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)byte_18012DB11,
        v11,
        v12,
        (__int64)&v51,
        (__int64)&String2,
        (__int64)&v45,
        (__int64)&v46,
        (__int64)&EsimDetails,
        (__int64)&v48);
    }
    v14 = (LPA::EsimManager *)(v56 - 16);
  }
  else if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v49[0] = a3;
      v46 = a2;
      v57[0] = (std::_Ref_count_base *)"LPA::EsimManager::OnEs10cGetEidComplete";
      v48 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)"LpaServiceEsimManager",
        (unsigned int)&dword_18012D9CC,
        v11,
        v12,
        (__int64)&v48,
        (__int64)v57,
        (__int64)&v46,
        (__int64)v49);
    }
    v46 = *(_DWORD *)(*(_QWORD *)(v13 + 40) + 224LL);
    v33 = v56;
    v14 = (LPA::EsimManager *)(v56 - 16);
    LPA::EsimManager::TryFindEsimRecordBySlotId(v56 - 16, v49, &v46, a3);
    v34 = v49[0];
    if ( v49[0] != *((_QWORD *)v33 + 24) )
    {
      EsimInfo = LPA::EsimManager::EsimRecord::GetEsimInfo(*(LPA::EsimManager::EsimRecord **)(v49[0] + 48LL));
      if ( EsimInfo )
      {
        if ( (*(_BYTE *)EsimInfo & 1) == 0 )
        {
          v46 = 2;
          if ( (int)LPA::EsimManager::EsimRecord::GetTrueState(
                      *(LPA::EsimManager::EsimRecord **)(v34 + 48),
                      (enum LPAESIMSTATE *)&v46) >= 0
            && a2 != -2147467260
            && !v46 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              v49[0] = a3;
              v46 = a2;
              v57[0] = (std::_Ref_count_base *)"LPA::EsimManager::OnEs10cGetEidComplete";
              v48 = "LpaServiceEsimManager";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
                v36,
                (unsigned int)&word_18012D986,
                v37,
                v38,
                (__int64)&v48,
                (__int64)v57,
                (__int64)&v46,
                (__int64)v49);
            }
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
      }
      v39 = *(LPA::EsimManager::EsimRecord **)(v34 + 48);
      v40 = *((_QWORD *)v39 + 4);
      if ( (*(_BYTE *)(v40 + 4) & 1) == 0 || (*(_BYTE *)(v40 + 8) & 8) == 0 || *(_DWORD *)(v40 + 100) )
      {
        if ( LPA::EsimManager::EsimRecord::IsBusy(v39) && *(_DWORD *)(v41 + 100) == 3 )
        {
          v43 = *(_DWORD *)(v42 + 180);
          if ( v43 != -1 )
            *(_DWORD *)(v42 + 180) = v43 + 1;
        }
        *(_DWORD *)(v41 + 100) = 0;
        *(_DWORD *)(*(_QWORD *)(v42 + 32) + 8LL) |= 8u;
        *(_DWORD *)(*(_QWORD *)(v42 + 32) + 4LL) |= 1u;
        *(_BYTE *)(v42 + 3) = 1;
      }
    }
    LPA::EsimManager::CompleteOperation(v14);
  }
  else
  {
    v15 = 1;
    v46 = 0;
    v45 = *(_DWORD *)(*(_QWORD *)(v50 + 40) + 224LL);
    v14 = (LPA::EsimManager *)((char *)this - 16);
    LPA::EsimManager::TryFindEsimRecordBySlotId((char *)this - 16, &EsimDetails, &v45, a3);
    v16 = EsimDetails;
    if ( EsimDetails == *((const char **)this + 24) )
    {
      a2 = -2147023728;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v49[0] = String2;
        v45 = a5;
        v57[0] = (std::_Ref_count_base *)a3;
        EsimDetails = "LPA::EsimManager::OnEs10cGetEidComplete";
        v56 = "LpaServiceEsimManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)&unk_18012DA18,
          v11,
          v12,
          (__int64)&v56,
          (__int64)&EsimDetails,
          (__int64)v57,
          (__int64)&v45,
          (__int64)v49);
      }
    }
    else
    {
      v54 = 0;
      v49[0] = LPA::EsimManager::EsimRecord::GetEsimInfo(*((LPA::EsimManager::EsimRecord **)EsimDetails + 6));
      v17 = String2;
      v18 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, unsigned int *))(**((_QWORD **)this + 20) + 48LL))(
              *((_QWORD *)this + 20),
              String2,
              &v54);
      if ( v18 < 0 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          EsimDetails = (const char *)a3;
          v45 = v18;
          v51 = (LPA::EsimManager::EsimRecord *)"LPA::EsimManager::OnEs10cGetEidComplete";
          v57[0] = (std::_Ref_count_base *)"LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            (unsigned int)"LPA::EsimManager::OnEs10cGetEidComplete",
            (unsigned int)&dword_18012DAC4,
            v18,
            v19,
            (__int64)v57,
            (__int64)&v51,
            (__int64)&v45,
            (__int64)&EsimDetails);
        }
      }
      else
      {
        LPA::EsimManager::EsimRecord::SetEsimPolicy(*((LPA::EsimManager::EsimRecord **)v16 + 6), v54);
      }
      if ( v49[0] && (*(_BYTE *)v49[0] & 1) != 0 && wcsncmp_0((const wchar_t *)(v49[0] + 4LL), v17, 0x21u) )
      {
        v45 = 0;
        EsimDetails = (const char *)LPA::EsimManager::EsimRecord::GetEsimDetails(*((LPA::EsimManager::EsimRecord **)v16
                                                                                 + 6));
        std::make_unique<LPA::EsimManager::EsimRecord,,0>(&v51);
        v20 = v51;
        LPA::EsimManager::EsimRecord::Initialize(v51, a3);
        LPA::EsimManager::EsimRecord::SetImei(v20, (const unsigned __int16 *)(*((_QWORD *)v16 + 6) + 216LL));
        LPA::EsimManager::EsimRecord::SetEsimId(v20, (const unsigned __int16 (*const)[33])v17);
        if ( (int)LPA::EsimManager::EsimRecord::GetTrueState(
                    *((LPA::EsimManager::EsimRecord **)v16 + 6),
                    (enum LPAESIMSTATE *)&v45) >= 0 )
          LPA::EsimManager::EsimRecord::SetState(v20, v45);
        if ( (EsimDetails[4] & 0x10) != 0 )
          LPA::EsimManager::EsimRecord::SetActiveProfile(v20, (const unsigned __int16 (*)[21])(EsimDetails + 116));
        v45 = 0;
        if ( !LPA::Util::WwanHelper::TryQueryActiveSlotMapping(*((void *const *)this + 13), a3, &v45) )
        {
          v47 = *((_DWORD *)EsimDetails + 27) == v45;
          LPA::EsimManager::EsimRecord::SetEsimSlotId(v20, (const unsigned int *)EsimDetails + 27, &v47);
        }
        v21 = (LPA::EsimManager::EsimRecord *)*((_QWORD *)v16 + 6);
        v22 = *((_QWORD *)v21 + 4);
        if ( (*(_BYTE *)(v22 + 4) & 1) == 0 || (*(_BYTE *)(v22 + 8) & 8) == 0 || *(_DWORD *)(v22 + 100) != 3 )
        {
          if ( LPA::EsimManager::EsimRecord::IsBusy(v21) && *(_DWORD *)(v23 + 100) == 3 )
          {
            v25 = *(_DWORD *)(v24 + 180);
            if ( v25 != -1 )
              *(_DWORD *)(v24 + 180) = v25 + 1;
          }
          *(_DWORD *)(v23 + 100) = 3;
          *(_DWORD *)(*(_QWORD *)(v24 + 32) + 8LL) |= 8u;
          *(_DWORD *)(*(_QWORD *)(v24 + 32) + 4LL) |= 1u;
          *(_BYTE *)(v24 + 3) = 1;
        }
        LPA::EsimManager::CompleteOperation((LPA::EsimManager *)((char *)this - 16));
        LPA::EsimManager::ProcessAndBroadcastChanges((LPA::EsimManager *)((char *)this - 16), 0);
        v15 = 0;
        *(struct _GUID *)v57 = *a3;
        v51 = 0;
        v58 = v20;
        std::_Tree<std::_Tmap_traits<_GUID,std::unique_ptr<LPA::EsimManager::EsimRecord>,LPA::GuidComparator,std::allocator<std::pair<_GUID const,std::unique_ptr<LPA::EsimManager::EsimRecord>>>,1>>::_Emplace<std::pair<_GUID,std::unique_ptr<LPA::EsimManager::EsimRecord>>>(
          (_QWORD *)this + 24,
          (__int64)v49,
          (__int64)v57);
        std::unique_ptr<LPA::EsimManager::EsimRecord>::~unique_ptr<LPA::EsimManager::EsimRecord>(&v58);
        v16 = *(const char **)LPA::EsimManager::TryFindEsimRecordByEid((char *)this - 16, v49, v17, a3);
        std::unique_ptr<LPA::EsimManager::EsimRecord>::~unique_ptr<LPA::EsimManager::EsimRecord>(&v51);
        v13 = v50;
      }
      else
      {
        LPA::EsimManager::EsimRecord::SetEsimId(
          *((LPA::EsimManager::EsimRecord **)v16 + 6),
          (const unsigned __int16 (*const)[33])v17);
      }
      v26 = (__int128)*a3;
      std::wstring::wstring(v57, String2);
      *(_OWORD *)(*(_QWORD *)std::map<std::wstring,_GUID>::_Try_emplace<std::wstring,>((char *)this + 176, v49, v57)
                + 64LL) = v26;
      std::wstring::_Tidy_deallocate(v57);
      v45 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v16 + 6) + 32LL) + 108LL);
      LPA::EsimManager::AttemptToGetEuiccConfiguredData((LPA::EsimManager *)((char *)this - 16), a3, &v45);
      v45 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v16 + 6) + 32LL) + 108LL);
      LPA::EsimManager::AttemptToGetEuiccInfo2((LPA::EsimManager *)((char *)this - 16), a3, &v45);
      v27 = *((_QWORD *)this + 16);
      v28 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, __int64, unsigned int *))(*(_QWORD *)(v27 + 16) + 32LL);
      v49[0] = v56 + 72;
      std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(v56 + 72, &EsimDetails);
      v29 = std::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>(v57);
      a2 = v28(v27 + 16, a3, *(unsigned int *)(*(_QWORD *)(*((_QWORD *)v16 + 6) + 32LL) + 108LL), v29, &v46);
      v10 = (int)v53;
      if ( v53 )
        std::_Ref_count_base::_Decref(v53);
      if ( a2 < 0 )
      {
        if ( v15 )
        {
          LPA::EsimManager::CompleteOperation(v14);
          v15 = 0;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v49[0] = a3;
            v45 = a2;
            v57[0] = (std::_Ref_count_base *)"LPA::EsimManager::OnEs10cGetEidComplete";
            EsimDetails = "LpaServiceEsimManager";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              v10,
              (unsigned int)&byte_18012DA77,
              v11,
              v12,
              (__int64)&EsimDetails,
              (__int64)v57,
              (__int64)&v45,
              (__int64)v49);
          }
          v13 = v50;
        }
      }
      else if ( v15 )
      {
        LOBYTE(v44) = 0;
        LPA::EsimManager::TransferOperationToNewTransactionId(
          (_DWORD)v14,
          (unsigned int)&v50,
          (_DWORD)a3,
          0,
          0,
          0,
          0,
          v44,
          v46);
        v15 = 0;
      }
      else
      {
        v45 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v16 + 6) + 32LL) + 108LL);
        v30 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(v49[0], v57);
        v31 = (__int64 *)std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,unsigned long &,_GUID const &,unsigned long,0>(
                           (unsigned int)v49,
                           v30,
                           (unsigned int)&a5,
                           (_DWORD)a3,
                           (__int64)&v45);
        v32 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
                v48,
                &EsimDetails,
                &a5);
        std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
          (__int64 *)(*(_QWORD *)v32 + 40LL),
          v31);
        std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(v49);
        v10 = (int)v57[1];
        if ( v57[1] )
          std::_Ref_count_base::_Decref(v57[1]);
      }
    }
    if ( v15 )
      std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>,0>>::_Erase_unchecked(
        v48,
        v13);
  }
  if ( a2 < 0 && (unsigned int)CallbackContext > 2 )
  {
    v49[0] = a3;
    v46 = a2;
    v57[0] = (std::_Ref_count_base *)"LPA::EsimManager::OnEs10cGetEidComplete";
    v48 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v10,
      (unsigned int)&word_18012D93E,
      v11,
      v12,
      (__int64)&v48,
      (__int64)v57,
      (__int64)&v46,
      (__int64)v49);
  }
  LPA::EsimManager::ProcessAndBroadcastChanges(v14, 0);
}

```

## disassembly

```asm
0x18008d700  mov     rax, rsp
0x18008d703  mov     [rax+10h], rbx
0x18008d707  push    rbp
0x18008d708  push    rsi
0x18008d709  push    rdi
0x18008d70a  push    r12
0x18008d70c  push    r13
0x18008d70e  push    r14
0x18008d710  push    r15
0x18008d712  lea     rbp, [rax-57h]
0x18008d716  sub     rsp, 0F0h
0x18008d71d  movaps  xmmword ptr [rax-48h], xmm6
0x18008d721  mov     rax, cs:__security_cookie
0x18008d728  xor     rax, rsp
0x18008d72b  mov     [rbp+4Fh+var_50], rax
0x18008d72f  mov     r15, r9
0x18008d732  mov     [rbp+4Fh+String2], r9
0x18008d736  mov     r12, r8
0x18008d739  mov     esi, edx
0x18008d73b  mov     r14, rcx
0x18008d73e  mov     [rbp+4Fh+var_78], rcx
0x18008d742  lea     rbx, [rcx+0E0h]
0x18008d749  mov     [rbp+4Fh+var_C0], rbx
0x18008d74d  lea     r8, [rbp+4Fh+arg_20]
0x18008d751  lea     rdx, [rbp+4Fh+var_A8]
0x18008d755  mov     rcx, rbx
0x18008d758  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18008d75d  mov     rdi, [rbp+4Fh+var_A8]
0x18008d761  cmp     [rbx], rdi
0x18008d764  jnz     loc_18008D7ED
0x18008d76a  mov     eax, cs:CallbackContext
0x18008d770  lea     r14, aLpaEsimmanager_34; "LPA::EsimManager::OnEs10cGetEidComplete"
0x18008d777  lea     rbx, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d77e  cmp     eax, 3
0x18008d781  jbe     short loc_18008D7E0
0x18008d783  mov     [rbp+4Fh+var_C0], r15
0x18008d787  mov     [rbp+4Fh+var_98], r12
0x18008d78b  mov     eax, [rbp+4Fh+arg_20]
0x18008d78e  mov     [rbp+4Fh+var_CC], eax
0x18008d791  mov     [rsp+120h+var_D0], esi
0x18008d795  mov     [rbp+4Fh+String2], r14
0x18008d799  mov     [rbp+4Fh+var_A0], rbx
0x18008d79d  lea     rax, [rbp+4Fh+var_C0]
0x18008d7a1  mov     qword ptr [rsp+120h+var_D8], rax
0x18008d7a6  lea     rax, [rbp+4Fh+var_98]
0x18008d7aa  mov     [rsp+120h+var_E0], rax
0x18008d7af  lea     rax, [rbp+4Fh+var_CC]
0x18008d7b3  mov     [rsp+120h+var_E8], rax
0x18008d7b8  lea     rax, [rsp+120h+var_D0]
0x18008d7bd  mov     [rsp+120h+var_F0], rax
0x18008d7c2  lea     rax, [rbp+4Fh+String2]
0x18008d7c6  mov     [rsp+120h+var_F8], rax
0x18008d7cb  lea     rax, [rbp+4Fh+var_A0]
0x18008d7cf  mov     [rsp+120h+var_100], rax
0x18008d7d4  lea     rdx, byte_18012DB11
0x18008d7db  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18008d7e0  mov     r13, [rbp+4Fh+var_78]
0x18008d7e4  add     r13, 0FFFFFFFFFFFFFFF0h
0x18008d7e8  jmp     loc_18008DEF6
0x18008d7ed  test    esi, esi
0x18008d7ef  js      loc_18008DD62
0x18008d7f5  mov     r15d, 1
0x18008d7fb  mov     [rbp+4Fh+var_CC], 0
0x18008d802  mov     rax, [rdi+28h]
0x18008d806  mov     ecx, [rax+0E0h]
0x18008d80c  mov     [rsp+120h+var_D0], ecx
0x18008d810  lea     r13, [r14-10h]
0x18008d814  mov     r9, r12
0x18008d817  lea     r8, [rsp+120h+var_D0]
0x18008d81c  lea     rdx, [rbp+4Fh+var_98]
0x18008d820  mov     rcx, r13
0x18008d823  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008d828  mov     rbx, [rbp+4Fh+var_98]
0x18008d82c  cmp     rbx, [r14+0C0h]
0x18008d833  jz      loc_18008DCE6
0x18008d839  mov     [rbp+4Fh+var_88], 0
0x18008d840  mov     rcx, [rbx+30h]; this
0x18008d844  call    ?GetEsimInfo@EsimRecord@EsimManager@LPA@@QEBAPEBULPA_ESIM_INFO@@XZ; LPA::EsimManager::EsimRecord::GetEsimInfo(void)
0x18008d849  mov     [rbp+4Fh+var_B8], rax
0x18008d84d  mov     rcx, [r14+0A0h]
0x18008d854  mov     rdx, [rcx]
0x18008d857  mov     rax, [rdx+30h]
0x18008d85b  lea     r8, [rbp+4Fh+var_88]
0x18008d85f  mov     rsi, [rbp+4Fh+String2]
0x18008d863  mov     rdx, rsi
0x18008d866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d86b  mov     r8d, eax
0x18008d86e  lea     rcx, aLpaEsimmanager_34; "LPA::EsimManager::OnEs10cGetEidComplete"
0x18008d875  lea     rdx, aLpaserviceesim; "LpaServiceEsimManager"
0x18008d87c  test    eax, eax
0x18008d87e  js      short loc_18008D88E
0x18008d880  mov     edx, [rbp+4Fh+var_88]; unsigned int
0x18008d883  mov     rcx, [rbx+30h]; this
0x18008d887  call    ?SetEsimPolicy@EsimRecord@EsimManager@LPA@@QEAAXK@Z; LPA::EsimManager::EsimRecord::SetEsimPolicy(ulong)
0x18008d88c  jmp     short loc_18008D8DB
0x18008d88e  mov     eax, cs:CallbackContext
0x18008d894  cmp     eax, 4
0x18008d897  jbe     short loc_18008D8DB
0x18008d899  mov     [rbp+4Fh+var_98], r12
0x18008d89d  mov     [rsp+120h+var_D0], r8d
0x18008d8a2  mov     [rbp+4Fh+var_A0], rcx
0x18008d8a6  mov     [rbp+4Fh+var_70], rdx
0x18008d8aa  lea     rax, [rbp+4Fh+var_98]
0x18008d8ae  mov     [rsp+120h+var_E8], rax
0x18008d8b3  lea     rax, [rsp+120h+var_D0]
0x18008d8b8  mov     [rsp+120h+var_F0], rax
0x18008d8bd  lea     rax, [rbp+4Fh+var_A0]
0x18008d8c1  mov     [rsp+120h+var_F8], rax
0x18008d8c6  lea     rax, [rbp+4Fh+var_70]
0x18008d8ca  mov     [rsp+120h+var_100], rax
0x18008d8cf  lea     rdx, dword_18012DAC4
0x18008d8d6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008d8db  mov     rax, [rbp+4Fh+var_B8]
0x18008d8df  test    rax, rax
0x18008d8e2  jz      loc_18008DA8E
0x18008d8e8  test    [rax], r15b
0x18008d8eb  jz      loc_18008DA8E
0x18008d8f1  lea     rcx, [rax+4]; String1
0x18008d8f5  mov     r8d, 21h ; '!'; MaxCount
0x18008d8fb  mov     rdx, rsi; String2
0x18008d8fe  call    wcsncmp_0
0x18008d903  test    eax, eax
0x18008d905  jz      loc_18008DA8E
0x18008d90b  mov     [rsp+120h+var_D0], 0
0x18008d913  mov     rcx, [rbx+30h]; this
0x18008d917  call    ?GetEsimDetails@EsimRecord@EsimManager@LPA@@QEBAPEBULPA_ESIM_DETAILS@@XZ; LPA::EsimManager::EsimRecord::GetEsimDetails(void)
0x18008d91c  mov     [rbp+4Fh+var_98], rax
0x18008d920  lea     rcx, [rbp+4Fh+var_A0]
0x18008d924  call    ??$make_unique@VEsimRecord@EsimManager@LPA@@$$V$0A@@std@@YA?AV?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@0@XZ; std::make_unique<LPA::EsimManager::EsimRecord,,0>(void)
0x18008d929  nop
0x18008d92a  mov     rdx, r12; struct _GUID *
0x18008d92d  mov     rdi, [rbp+4Fh+var_A0]
0x18008d931  mov     rcx, rdi; this
0x18008d934  call    ?Initialize@EsimRecord@EsimManager@LPA@@QEAAXAEBU_GUID@@@Z; LPA::EsimManager::EsimRecord::Initialize(_GUID const &)
0x18008d939  mov     rdx, [rbx+30h]
0x18008d93d  add     rdx, 0D8h; unsigned __int16 *
0x18008d944  mov     rcx, rdi; this
0x18008d947  call    ?SetImei@EsimRecord@EsimManager@LPA@@QEAAXPEBG@Z; LPA::EsimManager::EsimRecord::SetImei(ushort const *)
0x18008d94c  mov     rdx, rsi; unsigned __int16 (*)[33]
0x18008d94f  mov     rcx, rdi; this
0x18008d952  call    ?SetEsimId@EsimRecord@EsimManager@LPA@@QEAAXQEAY0CB@$$CBG@Z; LPA::EsimManager::EsimRecord::SetEsimId(ushort const (* const)[33])
0x18008d957  lea     rdx, [rsp+120h+var_D0]; enum LPAESIMSTATE *
0x18008d95c  mov     rcx, [rbx+30h]; this
0x18008d960  call    ?GetTrueState@EsimRecord@EsimManager@LPA@@QEBAJAEAW4LPAESIMSTATE@@@Z; LPA::EsimManager::EsimRecord::GetTrueState(LPAESIMSTATE &)
0x18008d965  test    eax, eax
0x18008d967  js      short loc_18008D975
0x18008d969  mov     edx, [rsp+120h+var_D0]
0x18008d96d  mov     rcx, rdi
0x18008d970  call    ?SetState@EsimRecord@EsimManager@LPA@@QEAAXW4LPAESIMSTATE@@@Z; LPA::EsimManager::EsimRecord::SetState(LPAESIMSTATE)
0x18008d975  mov     rax, [rbp+4Fh+var_98]
0x18008d979  test    byte ptr [rax+4], 10h
0x18008d97d  jz      short loc_18008D98B
0x18008d97f  lea     rdx, [rax+74h]; unsigned __int16 (*)[21]
0x18008d983  mov     rcx, rdi; this
0x18008d986  call    ?SetActiveProfile@EsimRecord@EsimManager@LPA@@QEAAXAEAY0BF@$$CBG@Z; LPA::EsimManager::EsimRecord::SetActiveProfile(ushort const (&)[21])
0x18008d98b  mov     [rsp+120h+var_D0], 0
0x18008d993  lea     r8, [rsp+120h+var_D0]; unsigned int *
0x18008d998  mov     rdx, r12; struct _GUID *
0x18008d99b  mov     rcx, [r14+68h]; void *
0x18008d99f  call    ?TryQueryActiveSlotMapping@WwanHelper@Util@LPA@@SAKQEAXAEBU_GUID@@AEAK@Z; LPA::Util::WwanHelper::TryQueryActiveSlotMapping(void * const,_GUID const &,ulong &)
0x18008d9a4  test    eax, eax
0x18008d9a6  jnz     short loc_18008D9C6
0x18008d9a8  mov     rdx, [rbp+4Fh+var_98]
0x18008d9ac  add     rdx, 6Ch ; 'l'; unsigned int *
0x18008d9b0  mov     eax, [rsp+120h+var_D0]
0x18008d9b4  cmp     [rdx], eax
0x18008d9b6  setz    [rbp+4Fh+var_C8]
0x18008d9ba  lea     r8, [rbp+4Fh+var_C8]; bool *
0x18008d9be  mov     rcx, rdi; this
0x18008d9c1  call    ?SetEsimSlotId@EsimRecord@EsimManager@LPA@@QEAAXAEBKAEB_N@Z; LPA::EsimManager::EsimRecord::SetEsimSlotId(ulong const &,bool const &)
0x18008d9c6  mov     rcx, [rbx+30h]; this
0x18008d9ca  mov     rdx, [rcx+20h]
0x18008d9ce  test    [rdx+4], r15b
0x18008d9d2  jz      short loc_18008D9E0
0x18008d9d4  test    byte ptr [rdx+8], 8
0x18008d9d8  jz      short loc_18008D9E0
0x18008d9da  cmp     dword ptr [rdx+64h], 3
0x18008d9de  jz      short loc_18008DA1D
0x18008d9e0  call    ?IsBusy@EsimRecord@EsimManager@LPA@@QEBA_NXZ; LPA::EsimManager::EsimRecord::IsBusy(void)
0x18008d9e5  test    al, al
0x18008d9e7  jz      short loc_18008DA02
0x18008d9e9  cmp     dword ptr [rdx+64h], 3
0x18008d9ed  jnz     short loc_18008DA02
0x18008d9ef  mov     eax, [rcx+0B4h]
0x18008d9f5  cmp     eax, 0FFFFFFFFh
0x18008d9f8  jnb     short loc_18008DA02
0x18008d9fa  inc     eax
0x18008d9fc  mov     [rcx+0B4h], eax
0x18008da02  mov     dword ptr [rdx+64h], 3
0x18008da09  mov     rax, [rcx+20h]
0x18008da0d  or      dword ptr [rax+8], 8
0x18008da11  mov     rax, [rcx+20h]
0x18008da15  or      [rax+4], r15d
0x18008da19  mov     [rcx+3], r15b
0x18008da1d  lea     rdx, [rbp+4Fh+var_A8]
0x18008da21  mov     rcx, r13; this
0x18008da24  call    ?CompleteOperation@EsimManager@LPA@@AEAAXAEAV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@@Z; LPA::EsimManager::CompleteOperation(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &)
0x18008da29  xor     edx, edx; bool
0x18008da2b  mov     rcx, r13; this
0x18008da2e  call    ?ProcessAndBroadcastChanges@EsimManager@LPA@@AEAAX_N@Z; LPA::EsimManager::ProcessAndBroadcastChanges(bool)
0x18008da33  xor     r15b, r15b
0x18008da36  movups  xmm0, xmmword ptr [r12]
0x18008da3b  movdqu  xmmword ptr [rbp+4Fh+var_70], xmm0
0x18008da40  mov     [rbp+4Fh+var_A0], 0
0x18008da48  mov     [rbp+4Fh+var_60], rdi
0x18008da4c  lea     r8, [rbp+4Fh+var_70]
0x18008da50  lea     rdx, [rbp+4Fh+var_B8]
0x18008da54  lea     rcx, [r14+0C0h]
0x18008da5b  call    ??$_Emplace@U?$pair@U_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@UGuidComparator@LPA@@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@3@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::unique_ptr<LPA::EsimManager::EsimRecord>,LPA::GuidComparator,std::allocator<std::pair<_GUID const,std::unique_ptr<LPA::EsimManager::EsimRecord>>>,1>>::_Emplace<std::pair<_GUID,std::unique_ptr<LPA::EsimManager::EsimRecord>>>(std::pair<_GUID,std::unique_ptr<LPA::EsimManager::EsimRecord>> &&)
0x18008da60  nop
0x18008da61  lea     rcx, [rbp+4Fh+var_60]
0x18008da65  call    ??1?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EsimManager::EsimRecord>::~unique_ptr<LPA::EsimManager::EsimRecord>(void)
0x18008da6a  mov     r9, r12
0x18008da6d  mov     r8, rsi
0x18008da70  lea     rdx, [rbp+4Fh+var_B8]
0x18008da74  mov     rcx, r13
0x18008da77  call    ?TryFindEsimRecordByEid@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@PEAY0CB@$$CBGAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordByEid(ushort const (*)[33],_GUID const &)
0x18008da7c  mov     rbx, [rax]
0x18008da7f  lea     rcx, [rbp+4Fh+var_A0]
0x18008da83  call    ??1?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EsimManager::EsimRecord>::~unique_ptr<LPA::EsimManager::EsimRecord>(void)
0x18008da88  mov     rdi, [rbp+4Fh+var_A8]
0x18008da8c  jmp     short loc_18008DA9A
0x18008da8e  mov     rdx, rsi; unsigned __int16 (*)[33]
0x18008da91  mov     rcx, [rbx+30h]; this
0x18008da95  call    ?SetEsimId@EsimRecord@EsimManager@LPA@@QEAAXQEAY0CB@$$CBG@Z; LPA::EsimManager::EsimRecord::SetEsimId(ushort const (* const)[33])
0x18008da9a  movups  xmm6, xmmword ptr [r12]
0x18008da9f  mov     rdx, [rbp+4Fh+String2]
0x18008daa3  lea     rcx, [rbp+4Fh+var_70]
0x18008daa7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008daac  nop
0x18008daad  lea     r8, [rbp+4Fh+var_70]
0x18008dab1  lea     rdx, [rbp+4Fh+var_B8]
0x18008dab5  lea     rcx, [r14+0B0h]
0x18008dabc  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_GUID>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18008dac1  mov     rcx, [rax]
0x18008dac4  movdqu  xmmword ptr [rcx+40h], xmm6
0x18008dac9  lea     rcx, [rbp+4Fh+var_70]
0x18008dacd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008dad2  mov     rax, [rbx+30h]
0x18008dad6  mov     rcx, [rax+20h]
0x18008dada  mov     eax, [rcx+6Ch]
0x18008dadd  mov     [rsp+120h+var_D0], eax
0x18008dae1  lea     r8, [rsp+120h+var_D0]; unsigned int *
0x18008dae6  mov     rdx, r12; struct _GUID *
0x18008dae9  mov     rcx, r13; this
0x18008daec  call    ?AttemptToGetEuiccConfiguredData@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK@Z; LPA::EsimManager::AttemptToGetEuiccConfiguredData(_GUID const &,ulong const &)
0x18008daf1  mov     rax, [rbx+30h]
0x18008daf5  mov     rcx, [rax+20h]
0x18008daf9  mov     eax, [rcx+6Ch]
0x18008dafc  mov     [rsp+120h+var_D0], eax
0x18008db00  lea     r8, [rsp+120h+var_D0]; unsigned int *
0x18008db05  mov     rdx, r12; struct _GUID *
0x18008db08  mov     rcx, r13; this
0x18008db0b  call    ?AttemptToGetEuiccInfo2@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK@Z; LPA::EsimManager::AttemptToGetEuiccInfo2(_GUID const &,ulong const &)
0x18008db10  mov     r14, [r14+80h]
0x18008db17  mov     rax, [r14+10h]
0x18008db1b  mov     rsi, [rax+20h]
0x18008db1f  mov     rax, [rbp+4Fh+var_78]
0x18008db23  add     rax, 48h ; 'H'
0x18008db27  mov     [rbp+4Fh+var_B8], rax
0x18008db2b  lea     rdx, [rbp+4Fh+var_98]
0x18008db2f  mov     rcx, rax
0x18008db32  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18008db37  nop
0x18008db38  mov     rdx, rax
0x18008db3b  lea     rcx, [rbp+4Fh+var_70]
0x18008db3f  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UApduHelperEs10cCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>::weak_ptr<LPA::ApduHelperEs10cCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x18008db44  mov     rdx, [rbx+30h]
0x18008db48  mov     r8, [rdx+20h]
0x18008db4c  lea     rcx, [rbp+4Fh+var_CC]
0x18008db50  mov     [rsp+120h+var_100], rcx
0x18008db55  mov     r9, rax
0x18008db58  mov     r8d, [r8+6Ch]
0x18008db5c  mov     rdx, r12
0x18008db5f  lea     rcx, [r14+10h]
0x18008db63  mov     rax, rsi
0x18008db66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008db6b  mov     esi, eax
0x18008db6d  mov     rcx, [rbp+4Fh+var_90]; this
0x18008db71  xor     r14d, r14d
0x18008db74  test    rcx, rcx
0x18008db77  jz      short loc_18008DB7E
0x18008db79  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008db7e  test    esi, esi
0x18008db80  js      loc_18008DC62
0x18008db86  test    r15b, r15b
0x18008db89  jz      short loc_18008DBE3
0x18008db8b  mov     eax, [rbp+4Fh+var_CC]
0x18008db8e  mov     dword ptr [rsp+120h+var_E0], eax
0x18008db92  mov     byte ptr [rsp+120h+var_E8], r14b
0x18008db97  mov     byte ptr [rsp+120h+var_F0], r14b
0x18008db9c  mov     byte ptr [rsp+120h+var_F8], r14b
0x18008dba1  mov     byte ptr [rsp+120h+var_100], r14b
0x18008dba6  xor     r9d, r9d
0x18008dba9  mov     r8, r12
0x18008dbac  lea     rdx, [rbp+4Fh+var_A8]
0x18008dbb0  mov     rcx, r13
0x18008dbb3  call    ?TransferOperationToNewTransactionId@EsimManager@LPA@@AEAAXAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBU_GUID@@_N2222K@Z; LPA::EsimManager::TransferOperationToNewTransactionId(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>>> &,_GUID const &,bool,bool,bool,bool,bool,ulong)
0x18008dbb8  mov     r15b, r14b
0x18008dbbb  lea     r14, aLpaEsimmanager_34; "LPA::EsimManager::OnEs10cGetEidComplete"
  ... truncated ...
```
