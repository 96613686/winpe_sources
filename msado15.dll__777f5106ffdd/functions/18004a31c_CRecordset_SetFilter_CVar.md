# CRecordset::SetFilter(CVar &)

- ea: `0x18004a31c`
- end: `0x18004b30b`
- name: `?SetFilter@CRecordset@@QEAAJAEAVCVar@@@Z`
- size: `4079`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, struct CVar *)`
- caller_count: `3`
- callee_count: `44`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800609e0`
- `0x180096a70`
- `0x1800b9fc0`

## callees

- `0x180001514`
- `0x180006310`
- `0x180006890`
- `0x180007630`
- `0x1800098a0`
- `0x18000a320`
- `0x180010ec0`
- `0x180011230`
- `0x180011530`
- `0x180018788`
- `0x180020e20`
- `0x180020fc0`
- `0x1800265d0`
- `0x180029230`
- `0x18003d270`
- `0x18003ec80`
- `0x18003f430`
- `0x180042a04`
- `0x180045760`
- `0x18004a31c`
- `0x18004b314`
- `0x18004b368`
- `0x18004b5f4`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x18004f370`
- `0x180052080`
- `0x180053634`
- `0x180053f50`
- `0x180055e08`
- `0x180055ec4`
- `0x180056e84`
- `0x18006a22c`
- `0x18009c178`
- `0x1800a8e40`
- `0x1800a95b0`
- `0x1800a9a3c`
- `0x1800ad134`
- `0x1800ad2f0`
- `0x1800c8f34`
- `0x1800cd4c4`
- `0x1800cd4e0`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18004a3b1`
- `KERNEL32!TlsSetValue` at `0x18004b2d9`
- `KERNEL32!TlsSetValue` at `0x18004a3b1`
- `KERNEL32!TlsSetValue` at `0x18004b2d9`
- `KERNEL32!TlsGetValue` at `0x18004a362`
- `KERNEL32!TlsGetValue` at `0x18004a362`
- `ole32!CoTaskMemFree` at `0x18004b1bd`
- `ole32!CoTaskMemFree` at `0x18004b1bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a835`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a835`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004b2a1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004b2a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::SetFilter(CRecordset *this, struct CVar *a2)
{
  _DWORD *Value; // rax
  unsigned int BidObjectID; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  enum FilterGroupEnum v9; // r14d
  __int16 v10; // dx
  __int64 v11; // rcx
  _QWORD *v12; // r14
  int v13; // eax
  __int16 *v14; // rax
  int IsValidFilterGroup; // eax
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  unsigned __int8 **v20; // r12
  CRecordset *v21; // rcx
  char *Chapter; // rbx
  __int64 v23; // r8
  unsigned int v24; // eax
  unsigned __int64 RecoveryHRow; // rbx
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // edx
  unsigned __int8 **v29; // rcx
  unsigned __int8 **v30; // rbx
  unsigned __int8 **v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rcx
  int v34; // edx
  CSafeArray *v35; // rcx
  unsigned int v36; // eax
  unsigned __int8 **v37; // r12
  void *v38; // rbx
  int v39; // r13d
  unsigned int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r9
  __int64 v43; // rdx
  void *v44; // rbx
  unsigned __int8 **v45; // rdx
  char *v46; // rbx
  unsigned int v47; // ebx
  _DWORD *v49; // rax
  IErrorInfo *v50; // rdx
  __int64 **v52; // [rsp+20h] [rbp-E0h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-C0h] BYREF
  int v54; // [rsp+48h] [rbp-B8h]
  __int64 v55; // [rsp+50h] [rbp-B0h]
  int v56; // [rsp+58h] [rbp-A8h]
  __int16 v57; // [rsp+5Ch] [rbp-A4h]
  char v58; // [rsp+5Eh] [rbp-A2h]
  unsigned __int64 v59; // [rsp+60h] [rbp-A0h]
  int v60; // [rsp+68h] [rbp-98h]
  int v61; // [rsp+6Ch] [rbp-94h]
  void *v62; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  struct tagVARIANT v64; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v65[24]; // [rsp+A0h] [rbp-60h] BYREF
  struct CChapter *v66; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int8 **v67; // [rsp+178h] [rbp+78h] BYREF
  void *v68; // [rsp+180h] [rbp+80h] BYREF
  void *Src; // [rsp+188h] [rbp+88h] BYREF

  v59 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v61 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v60 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v54 = 1;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  if ( (*((_BYTE *)a2 + 8) & 4) == 0 )
  {
    v60 = -2147024882;
    if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
    {
      if ( v60 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_184;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v52) = 12116;
          v6 = 12406793;
LABEL_10:
          bidTraceW(off_18012A208[0], v6, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", BidObjectID, v52);
          goto LABEL_184;
        }
        v7 = 12116;
        v8 = 12406793;
        goto LABEL_12;
      }
    }
  }
  v9 = -1;
  v10 = *((_WORD *)a2 + 8);
  if ( (v10 & 0xBFFF) == 2 )
  {
    v14 = (__int16 *)((char *)a2 + 24);
    if ( (v10 & 0x4000) != 0 )
      v14 = *(__int16 **)v14;
    v9 = *v14;
    IsValidFilterGroup = CRecordset::IsValidFilterGroup((CRecordset *)((v10 & 0xBFFFu) - 2), v9);
    if ( (unsigned int)CContext::ArgFailed((CContext *)&TlsValue, IsValidFilterGroup) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_184;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v52) = 12133;
        v6 = 12424201;
        goto LABEL_10;
      }
      v7 = 12133;
      v8 = 12424201;
      goto LABEL_12;
    }
    goto LABEL_34;
  }
  if ( (v10 & 0xBFFF) == 3 )
  {
    v12 = (_QWORD *)((char *)a2 + 24);
    if ( (v10 & 0x4000) != 0 )
      v12 = (_QWORD *)*v12;
    v9 = *(_DWORD *)v12;
    v13 = CRecordset::IsValidFilterGroup((CRecordset *)((v10 & 0xBFFFu) - 3), v9);
    if ( (unsigned int)CContext::ArgFailed((CContext *)&TlsValue, v13) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v52) = 12129;
          v6 = 12420105;
          goto LABEL_10;
        }
        v7 = 12129;
        v8 = 12420105;
        goto LABEL_12;
      }
      goto LABEL_184;
    }
LABEL_34:
    if ( v9 != -1 )
      goto LABEL_40;
    goto LABEL_35;
  }
  v11 = (v10 & 0xBFFFu) - 8;
  if ( (v10 & 0xBFFF) == 8 )
  {
    v9 = adFilterPredicate;
    goto LABEL_40;
  }
  v11 = (v10 & 0xBFFFu) - 8204;
  if ( (v10 & 0xBFFF) == 0x200C || (v10 & 0xBFFF) == 0x2011 )
  {
    v9 = adFilterFetchedRecords;
    goto LABEL_40;
  }
LABEL_35:
  LODWORD(v66) = -2146825287;
  if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v66) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_184;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v52) = 12142;
      v6 = 12433417;
      goto LABEL_10;
    }
    v7 = 12142;
    v8 = 12433417;
    goto LABEL_12;
  }
LABEL_40:
  if ( (unsigned int)(v9 - 1) > 2 && v9 != adFilterConflictingRecords )
  {
    v67 = 0;
    if ( v9 != adFilterPredicate )
      goto LABEL_46;
    if ( (*((_WORD *)a2 + 8) & 0xBFFF) == 8 )
    {
      if ( !CSysString::GetLength(*((CSysString **)a2 + 5), 0) )
        v9 = adFilterNone;
LABEL_46:
      v60 = CRecordset::CopyStack(v11, *((_QWORD *)this + 186), &v67, 2);
      if ( v60 < 0 )
      {
        CContext::PushError((CContext *)&TlsValue);
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_79;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v17 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 12590089, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v17, 12295);
          goto LABEL_79;
        }
        v18 = 12295;
        v19 = 12590089;
        goto LABEL_83;
      }
      v20 = v67;
      Chapter = (char *)CRecordset::FindChapter(v16, v67, 2);
      v66 = (struct CChapter *)Chapter;
      if ( Chapter )
      {
        if ( v9 == adFilterNone )
        {
          CRecordset::DeleteChapter(v21, (struct CChapter **)&v67, &v66);
          v20 = v67;
          Chapter = (char *)v66;
        }
      }
      else if ( v9 == adFilterPredicate )
      {
        LODWORD(v66) = CRecordset::InsertChapter(v21, &v67, v23);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_79;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            v24 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(off_18012A208[0], 12604425, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v24, 12309);
            goto LABEL_79;
          }
          v18 = 12309;
          v19 = 12604425;
          goto LABEL_83;
        }
        v20 = v67;
        Chapter = (char *)v67;
      }
      else
      {
        Chapter = 0;
      }
      if ( Chapter )
      {
        if ( v9 )
        {
          CSysString::operator=(Chapter + 16, *((_QWORD *)a2 + 5));
          if ( (unsigned int)CContext::StringFailed((CContext *)&TlsValue, (const struct CSysString *)(Chapter + 16)) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_79;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v27 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              bidTraceW(off_18012A208[0], 12621833, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v27, 12326);
              goto LABEL_79;
            }
            v18 = 12326;
            v19 = 12621833;
            goto LABEL_83;
          }
        }
        else
        {
          SysFreeString(*((BSTR *)Chapter + 2));
          *((_QWORD *)Chapter + 2) = 0;
        }
      }
      if ( *((_DWORD *)this + 315) )
      {
        RecoveryHRow = CRecordset::GetRecoveryHRow(this);
        CRecordset::ReleaseCurrentGroup(this, 0);
        CRecordset::ReleaseAffectedGroup(this, 0);
        LODWORD(v66) = CRecordset::ApplyChapters(this, (struct CChapter *)v20);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
        {
          CRecordset::RecoverPosition(this, RecoveryHRow, 0);
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_79;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            v26 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(off_18012A208[0], 12639241, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v26, 12343);
            goto LABEL_79;
          }
          v18 = 12343;
          v19 = 12639241;
          goto LABEL_83;
        }
        CRecordset::ReleaseRecoveryHRow(this, RecoveryHRow);
      }
      v31 = (unsigned __int8 **)*((_QWORD *)this + 186);
      *((_QWORD *)this + 186) = v20;
      v67 = v31;
      if ( *((_DWORD *)this + 315) )
      {
        LODWORD(v66) = CRecordset::_MoveFirst(this, 1, 1);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
            {
              v18 = 12357;
              v19 = 12653577;
LABEL_83:
              bidTraceW(off_18012A208[0], v19, L"<CRecordset::SetFilter|ADO|ERR>  line %d\n", v18);
              goto LABEL_79;
            }
            v32 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(off_18012A208[0], 12653577, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v32, 12357);
          }
        }
      }
LABEL_79:
      CRecordset::ReleaseChapters(this, &v67, 2);
      v29 = v67;
      if ( v67 )
      {
        do
        {
          v30 = (unsigned __int8 **)v29[4];
          CChapter::`scalar deleting destructor'((CChapter *)v29, v28);
          v29 = v30;
        }
        while ( v30 );
      }
      goto LABEL_184;
    }
    LODWORD(v66) = -2146825287;
    if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
      goto LABEL_46;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_184;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v52) = 12289;
      v6 = 12583945;
      goto LABEL_10;
    }
    v7 = 12289;
    v8 = 12583945;
LABEL_12:
    bidTraceW(off_18012A208[0], v8, L"<CRecordset::SetFilter|ADO|ERR>  line %d\n", v7);
    goto LABEL_184;
  }
  v63 = 0;
  if ( (unsigned int)CContext::FailIfClosed((CContext *)&TlsValue, *((_DWORD *)this + 315)) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_184;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v52) = 12153;
      v6 = 12444681;
      goto LABEL_10;
    }
    v7 = 12153;
    v8 = 12444681;
    goto LABEL_12;
  }
  if ( v9 == adFilterPendingRecords )
  {
    v67 = 0;
    Src = 0;
    v62 = 0;
    v68 = 0;
    LODWORD(v66) = CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::HRCheck((char *)this + 432);
    if ( (unsigned int)CContext::FailedDescription((CContext *)&TlsValue, (const int *)&v66, 0x271Cu) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v40 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v52) = 12169;
          v41 = 12461065;
LABEL_168:
          bidTraceW(off_18012A208[0], v41, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v40, v52);
          goto LABEL_171;
        }
        v42 = 12169;
        v43 = 12461065;
        goto LABEL_170;
      }
    }
    else
    {
      LODWORD(v66) = CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(
                       (char *)this + 432,
                       &v68);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            v40 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            LODWORD(v52) = 12172;
            v41 = 12464137;
            goto LABEL_168;
          }
          v42 = 12172;
          v43 = 12464137;
LABEL_170:
          bidTraceW(off_18012A208[0], v43, L"<CRecordset::SetFilter|ADO|ERR>  line %d\n", v42);
        }
      }
      else
      {
        v44 = v68;
        LODWORD(v66) = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, unsigned __int8 ***, _QWORD, _QWORD))(*(_QWORD *)v68 + 56LL))(
                         v68,
                         *(_QWORD *)(*((_QWORD *)this + 186) + 8LL),
                         7,
                         &v67,
                         0,
                         0);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v40 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v52) = 12176;
              v41 = 12468233;
              goto LABEL_168;
            }
            v42 = 12176;
            v43 = 12468233;
            goto LABEL_170;
          }
        }
        else
        {
          LODWORD(v66) = CRecordset::PrepareForFetch(this, (__int64)v67, (unsigned __int64 **)&v62, 1);
          if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
          {
            v45 = v67;
            if ( v67 )
            {
              LODWORD(v66) = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, unsigned __int8 ***, void **, _QWORD))(*(_QWORD *)v44 + 56LL))(
                               v44,
                               *(_QWORD *)(*((_QWORD *)this + 186) + 8LL),
                               7,
                               &v67,
                               &Src,
                               0);
              if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
                  {
                    v40 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                    LODWORD(v52) = 12185;
                    v41 = 12477449;
                    goto LABEL_168;
                  }
                  v42 = 12185;
                  v43 = 12477449;
                  goto LABEL_170;
                }
                goto LABEL_171;
              }
              memcpy_0(v62, Src, 8LL * (_QWORD)v67);
              v45 = v67;
            }
            CRecordGroup::SetGroupProperties((CRecordset *)((char *)this + 736), (unsigned __int64)v45, 0, 1u, 1u);
            CRecordGroup::SetBookmarkProperties((CRecordset *)((char *)this + 736), 0, 0, 0, 0);
            if ( Src )
              CoTaskMemFree(Src);
            ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v68);
            goto LABEL_176;
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v40 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v52) = 12179;
              v41 = 12471305;
              goto LABEL_168;
            }
            v42 = 12179;
            v43 = 12471305;
            goto LABEL_170;
          }
        }
      }
    }
LABEL_171:
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v68);
    goto LABEL_184;
  }
  if ( v9 == adFilterAffectedRecords )
  {
    LODWORD(v66) = CRecordGroup::Emulate((CRecordset *)((char *)this + 736), (CRecordset *)((char *)this + 856), 0);
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_184;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v52) = 12204;
        v6 = 12496905;
        goto LABEL_10;
      }
      v7 = 12204;
      v8 = 12496905;
      goto LABEL_12;
    }
LABEL_176:
    v46 = (char *)this + 1488;
    if ( **((_DWORD **)this + 186) != 1 )
    {
      LODWORD(v66) = CRecordset::InsertChapter(v33, (char *)this + 1488, 1);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_184;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v52) = 12266;
          v6 = 12560393;
          goto LABEL_10;
        }
        v7 = 12266;
        v8 = 12560393;
        goto LABEL_12;
      }
      *(_QWORD *)(*(_QWORD *)v46 + 8LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v46 + 32LL) + 8LL);
    }
    *(_DWORD *)(*(_QWORD *)v46 + 40LL) = v9;
    LODWORD(v66) = CRecordset::_MoveFirst(this, 1, 1);
    CContext::Failed((CContext *)&TlsValue, (const int *)&v66);
    goto LABEL_184;
  }
  v33 = (unsigned int)(v9 - 3);
  if ( v9 != adFilterFetchedRecords )
  {
    if ( v9 == adFilterConflictingRecords )
    {
      LODWORD(v66) = CRecordGroup::Emulate((CRecordset *)((char *)this + 736), (CRecordset *)((char *)this + 976), 0);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_184;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v52) = 12211;
          v6 = 12504073;
          goto LABEL_10;
        }
        v7 = 12211;
        v8 = 12504073;
        goto LABEL_12;
      }
    }
    goto LABEL_176;
  }
  if ( (*((_WORD *)a2 + 8) & 0x2000) == 0 )
  {
LABEL_137:
    CRecordset::GetDeferredHRow(this, &v63);
    goto LABEL_176;
  }
  if ( (unsigned int)CSafeArray::cDims(*((CSafeArray **)a2 + 5)) != 1 || (unsigned int)CSafeArray::cDim(v35, v34) )
  {
    Src = 0;
    v67 = 0;
    v68 = 0;
    v62 = 0;
    if ( (unsigned int)CContext::FailIfClosed((CContext *)&TlsValue, *((_DWORD *)this + 315)) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_184;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v52) = 12242;
        v6 = 12535817;
        goto LABEL_10;
      }
      v7 = 12242;
      v8 = 12535817;
      goto LABEL_12;
    }
    CVar::UpdateVariant(a2);
    v64 = *(struct tagVARIANT *)((char *)a2 + 16);
    LODWORD(v66) = ExtractBookmarkArray(
                     &v64,
                     (unsigned __int64 *)&Src,
                     (unsigned __int64 **)&v68,
                     &v67,
                     (__int64 **)&v62);
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_184;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v52) = 12244;
        v6 = 12537865;
        goto LABEL_10;
      }
      v7 = 12244;
      v8 = 12537865;
      goto LABEL_12;
    }
    v37 = v67;
    v38 = v68;
    LODWORD(v66) = CRecordset::FetchRecords(this, (unsigned __int64)Src, (unsigned __int64 *const)v68, v67);
    v39 = CContext::Failed((CContext *)&TlsValue, (const int *)&v66);
    if ( v37 )
      operator delete(v37);
    if ( v38 )
      operator delete(v38);
    if ( v62 )
      operator delete(v62);
    if ( v39 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_184;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v52) = 12255;
        v6 = 12549129;
        goto LABEL_10;
      }
      v7 = 12255;
      v8 = 12549129;
      goto LABEL_12;
    }
    goto LABEL_137;
  }
  CRecordGroup::CRecordGroup((CRecordGroup *)v65);
  v65[0] = this;
  LODWORD(v66) = CRecordGroup::Emulate((CRecordset *)((char *)this + 736), (struct CRecordGroup *)v65, 0);
  if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v66) )
  {
    CRecordGroup::~CRecordGroup((CRecordGroup *)v65);
    goto LABEL_176;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
    {
      bidTraceW(off_18012A208[0], 12518409, L"<CRecordset::SetFilter|ADO|ERR>  line %d\n", 12225);
    }
    else
    {
      v36 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(off_18012A208[0], 12518409, L"<CRecordset::SetFilter|ADO|ERR> %u#, line %d\n", v36, 12225);
    }
  }
  CRecordGroup::~CRecordGroup((CRecordGroup *)v65);
LABEL_184:
  v47 = v60;
  if ( TlsValue[2]-- == 1 )
  {
    v49 = TlsValue;
    v50 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v50 )
    {
      SetErrorInfo(0, v50);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v49 = TlsValue;
    }
    if ( *((_BYTE *)v49 + 30) )
    {
      *((_QWORD *)v49 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v47;
}

```

## disassembly

```asm
0x18004a31c  push    rbp
0x18004a31e  push    rbx
0x18004a31f  push    rsi
0x18004a320  push    rdi
0x18004a321  push    r12
0x18004a323  push    r13
0x18004a325  push    r14
0x18004a327  push    r15
0x18004a329  lea     rbp, [rsp-28h]
0x18004a32e  sub     rsp, 128h
0x18004a335  mov     r13, rdx
0x18004a338  mov     rdi, rcx
0x18004a33b  mov     rax, rcx
0x18004a33e  lea     r9, [rcx+20h]
0x18004a342  neg     rax
0x18004a345  sbb     r8, r8
0x18004a348  and     r8, r9
0x18004a34b  mov     [rsp+160h+var_100], r8
0x18004a350  xor     r12d, r12d
0x18004a353  mov     [rsp+160h+var_F4], r12d
0x18004a358  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004a35f  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004a362  call    cs:__imp_TlsGetValue
0x18004a369  nop     dword ptr [rax+rax+00h]
0x18004a36e  mov     [rsp+160h+TlsValue], rax
0x18004a373  mov     [rsp+160h+var_F8], r12d
0x18004a378  lea     r15d, [r12+1]
0x18004a37d  test    rax, rax
0x18004a380  jz      short loc_18004A388
0x18004a382  add     [rax+8], r15d
0x18004a386  jmp     short loc_18004A3C7
0x18004a388  mov     [rsp+160h+var_118], r15d
0x18004a38d  mov     [rsp+160h+var_110], r12
0x18004a392  mov     [rsp+160h+var_108], r12d
0x18004a397  mov     [rsp+160h+var_104], r12w
0x18004a39d  mov     [rsp+160h+var_102], r12b
0x18004a3a2  lea     rdx, [rsp+160h+TlsValue]; lpTlsValue
0x18004a3a7  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004a3ae  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004a3b1  call    cs:__imp_TlsSetValue
0x18004a3b8  nop     dword ptr [rax+rax+00h]
0x18004a3bd  lea     rax, [rsp+160h+TlsValue]
0x18004a3c2  mov     [rsp+160h+TlsValue], rax
0x18004a3c7  or      ebx, 0FFFFFFFFh
0x18004a3ca  test    byte ptr [r13+8], 4
0x18004a3cf  jnz     loc_18004A46F
0x18004a3d5  mov     [rsp+160h+var_F8], 8007000Eh
0x18004a3dd  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a3e2  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18004a3e7  test    eax, eax
0x18004a3e9  jz      loc_18004A46F
0x18004a3ef  cmp     [rsp+160h+var_F8], r12d
0x18004a3f4  jz      short loc_18004A46F
0x18004a3f6  mov     esi, 2
0x18004a3fb  test    byte ptr cs:_bidGblFlags, sil
0x18004a402  jz      loc_18004B282
0x18004a408  lea     rcx, [rdi+618h]; this
0x18004a40f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a414  cmp     eax, ebx
0x18004a416  jz      short loc_18004A44C
0x18004a418  lea     rcx, [rdi+618h]; this
0x18004a41f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a424  mov     dword ptr [rsp+160h+var_140], 2F54h
0x18004a42c  mov     edx, 0BD5009h
0x18004a431  lea     r8, aCrecordsetSetf_0; "<CRecordset::SetFilter|ADO|ERR> %u#, li"...
0x18004a438  mov     r9d, eax
0x18004a43b  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004a442  call    _bidTraceW
0x18004a447  jmp     loc_18004B282
0x18004a44c  mov     r9d, 2F54h
0x18004a452  mov     edx, 0BD5009h
0x18004a457  lea     r8, aCrecordsetSetf; "<CRecordset::SetFilter|ADO|ERR>  line %"...
0x18004a45e  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004a465  call    _bidTraceW
0x18004a46a  jmp     loc_18004B282
0x18004a46f  or      r14d, 0FFFFFFFFh
0x18004a473  movzx   edx, word ptr [r13+10h]
0x18004a478  mov     ecx, edx
0x18004a47a  mov     r8d, 0BFFFh
0x18004a480  and     ecx, r8d
0x18004a483  lea     esi, [r14+3]
0x18004a487  sub     ecx, esi; this
0x18004a489  jz      loc_18004A538
0x18004a48f  sub     ecx, 1; this
0x18004a492  jz      short loc_18004A4C0
0x18004a494  sub     ecx, 5
0x18004a497  jz      short loc_18004A4B5
0x18004a499  sub     ecx, 2004h
0x18004a49f  jz      short loc_18004A4AA
0x18004a4a1  cmp     ecx, 5
0x18004a4a4  jnz     loc_18004A5B3
0x18004a4aa  mov     r14d, 3
0x18004a4b0  jmp     loc_18004A61D
0x18004a4b5  mov     r14d, 4
0x18004a4bb  jmp     loc_18004A61D
0x18004a4c0  lea     r14, [r13+18h]
0x18004a4c4  bt      dx, 0Eh
0x18004a4c9  jnb     short loc_18004A4CE
0x18004a4cb  mov     r14, [r14]
0x18004a4ce  mov     r14d, [r14]
0x18004a4d1  mov     edx, r14d; enum FilterGroupEnum
0x18004a4d4  call    ?IsValidFilterGroup@CRecordset@@AEAAHW4FilterGroupEnum@@@Z; CRecordset::IsValidFilterGroup(FilterGroupEnum)
0x18004a4d9  mov     edx, eax; int
0x18004a4db  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a4e0  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x18004a4e5  test    eax, eax
0x18004a4e7  jz      loc_18004A5AD
0x18004a4ed  test    byte ptr cs:_bidGblFlags, sil
0x18004a4f4  jz      loc_18004B282
0x18004a4fa  lea     rcx, [rdi+618h]; this
0x18004a501  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a506  cmp     eax, ebx
0x18004a508  jz      short loc_18004A528
0x18004a50a  lea     rcx, [rdi+618h]; this
0x18004a511  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a516  mov     dword ptr [rsp+160h+var_140], 2F61h
0x18004a51e  mov     edx, 0BD8409h
0x18004a523  jmp     loc_18004A431
0x18004a528  mov     r9d, 2F61h
0x18004a52e  mov     edx, 0BD8409h
0x18004a533  jmp     loc_18004A457
0x18004a538  lea     rax, [r13+18h]
0x18004a53c  bt      dx, 0Eh
0x18004a541  jnb     short loc_18004A546
0x18004a543  mov     rax, [rax]
0x18004a546  movsx   r14d, word ptr [rax]
0x18004a54a  mov     edx, r14d; enum FilterGroupEnum
0x18004a54d  call    ?IsValidFilterGroup@CRecordset@@AEAAHW4FilterGroupEnum@@@Z; CRecordset::IsValidFilterGroup(FilterGroupEnum)
0x18004a552  mov     edx, eax; int
0x18004a554  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a559  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x18004a55e  test    eax, eax
0x18004a560  jz      short loc_18004A5AD
0x18004a562  test    byte ptr cs:_bidGblFlags, sil
0x18004a569  jz      loc_18004B282
0x18004a56f  lea     rcx, [rdi+618h]; this
0x18004a576  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a57b  cmp     eax, ebx
0x18004a57d  jz      short loc_18004A59D
0x18004a57f  lea     rcx, [rdi+618h]; this
0x18004a586  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a58b  mov     dword ptr [rsp+160h+var_140], 2F65h
0x18004a593  mov     edx, 0BD9409h
0x18004a598  jmp     loc_18004A431
0x18004a59d  mov     r9d, 2F65h
0x18004a5a3  mov     edx, 0BD9409h
0x18004a5a8  jmp     loc_18004A457
0x18004a5ad  cmp     r14d, 0FFFFFFFFh
0x18004a5b1  jnz     short loc_18004A617
0x18004a5b3  mov     dword ptr [rbp+60h+arg_0], 800A0BB9h
0x18004a5ba  lea     rdx, [rbp+60h+arg_0]; int *
0x18004a5be  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a5c3  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18004a5c8  test    eax, eax
0x18004a5ca  jz      short loc_18004A617
0x18004a5cc  test    byte ptr cs:_bidGblFlags, sil
0x18004a5d3  jz      loc_18004B282
0x18004a5d9  lea     rcx, [rdi+618h]; this
0x18004a5e0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a5e5  cmp     eax, ebx
0x18004a5e7  jz      short loc_18004A607
0x18004a5e9  lea     rcx, [rdi+618h]; this
0x18004a5f0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a5f5  mov     dword ptr [rsp+160h+var_140], 2F6Eh
0x18004a5fd  mov     edx, 0BDB809h
0x18004a602  jmp     loc_18004A431
0x18004a607  mov     r9d, 2F6Eh
0x18004a60d  mov     edx, 0BDB809h
0x18004a612  jmp     loc_18004A457
0x18004a617  mov     r8d, 0BFFFh
0x18004a61d  lea     eax, [r14-1]
0x18004a621  cmp     eax, esi
0x18004a623  jbe     loc_18004AA49
0x18004a629  cmp     r14d, 5
0x18004a62d  jz      loc_18004AA49
0x18004a633  mov     [rbp+60h+arg_8], r12
0x18004a637  cmp     r14d, 4
0x18004a63b  jnz     short loc_18004A662
0x18004a63d  movzx   eax, word ptr [r13+10h]
0x18004a642  and     ax, r8w
0x18004a646  cmp     ax, 8
0x18004a64a  jnz     loc_18004A6E0
0x18004a650  xor     edx, edx; int
0x18004a652  mov     rcx, [r13+28h]; this
0x18004a656  call    ?GetLength@CSysString@@QEBAKH@Z; CSysString::GetLength(int)
0x18004a65b  test    eax, eax
0x18004a65d  jnz     short loc_18004A662
0x18004a65f  mov     r14d, r12d
0x18004a662  mov     r9d, esi
0x18004a665  lea     r8, [rbp+60h+arg_8]
0x18004a669  mov     rdx, [rdi+5D0h]
0x18004a670  call    ?CopyStack@CRecordset@@AEAAJPEAVCChapter@@PEAPEAV2@W4ChapterType@@@Z; CRecordset::CopyStack(CChapter *,CChapter * *,ChapterType)
0x18004a675  mov     [rsp+160h+var_F8], eax
0x18004a679  test    eax, eax
0x18004a67b  jns     loc_18004A76B
0x18004a681  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a686  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18004a68b  test    byte ptr cs:_bidGblFlags, sil
0x18004a692  jz      loc_18004A951
0x18004a698  lea     rbx, [rdi+618h]
0x18004a69f  mov     rcx, rbx; this
0x18004a6a2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a6a7  cmp     eax, 0FFFFFFFFh
0x18004a6aa  jz      loc_18004A748
0x18004a6b0  mov     rcx, rbx; this
0x18004a6b3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a6b8  mov     dword ptr [rsp+160h+var_140], 3007h
0x18004a6c0  mov     edx, 0C01C09h
0x18004a6c5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004a6cc  mov     r9d, eax
0x18004a6cf  lea     r8, aCrecordsetSetf_0; "<CRecordset::SetFilter|ADO|ERR> %u#, li"...
0x18004a6d6  call    _bidTraceW
0x18004a6db  jmp     loc_18004A951
0x18004a6e0  mov     dword ptr [rbp+60h+arg_0], 800A0BB9h
0x18004a6e7  lea     rdx, [rbp+60h+arg_0]; int *
0x18004a6eb  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a6f0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004a6f5  test    eax, eax
0x18004a6f7  jz      loc_18004A662
0x18004a6fd  test    byte ptr cs:_bidGblFlags, sil
0x18004a704  jz      loc_18004B282
0x18004a70a  lea     rcx, [rdi+618h]; this
0x18004a711  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a716  cmp     eax, ebx
0x18004a718  jz      short loc_18004A738
0x18004a71a  lea     rcx, [rdi+618h]; this
0x18004a721  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a726  mov     dword ptr [rsp+160h+var_140], 3001h
0x18004a72e  mov     edx, 0C00409h
0x18004a733  jmp     loc_18004A431
0x18004a738  mov     r9d, 3001h
0x18004a73e  mov     edx, 0C00409h
0x18004a743  jmp     loc_18004A457
0x18004a748  mov     r9d, 3007h
0x18004a74e  mov     edx, 0C01C09h
0x18004a753  lea     r8, aCrecordsetSetf; "<CRecordset::SetFilter|ADO|ERR>  line %"...
0x18004a75a  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004a761  call    _bidTraceW
0x18004a766  jmp     loc_18004A951
0x18004a76b  mov     r8d, esi
0x18004a76e  mov     r12, [rbp+60h+arg_8]
0x18004a772  mov     rdx, r12
0x18004a775  call    ?FindChapter@CRecordset@@AEAAPEAVCChapter@@PEAV2@W4ChapterType@@@Z; CRecordset::FindChapter(CChapter *,ChapterType)
0x18004a77a  mov     rbx, rax
0x18004a77d  mov     [rbp+60h+arg_0], rax
0x18004a781  test    rax, rax
0x18004a784  jz      short loc_18004A7A6
0x18004a786  test    r14d, r14d
0x18004a789  jnz     loc_18004A823
0x18004a78f  lea     r8, [rbp+60h+arg_0]; struct CChapter **
0x18004a793  lea     rdx, [rbp+60h+arg_8]; struct CChapter **
0x18004a797  call    ?DeleteChapter@CRecordset@@AEAAXPEAPEAVCChapter@@0@Z; CRecordset::DeleteChapter(CChapter * *,CChapter * *)
0x18004a79c  mov     r12, [rbp+60h+arg_8]
0x18004a7a0  mov     rbx, [rbp+60h+arg_0]
0x18004a7a4  jmp     short loc_18004A823
0x18004a7a6  cmp     r14d, 4
0x18004a7aa  jnz     short loc_18004A821
0x18004a7ac  lea     rdx, [rbp+60h+arg_8]
0x18004a7b0  call    ?InsertChapter@CRecordset@@AEAAJPEAPEAVCChapter@@W4ChapterType@@@Z; CRecordset::InsertChapter(CChapter * *,ChapterType)
0x18004a7b5  mov     dword ptr [rbp+60h+arg_0], eax
0x18004a7b8  lea     rdx, [rbp+60h+arg_0]; int *
0x18004a7bc  lea     rcx, [rsp+160h+TlsValue]; this
0x18004a7c1  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004a7c6  xor     r12d, r12d
0x18004a7c9  test    eax, eax
0x18004a7cb  jz      short loc_18004A818
0x18004a7cd  test    byte ptr cs:_bidGblFlags, sil
0x18004a7d4  jz      loc_18004A951
0x18004a7da  lea     rbx, [rdi+618h]
0x18004a7e1  mov     rcx, rbx; this
0x18004a7e4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a7e9  cmp     eax, 0FFFFFFFFh
0x18004a7ec  jz      short loc_18004A808
0x18004a7ee  mov     rcx, rbx; this
0x18004a7f1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004a7f6  mov     dword ptr [rsp+160h+var_140], 3015h
0x18004a7fe  mov     edx, 0C05409h
0x18004a803  jmp     loc_18004A6C5
0x18004a808  mov     r9d, 3015h
0x18004a80e  mov     edx, 0C05409h
0x18004a813  jmp     loc_18004A753
0x18004a818  mov     r12, [rbp+60h+arg_8]
0x18004a81c  mov     rbx, r12
0x18004a81f  jmp     short loc_18004A823
0x18004a821  xor     ebx, ebx
0x18004a823  test    rbx, rbx
0x18004a826  jz      short loc_18004A849
0x18004a828  test    r14d, r14d
0x18004a82b  jnz     loc_18004A8E3
0x18004a831  mov     rcx, [rbx+10h]; bstrString
0x18004a835  call    cs:__imp_SysFreeString
0x18004a83c  nop     dword ptr [rax+rax+00h]
0x18004a841  mov     qword ptr [rbx+10h], 0
0x18004a849  cmp     dword ptr [rdi+4ECh], 0
0x18004a850  jz      loc_18004A9B5
0x18004a856  mov     rcx, rdi; this
0x18004a859  call    ?GetRecoveryHRow@CRecordset@@AEAA_KXZ; CRecordset::GetRecoveryHRow(void)
0x18004a85e  mov     rbx, rax
0x18004a861  xor     edx, edx; bool
0x18004a863  mov     rcx, rdi; this
  ... truncated ...
```
