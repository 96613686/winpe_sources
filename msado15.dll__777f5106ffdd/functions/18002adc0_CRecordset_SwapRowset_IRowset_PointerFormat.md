# CRecordset::SwapRowset(IRowset *,PointerFormat)

- ea: `0x18002adc0`
- end: `0x18002c34a`
- name: `?SwapRowset@CRecordset@@AEAAJPEAUIRowset@@W4PointerFormat@@@Z`
- size: `5514`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002a580`
- `0x1800b42e8`

## callees

- `0x180001514`
- `0x180006610`
- `0x18000f760`
- `0x180011690`
- `0x1800193f0`
- `0x180019460`
- `0x180019700`
- `0x180020e20`
- `0x180027790`
- `0x18002a0f0`
- `0x18002a580`
- `0x18002adc0`
- `0x18002c440`
- `0x18002cd84`
- `0x18002ce00`
- `0x18002d044`
- `0x18002ddd4`
- `0x18002e670`
- `0x180056e84`
- `0x18005cc90`
- `0x18006a22c`
- `0x1800973a0`
- `0x180098d98`
- `0x1800a8e40`
- `0x1800aa7c4`
- `0x1800af92c`
- `0x1800b029c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002afcd`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002afcd`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002afee`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002afee`
- `MSDART!MpHeapFree` at `0x18002b944`
- `MSDART!MpHeapFree` at `0x18002b973`
- `MSDART!MpHeapFree` at `0x18002b944`
- `MSDART!MpHeapFree` at `0x18002b973`
- `KERNEL32!TlsSetValue` at `0x18002aeff`
- `KERNEL32!TlsSetValue` at `0x18002af79`
- `KERNEL32!TlsSetValue` at `0x18002b453`
- `KERNEL32!TlsSetValue` at `0x18002b4b8`
- `KERNEL32!TlsSetValue` at `0x18002aeff`
- `KERNEL32!TlsSetValue` at `0x18002af79`
- `KERNEL32!TlsSetValue` at `0x18002b453`
- `KERNEL32!TlsSetValue` at `0x18002b4b8`
- `KERNEL32!TlsGetValue` at `0x18002aebc`
- `KERNEL32!TlsGetValue` at `0x18002b414`
- `KERNEL32!TlsGetValue` at `0x18002aebc`
- `KERNEL32!TlsGetValue` at `0x18002b414`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002b3bd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002b523`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002b3bd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002b523`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CRecordset::SwapRowset(__int64 a1, struct IUnknown *a2, int a3)
{
  int v3; // r15d
  struct IUnknown *v4; // rsi
  unsigned int *v6; // r12
  int Interface; // r14d
  __int64 result; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  _DWORD *Value; // rax
  CRecordset *v13; // rcx
  struct IUnknown *v14; // rsi
  struct IUnknown *lpVtbl; // rax
  int v16; // ebx
  bool v17; // zf
  _DWORD *v18; // rax
  IErrorInfo *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdi
  struct IUnknown *v22; // rbx
  unsigned __int64 v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r8
  int v27; // edx
  __int64 v28; // r8
  int v29; // edx
  int v30; // r10d
  int v31; // ecx
  __int64 v32; // r9
  __int64 v33; // r8
  int v34; // edx
  int v35; // r10d
  int v36; // ecx
  __int64 v37; // r9
  unsigned int v38; // eax
  int v39; // edi
  unsigned int v40; // eax
  __int64 v41; // r14
  __int64 v42; // r8
  unsigned __int64 *v43; // r12
  __int64 v44; // rax
  _DWORD *v45; // rax
  unsigned __int64 *i; // rbx
  _DWORD *v47; // rax
  IErrorInfo *v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // edx
  int v57; // ecx
  int v58; // edx
  char v59; // di
  __int64 v60; // rbx
  __int64 v61; // rdx
  unsigned int BidObjectID; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  __int64 v65; // r9
  __int64 v66; // rdx
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  __int64 v76; // rdx
  unsigned __int64 *v77; // r15
  unsigned __int64 *v78; // rdi
  unsigned int v79; // eax
  unsigned int v80; // eax
  __int64 v81; // r9
  __int64 v82; // rdx
  unsigned int v83; // eax
  unsigned int v84; // eax
  __int64 v85; // [rsp+20h] [rbp-58h]
  __int64 v86; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *TlsValue; // [rsp+38h] [rbp-40h] BYREF
  int v88; // [rsp+40h] [rbp-38h]
  __int64 v89; // [rsp+48h] [rbp-30h]
  int v90; // [rsp+50h] [rbp-28h]
  __int16 v91; // [rsp+54h] [rbp-24h]
  char v92; // [rsp+56h] [rbp-22h]
  __int64 v93; // [rsp+58h] [rbp-20h]
  int v94; // [rsp+60h] [rbp-18h]
  int v95; // [rsp+64h] [rbp-14h]
  struct IUnknown *v96; // [rsp+C0h] [rbp+48h] BYREF
  struct IUnknown *v97; // [rsp+C8h] [rbp+50h]
  int v98; // [rsp+D0h] [rbp+58h]
  __int64 v99; // [rsp+D8h] [rbp+60h] BYREF

  v98 = a3;
  v97 = a2;
  v3 = a3;
  v4 = a2;
  v6 = (unsigned int *)(a1 + 1128);
  if ( !*(_QWORD *)(a1 + 1128) )
  {
    Interface = 0;
    goto LABEL_3;
  }
  v9 = *(_QWORD *)(a1 + 1392);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *(_QWORD *)(a1 + 1392) = 0;
  }
  CRecordGroup::ReleaseRows((CRecordGroup *)(a1 + 736));
  *(_QWORD *)(a1 + 744) = 0;
  CRecordGroup::FreeRows((CRecordGroup *)(a1 + 736));
  CRecordGroup::ReleaseRows((CRecordGroup *)(a1 + 856));
  *(_QWORD *)(a1 + 864) = 0;
  CRecordGroup::FreeRows((CRecordGroup *)(a1 + 856));
  CRecordGroup::ReleaseRows((CRecordGroup *)(a1 + 976));
  *(_QWORD *)(a1 + 984) = 0;
  v10 = *(_QWORD *)(a1 + 1016);
  if ( v10 )
  {
    MpHeapFree(g_hHeapHandle, v10);
    *(_QWORD *)(a1 + 1016) = 0;
  }
  if ( *(_BYTE *)(a1 + 1072) )
  {
    v61 = *(_QWORD *)(a1 + 1024);
    if ( v61 )
    {
      MpHeapFree(g_hHeapHandle, v61);
      *(_QWORD *)(a1 + 1024) = 0;
    }
  }
  *(_QWORD *)(a1 + 1000) = 0;
  v11 = a1 + 32;
  if ( !a1 )
    v11 = 0;
  v93 = v11;
  v95 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v94 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v88 = 1;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v14 = *(struct IUnknown **)(a1 + 1488);
  v96 = v14;
  if ( !v14 )
  {
    v16 = v94;
    CContext::~CContext((CContext *)&TlsValue);
    goto LABEL_25;
  }
  if ( LODWORD(v14->lpVtbl) != 1 )
  {
    lpVtbl = v14;
    goto LABEL_18;
  }
  CRecordset::DeleteChapter(v13, (struct CChapter **)(a1 + 1488), (struct CChapter **)&v96);
  v14 = *(struct IUnknown **)(a1 + 1488);
  lpVtbl = v14;
  if ( !v14 )
  {
LABEL_20:
    v16 = v94;
    v17 = TlsValue[2]-- == 1;
    if ( v17 )
    {
      v18 = TlsValue;
      v19 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
      if ( v19 )
      {
        SetErrorInfo(0, v19);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
        v18 = TlsValue;
      }
      if ( *((_BYTE *)v18 + 30) )
      {
        *((_QWORD *)v18 + 2) = 0;
        TlsValue[6] = 0;
      }
      else
      {
        TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
      }
    }
    goto LABEL_25;
  }
LABEL_18:
  while ( LODWORD(lpVtbl->lpVtbl) )
  {
    lpVtbl = (struct IUnknown *)lpVtbl[4].lpVtbl;
    if ( !lpVtbl )
      goto LABEL_20;
  }
  v60 = 0;
  v99 = 0;
  v59 = 0;
  while ( 1 )
  {
    if ( !v14 )
    {
LABEL_118:
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      goto LABEL_20;
    }
    if ( v14[1].lpVtbl && *(_QWORD *)v6 )
    {
      if ( !v59 )
      {
        CRsetOptionalInterface<IChapteredRowset,&_GUID const IID_IChapteredRowset>::GetInterface(a1 + 360, &v99);
        v59 = 1;
        v60 = v99;
      }
      if ( v60 )
        break;
    }
LABEL_116:
    if ( !LODWORD(v14->lpVtbl) )
      goto LABEL_118;
    v14 = (struct IUnknown *)v14[4].lpVtbl;
  }
  LODWORD(v96) = (*(__int64 (__fastcall **)(__int64, struct IUnknownVtbl *, _QWORD))(*(_QWORD *)v60 + 32LL))(
                   v60,
                   v14[1].lpVtbl,
                   0);
  if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v96) )
  {
    v14[1].lpVtbl = 0;
    goto LABEL_116;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
    {
      bidTraceW(off_18012A208[0], 1857545, L"<CRecordset::ReleaseChapters|ADO|ERR>  line %d\n", 1814);
    }
    else
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
      bidTraceW(off_18012A208[0], 1857545, L"<CRecordset::ReleaseChapters|ADO|ERR> %u#, line %d\n", BidObjectID, 1814);
    }
  }
  v16 = v94;
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v99);
  CContext::~CContext((CContext *)&TlsValue);
LABEL_25:
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 7325705, L"<CRecordset::SwapRowset|ADO|ERR>  line %d\n", 7154);
      }
      else
      {
        v63 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7154;
        bidTraceW(off_18012A208[0], 7325705, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v63, v85);
      }
    }
    return (unsigned int)v16;
  }
  if ( (*(_BYTE *)(a1 + 328) & 4) == 0 )
  {
    v96 = 0;
    if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(a1 + 312, &v96) < 0 )
      goto LABEL_28;
    if ( v96 )
      ((void (__fastcall *)(struct IUnknown *))v96->lpVtbl->Release)(v96);
LABEL_81:
    v39 = CRecordset::ReleaseBookmarkAccessor((CRecordset *)a1);
    if ( v39 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 7329801, L"<CRecordset::SwapRowset|ADO|ERR>  line %d\n", 7158);
        }
        else
        {
          v40 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
          LODWORD(v85) = 7158;
          bidTraceW(off_18012A208[0], 7329801, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v40, v85);
        }
      }
      return (unsigned int)v39;
    }
    goto LABEL_28;
  }
  if ( *(_QWORD *)(a1 + 320) )
    goto LABEL_81;
LABEL_28:
  result = CRsetFields::ReleaseAccessors((CRsetFields *)(a1 + 1576));
  if ( (int)result < 0 )
    return result;
  CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(a1 + 1656));
  v21 = *(_QWORD *)(a1 + 1648);
  *(_QWORD *)(a1 + 1648) = 0;
  if ( v21 )
  {
    LODWORD(v41) = *(_DWORD *)(v21 + 16);
    while ( (_DWORD)v41 )
    {
      v42 = (unsigned int)v41;
      v41 = (unsigned int)(v41 - 1);
      if ( (unsigned int)v41 < *(_DWORD *)(v21 + 16) )
      {
        v20 = *(_QWORD *)(*(_QWORD *)(v21 + 8) + 8 * v41);
        if ( v20 )
        {
          if ( v20 != v42 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 1584) + 352LL))(a1 + 1584);
        }
      }
    }
    CCollectionList::`scalar deleting destructor'((CCollectionList *)v21, v20);
  }
  CReaderWriterLock3AR::WriteUnlock((CReaderWriterLock3AR *)(a1 + 1656));
  *(_DWORD *)(a1 + 1668) = 1;
  v96 = 0;
  Interface = CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface(a1 + 336, &v96);
  if ( Interface < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
      {
        v65 = 7168;
        v66 = 7340041;
        goto LABEL_205;
      }
      v64 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
      LODWORD(v85) = 7168;
      bidTraceW(off_18012A208[0], 7340041, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v64, v85);
    }
    goto LABEL_206;
  }
  v22 = v96;
LABEL_32:
  v23 = 0;
  v24 = 0;
  while ( (unsigned int)v24 < *(_DWORD *)(a1 + 1464) )
  {
    v25 = *(_QWORD *)(*(_QWORD *)(a1 + 1472) + 8 * v24);
    if ( v25 )
      v23 = *(_QWORD *)(v25 + 24);
    v24 = (unsigned int)(v24 + 1);
    if ( v23 )
    {
      Interface = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(
                    v22,
                    v23,
                    0);
      if ( Interface < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
          {
            v68 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
            LODWORD(v85) = 7174;
            bidTraceW(off_18012A208[0], 7346185, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v68, v85);
            goto LABEL_206;
          }
          v65 = 7174;
          v66 = 7346185;
LABEL_205:
          bidTraceW(off_18012A208[0], v66, L"<CRecordset::SwapRowset|ADO|ERR>  line %d\n", v65);
        }
LABEL_206:
        ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v96);
        return (unsigned int)Interface;
      }
      CCollectionMap::DeleteByData((CCollectionMap *)(a1 + 1464), v23);
      goto LABEL_32;
    }
  }
  v49 = *(_QWORD *)(a1 + 1208);
  if ( v49 )
  {
    Interface = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(v22, v49, 0);
    if ( Interface < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_206;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v69 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7180;
        bidTraceW(off_18012A208[0], 7352329, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v69, v85);
        goto LABEL_206;
      }
      v65 = 7180;
      v66 = 7352329;
      goto LABEL_205;
    }
    *(_QWORD *)(a1 + 1208) = 0;
  }
  v50 = *(_QWORD *)(a1 + 1224);
  if ( v50 )
  {
    Interface = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(v22, v50, 0);
    if ( Interface < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_206;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v70 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7186;
        bidTraceW(off_18012A208[0], 7358473, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v70, v85);
        goto LABEL_206;
      }
      v65 = 7186;
      v66 = 7358473;
      goto LABEL_205;
    }
    *(_QWORD *)(a1 + 1224) = 0;
  }
  v51 = *(_QWORD *)(a1 + 1232);
  if ( v51 )
  {
    Interface = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(v22, v51, 0);
    if ( Interface < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_206;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v71 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7192;
        bidTraceW(off_18012A208[0], 7364617, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v71, v85);
        goto LABEL_206;
      }
      v65 = 7192;
      v66 = 7364617;
      goto LABEL_205;
    }
    *(_QWORD *)(a1 + 1232) = 0;
  }
  v52 = *(_QWORD *)(a1 + 1248);
  if ( v52 )
  {
    Interface = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(v22, v52, 0);
    if ( Interface < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_206;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v72 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7198;
        bidTraceW(off_18012A208[0], 7370761, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v72, v85);
        goto LABEL_206;
      }
      v65 = 7198;
      v66 = 7370761;
      goto LABEL_205;
    }
    *(_QWORD *)(a1 + 1248) = 0;
  }
  v53 = *(_QWORD *)(a1 + 1400);
  if ( v53 )
  {
    Interface = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(v22, v53, 0);
    if ( Interface < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_206;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v73 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7204;
        bidTraceW(off_18012A208[0], 7376905, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v73, v85);
        goto LABEL_206;
      }
      v65 = 7204;
      v66 = 7376905;
      goto LABEL_205;
    }
    *(_QWORD *)(a1 + 1400) = 0;
  }
  v54 = *(_QWORD *)(a1 + 672);
  if ( v54 )
  {
    Interface = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v22->lpVtbl[2].QueryInterface)(v22, v54, 0);
    if ( Interface < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_206;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v67 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = 7210;
        bidTraceW(off_18012A208[0], 7383049, L"<CRecordset::SwapRowset|ADO|ERR> %u#, line %d\n", v67, v85);
        goto LABEL_206;
      }
      v65 = 7210;
      v66 = 7383049;
      goto LABEL_205;
    }
    *(_QWORD *)(a1 + 672) = 0;
  }
  if ( *(_QWORD *)(a1 + 368) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 368);
  *(_DWORD *)(a1 + 376) &= ~4u;
  if ( *(_QWORD *)(a1 + 344) )
    CAdoInterfacePtr<IAccessor,&_GUID const IID_IAccessor>::SetNullInterface((unsigned int *)(a1 + 344));
  *(_DWORD *)(a1 + 352) &= ~4u;
  if ( *(_QWORD *)(a1 + 320) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 320);
  *(_DWORD *)(a1 + 328) &= ~4u;
  if ( *(_QWORD *)(a1 + 392) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 392);
  *(_DWORD *)(a1 + 400) &= ~4u;
  if ( *(_QWORD *)(a1 + 416) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 416);
  *(_DWORD *)(a1 + 424) &= ~4u;
  if ( *(_QWORD *)(a1 + 440) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 440);
  *(_DWORD *)(a1 + 448) &= ~4u;
  if ( *(_QWORD *)(a1 + 464) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 464);
  *(_DWORD *)(a1 + 472) &= ~4u;
  if ( *(_QWORD *)(a1 + 488) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 488);
  *(_DWORD *)(a1 + 496) &= ~4u;
  if ( *(_QWORD *)(a1 + 512) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 512);
  *(_DWORD *)(a1 + 520) &= ~4u;
  if ( *(_QWORD *)(a1 + 536) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 536);
  *(_DWORD *)(a1 + 544) &= ~4u;
  if ( *(_QWORD *)(a1 + 560) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 560);
  *(_DWORD *)(a1 + 568) &= ~4u;
  if ( *(_QWORD *)(a1 + 608) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 608);
  *(_DWORD *)(a1 + 616) &= ~4u;
  if ( *(_QWORD *)(a1 + 632) )
    CAdoInterfacePtr<IRowsetIndex,&_GUID const IID_IRowsetIndex>::SetNullInterface(a1 + 632);
  *(_DWORD *)(a1 + 640) &= ~4u;
  if ( *(_QWORD *)(a1 + 656) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 656);
  *(_DWORD *)(a1 + 664) &= ~4u;
  if ( *(_QWORD *)(a1 + 584) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 584);
  *(_DWORD *)(a1 + 592) &= ~4u;
  v55 = *(_QWORD *)v6;
  if ( *(_QWORD *)v6 )
  {
    v56 = v6[2] & 2;
    if ( (v6[2] & 1) != 0 )
    {
      if ( v56
        || (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)g_pStaticGlobals + 10) + 32LL))(
             *((_QWORD *)g_pStaticGlobals + 10),
             (unsigned int)v55) >= 0 )
      {
        *v6 = 0;
      }
    }
    else
    {
      if ( !v56 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55 + 16LL))(*(_QWORD *)v6);
      *(_QWORD *)v6 = 0;
    }
  }
  if ( *(_QWORD *)(a1 + 1144) )
    CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 1144);
  *(_WORD *)(a1 + 1096) = -1;
  v57 = *(_DWORD *)(a1 + 696) & 0x200;
  v58 = *(_DWORD *)(a1 + 696) & 0x100;
  if ( !v58 || v57 )
  {
    *(_QWORD *)(a1 + 728) = 0;
    *(_WORD *)(a1 + 1098) = -1;
    *(_BYTE *)(a1 + 752) = 1;
    if ( !v58 || v57 )
      *(_QWORD *)(a1 + 728) = 0;
  }
  else
  {
    *(_WORD *)(a1 + 1098) = -1;
    *(_BYTE *)(a1 + 752) = 1;
  }
  *(_DWORD *)(a1 + 1260) = 0;
  if ( v22 )
    ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
  v6 = (unsigned int *)(a1 + 1128);
  v4 = v97;
  v3 = v98;
LABEL_3:
  if ( !v4 )
    return (unsigned int)Interface;
  v86 = 0;
  LODWORD(v99) = -268435456;
  v26 = *(_QWORD *)v6;
  if ( *(_QWORD *)v6 )
  {
    v27 = v6[2] & 2;
    if ( (v6[2] & 1) != 0 )
    {
      if ( v27
        || (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)g_pStaticGlobals + 10) + 32LL))(
             *((_QWORD *)g_pStaticGlobals + 10),
             (unsigned int)v26) >= 0 )
      {
        *v6 = 0;
      }
    }
    else
    {
      if ( !v27 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(*(_QWORD *)v6);
      *(_QWORD *)v6 = 0;
    }
  }
  v6[2] &= ~1u;
  v6[2] |= v3;
  if ( v3 )
  {
    Interface = CADOIGlobalInterfaceTable::RegisterInterfaceInGlobal(
                  (CDAOStaticGlobals *)((char *)g_pStaticGlobals + 80),
                  v4,
                  &IID_IRowset,
                  v6);
    if ( Interface >= 0 )
      goto LABEL_46;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_295;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
    {
      v74 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
      LODWORD(v85) = Interface;
      bidTraceW(
        off_18012A208[0],
        7428105,
        L"<CRecordset::SwapRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v74,
        v85,
        7254);
      goto LABEL_295;
    }
    LODWORD(v85) = 7254;
    v76 = 7428105;
LABEL_294:
    bidTraceW(
      off_18012A208[0],
      v76,
      L"<CRecordset::SwapRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)Interface,
      v85);
    goto LABEL_295;
  }
  *(_QWORD *)v6 = v4;
  ((void (__fastcall *)(struct IUnknown *))v4->lpVtbl->AddRef)(v4);
LABEL_46:
  v6[2] &= ~2u;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v4->lpVtbl->QueryInterface)(
         v4,
         &IID_IRowsetConnection,
         &v86) >= 0 )
  {
    LODWORD(v96) = 0;
    if ( (*(int (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v86 + 48LL))(v86, &v96) >= 0 )
      *(_DWORD *)(a1 + 712) = (_DWORD)v96 != 0;
  }
  v28 = *(_QWORD *)(a1 + 680);
  v29 = 0;
  v30 = *(_DWORD *)(v28 + 16);
  v31 = 0;
  if ( v30 > 0 )
  {
    do
    {
      if ( v31 < v30 )
      {
        v32 = *(_QWORD *)(v28 + 8);
        if ( v30 >= 2 )
          v32 = *(_QWORD *)(v32 + 8LL * (unsigned int)v31);
        if ( v32 && *(_QWORD *)(v32 + 8) )
          ++v29;
      }
      ++v31;
    }
    while ( v31 < v30 );
    if ( v29 )
      goto LABEL_298;
  }
  v33 = *(_QWORD *)(a1 + 688);
  v34 = 0;
  v35 = *(_DWORD *)(v33 + 16);
  v36 = 0;
  if ( v35 > 0 )
  {
    do
    {
      if ( v36 < v35 )
      {
        v37 = *(_QWORD *)(v33 + 8);
        if ( v35 >= 2 )
          v37 = *(_QWORD *)(v37 + 8LL * (unsigned int)v36);
        if ( v37 && *(_QWORD *)(v37 + 8) )
          ++v34;
      }
      ++v36;
    }
    while ( v36 < v35 );
    if ( v34 )
    {
LABEL_298:
      Interface = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(a1 + 104) + 64LL))(a1 + 104, 0, 0);
      if ( Interface < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_295;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
        {
          v75 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
          LODWORD(v85) = Interface;
          bidTraceW(
            off_18012A208[0],
            7445513,
            L"<CRecordset::SwapRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v75,
            v85,
            7271);
          goto LABEL_295;
        }
        LODWORD(v85) = 7271;
        v76 = 7445513;
        goto LABEL_294;
      }
    }
  }
  *(_DWORD *)(a1 + 1096) = 0;
  *(_BYTE *)(a1 + 1506) = 1;
  *(_DWORD *)(a1 + 696) = -268435456;
  CRecordset::GetAttributes((CRecordset *)a1, (unsigned int *)&v99);
  *(_DWORD *)(a1 + 700) = -1;
  if ( (*(_BYTE *)(a1 + 328) & 4) != 0 )
  {
    if ( *(_QWORD *)(a1 + 320) )
      goto LABEL_71;
  }
  else
  {
    v96 = 0;
    if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(a1 + 312, &v96) >= 0 )
    {
      if ( v96 )
        ((void (__fastcall *)(struct IUnknown *))v96->lpVtbl->Release)(v96);
LABEL_71:
      Interface = CRecordset::SetupBookmarkAccessor((CRecordset *)a1);
      if ( Interface < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_295;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
        {
          v38 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
          LODWORD(v85) = Interface;
          bidTraceW(
            off_18012A208[0],
            7460873,
            L"<CRecordset::SwapRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v38,
            v85,
            7286);
          goto LABEL_295;
        }
        LODWORD(v85) = 7286;
        v76 = 7460873;
        goto LABEL_294;
      }
    }
  }
  v43 = *(unsigned __int64 **)(a1 + 1488);
  v44 = a1 + 32;
  if ( !a1 )
    v44 = 0;
  v93 = v44;
  v95 = 0;
  v45 = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = v45;
  v94 = 0;
  if ( v45 )
  {
    ++v45[2];
  }
  else
  {
    v88 = 1;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  for ( i = v43; i; i = (unsigned __int64 *)i[4] )
  {
    if ( !*(_DWORD *)i )
      break;
  }
  if ( !i )
    goto LABEL_102;
  while ( 2 )
  {
    v77 = i;
    v78 = i;
    i = v43;
    if ( v78 != v43 )
    {
      while ( (unsigned __int64 *)i[4] != v78 )
        i = (unsigned __int64 *)i[4];
    }
    if ( v78[1] || !CSysString::GetLength((CSysString *)(v78 + 2), 0) )
      goto LABEL_275;
    if ( *(_DWORD *)v77 == 2 )
    {
      LODWORD(v96) = CRecordset::OpenFilterFromString(
                       (CRecordset *)a1,
                       (const struct CSysString *)(v78 + 2),
                       *(_QWORD *)(v78[4] + 8),
                       v78 + 1);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v96) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_280;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
        {
          v79 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
          LODWORD(v85) = 1870;
          bidTraceW(off_18012A208[0], 1914889, L"<CRecordset::ApplyChapters|ADO|ERR> %u#, line %d\n", v79, v85);
          goto LABEL_280;
        }
        v81 = 1870;
        v82 = 1914889;
        goto LABEL_279;
      }
      goto LABEL_275;
    }
    if ( *(_DWORD *)v77 != 3
      || (LODWORD(v96) = CRecordset::OpenSortFromString(
                           (CRecordset *)a1,
                           (const struct CSysString *)(v78 + 2),
                           *(_QWORD *)(v78[4] + 8),
                           v78 + 1),
          !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v96)) )
    {
LABEL_275:
      if ( v78 == v43 )
        goto LABEL_280;
      continue;
    }
    break;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_280;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
  {
    v80 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
    LODWORD(v85) = 1876;
    bidTraceW(off_18012A208[0], 1921033, L"<CRecordset::ApplyChapters|ADO|ERR> %u#, line %d\n", v80, v85);
    goto LABEL_280;
  }
  v81 = 1876;
  v82 = 1921033;
LABEL_279:
  bidTraceW(off_18012A208[0], v82, L"<CRecordset::ApplyChapters|ADO|ERR>  line %d\n", v81);
LABEL_280:
  v4 = v97;
LABEL_102:
  Interface = v94;
  v17 = TlsValue[2]-- == 1;
  if ( v17 )
  {
    v47 = TlsValue;
    v48 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v48 )
    {
      SetErrorInfo(0, v48);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v47 = TlsValue;
    }
    if ( *((_BYTE *)v47 + 30) )
    {
      *((_QWORD *)v47 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  if ( Interface < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_295;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
    {
      v83 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
      LODWORD(v85) = Interface;
      bidTraceW(
        off_18012A208[0],
        7464969,
        L"<CRecordset::SwapRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v83,
        v85,
        7290);
      goto LABEL_295;
    }
    LODWORD(v85) = 7290;
    v76 = 7464969;
    goto LABEL_294;
  }
  if ( *(_QWORD *)(a1 + 1144) )
    goto LABEL_109;
  v96 = 0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v4->lpVtbl->QueryInterface)(
    v4,
    &IID_IDBAsynchStatus,
    &v96);
  if ( v96
    && (Interface = CAdoInterfacePtr<IDBAsynchStatus,&_GUID const IID_IDBAsynchStatus>::SetInterface(
                      (unsigned int *)(a1 + 1144),
                      v96),
        Interface < 0) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
      {
        LODWORD(v85) = 7302;
        bidTraceW(
          off_18012A208[0],
          7477257,
          L"<CRecordset::SwapRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)Interface,
          v85);
      }
      else
      {
        v84 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(v85) = Interface;
        bidTraceW(
          off_18012A208[0],
          7477257,
          L"<CRecordset::SwapRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v84,
          v85,
          7302);
      }
    }
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v96);
LABEL_295:
    CRecordset::SetRowset(a1, 0, 0);
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v86);
  }
  else
  {
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v96);
    if ( *(_QWORD *)(a1 + 1144) )
    {
LABEL_109:
      LODWORD(v96) = 0;
      *(_BYTE *)(a1 + 1504) = 1;
      CRecordset::GetFetchStatus((CRecordset *)a1, (unsigned int *)&v96);
    }
    *(_DWORD *)(a1 + 1260) = 1;
    if ( v86 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18002adc0  mov     [rsp-40h+arg_10], r8d
0x18002adc5  mov     [rsp-40h+arg_8], rdx
0x18002adca  push    rbp
0x18002adcb  push    rbx
0x18002adcc  push    rsi
0x18002adcd  push    rdi
0x18002adce  push    r12
0x18002add0  push    r13
0x18002add2  push    r14
0x18002add4  push    r15
0x18002add6  mov     rbp, rsp
0x18002add9  sub     rsp, 78h
0x18002addd  mov     r15d, r8d
0x18002ade0  mov     rsi, rdx
0x18002ade3  mov     r13, rcx
0x18002ade6  lea     r12, [rcx+468h]
0x18002aded  cmp     qword ptr [r12], 0
0x18002adf2  jnz     short loc_18002AE17
0x18002adf4  xor     edi, edi
0x18002adf6  mov     r14d, edi
0x18002adf9  test    rsi, rsi
0x18002adfc  jnz     loc_18002B088
0x18002ae02  mov     eax, r14d
0x18002ae05  add     rsp, 78h
0x18002ae09  pop     r15
0x18002ae0b  pop     r14
0x18002ae0d  pop     r13
0x18002ae0f  pop     r12
0x18002ae11  pop     rdi
0x18002ae12  pop     rsi
0x18002ae13  pop     rbx
0x18002ae14  pop     rbp
0x18002ae15  retn
0x18002ae17  mov     rcx, [rcx+570h]
0x18002ae1e  xor     r14d, r14d
0x18002ae21  test    rcx, rcx
0x18002ae24  jnz     loc_18002B925
0x18002ae2a  lea     rcx, [r13+2E0h]; this
0x18002ae31  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x18002ae36  mov     [r13+2E8h], r14
0x18002ae3d  lea     rcx, [r13+2E0h]; this
0x18002ae44  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x18002ae49  lea     rcx, [r13+358h]; this
0x18002ae50  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x18002ae55  mov     [r13+360h], r14
0x18002ae5c  lea     rcx, [r13+358h]; this
0x18002ae63  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x18002ae68  lea     rcx, [r13+3D0h]; this
0x18002ae6f  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x18002ae74  mov     [r13+3D8h], r14
0x18002ae7b  mov     rdx, [r13+3F8h]
0x18002ae82  test    rdx, rdx
0x18002ae85  jnz     loc_18002B93D
0x18002ae8b  cmp     [r13+430h], r14b
0x18002ae92  jnz     loc_18002B95C
0x18002ae98  mov     [r13+3E8h], r14
0x18002ae9f  lea     rax, [r13+20h]
0x18002aea3  test    r13, r13
0x18002aea6  cmovz   rax, r14
0x18002aeaa  mov     [rbp+var_20], rax
0x18002aeae  mov     [rbp+var_14], r14d
0x18002aeb2  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002aeb9  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002aebc  call    cs:__imp_TlsGetValue
0x18002aec3  nop     dword ptr [rax+rax+00h]
0x18002aec8  mov     [rbp+TlsValue], rax
0x18002aecc  mov     [rbp+var_18], r14d
0x18002aed0  test    rax, rax
0x18002aed3  jnz     loc_18002B365
0x18002aed9  mov     [rbp+var_38], 1
0x18002aee0  mov     [rbp+var_30], r14
0x18002aee4  mov     [rbp+var_28], r14d
0x18002aee8  mov     [rbp+var_24], r14w
0x18002aeed  mov     [rbp+var_22], r14b
0x18002aef1  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18002aef5  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002aefc  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002aeff  call    cs:__imp_TlsSetValue
0x18002af06  nop     dword ptr [rax+rax+00h]
0x18002af0b  lea     rax, [rbp+TlsValue]
0x18002af0f  mov     [rbp+TlsValue], rax
0x18002af13  mov     rsi, [r13+5D0h]
0x18002af1a  mov     [rbp+arg_0], rsi
0x18002af1e  test    rsi, rsi
0x18002af21  jz      loc_18002B98B
0x18002af27  cmp     dword ptr [rsi], 1
0x18002af2a  jz      loc_18002B87A
0x18002af30  mov     rax, rsi
0x18002af33  cmp     dword ptr [rax], 0
0x18002af36  jz      loc_18002B99C
0x18002af3c  mov     rax, [rax+20h]
0x18002af40  test    rax, rax
0x18002af43  jnz     short loc_18002AF33
0x18002af45  mov     ebx, [rbp+var_18]
0x18002af48  mov     rax, [rbp+TlsValue]
0x18002af4c  add     dword ptr [rax+8], 0FFFFFFFFh
0x18002af50  jnz     short loc_18002AF86
0x18002af52  mov     rax, [rbp+TlsValue]
0x18002af56  mov     rdx, [rax+10h]; perrinfo
0x18002af5a  test    rdx, rdx
0x18002af5d  jnz     loc_18002B3BB
0x18002af63  cmp     byte ptr [rax+1Eh], 0
0x18002af67  jnz     loc_18002BA2F
0x18002af6d  xor     edx, edx; lpTlsValue
0x18002af6f  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002af76  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002af79  call    cs:__imp_TlsSetValue
0x18002af80  nop     dword ptr [rax+rax+00h]
0x18002af85  nop
0x18002af86  test    ebx, ebx
0x18002af88  js      loc_18002BA40
0x18002af8e  lea     rcx, [r13+138h]
0x18002af95  lea     r15, [rcx+8]
0x18002af99  test    byte ptr [r15+8], 4
0x18002af9e  jz      loc_18002B2D3
0x18002afa4  cmp     qword ptr [r15], 0
0x18002afa8  jnz     loc_18002B2FD
0x18002afae  lea     rcx, [r13+628h]; this
0x18002afb5  call    ?ReleaseAccessors@CRsetFields@@QEAAJXZ; CRsetFields::ReleaseAccessors(void)
0x18002afba  test    eax, eax
0x18002afbc  js      loc_18002AE05
0x18002afc2  lea     rbx, [r13+630h]
0x18002afc9  lea     rcx, [rbx+48h]
0x18002afcd  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18002afd4  nop     dword ptr [rax+rax+00h]
0x18002afd9  mov     rdi, [rbx+40h]
0x18002afdd  mov     [rbx+40h], r14
0x18002afe1  test    rdi, rdi
0x18002afe4  jnz     loc_18002B36D
0x18002afea  lea     rcx, [rbx+48h]
0x18002afee  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18002aff5  nop     dword ptr [rax+rax+00h]
0x18002affa  mov     dword ptr [r13+684h], 1
0x18002b005  mov     [rbp+arg_0], r14
0x18002b009  lea     rcx, [r13+150h]
0x18002b010  lea     rdx, [rbp+arg_0]
0x18002b014  call    ?GetInterface@?$CRsetOptionalInterface@UIAccessor@@$1?IID_IAccessor@@3U_GUID@@B@@QEAAJPEAPEAUIAccessor@@@Z; CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface(IAccessor * *)
0x18002b019  mov     r14d, eax
0x18002b01c  test    eax, eax
0x18002b01e  js      loc_18002BAD5
0x18002b024  mov     rbx, [rbp+arg_0]
0x18002b028  xor     edi, edi
0x18002b02a  xor     edx, edx
0x18002b02c  mov     r9d, [r13+5B8h]
0x18002b033  cmp     edx, r9d
0x18002b036  jnb     loc_18002B585
0x18002b03c  mov     rax, [r13+5C0h]
0x18002b043  mov     r8, [rax+rdx*8]
0x18002b047  test    r8, r8
0x18002b04a  jnz     loc_18002BB8F
0x18002b050  inc     edx
0x18002b052  test    rdi, rdi
0x18002b055  jz      short loc_18002B033
0x18002b057  mov     rax, [rbx]
0x18002b05a  xor     r8d, r8d
0x18002b05d  mov     rdx, rdi
0x18002b060  mov     rcx, rbx
0x18002b063  mov     rax, [rax+30h]
0x18002b067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b06c  mov     r14d, eax
0x18002b06f  test    eax, eax
0x18002b071  js      loc_18002BB98
0x18002b077  mov     rdx, rdi; unsigned __int64
0x18002b07a  lea     rcx, [r13+5B8h]; this
0x18002b081  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x18002b086  jmp     short loc_18002B028
0x18002b088  mov     [rbp+var_48], rdi
0x18002b08c  mov     dword ptr [rbp+arg_18], 0F0000000h
0x18002b093  mov     r8, [r12]
0x18002b097  test    r8, r8
0x18002b09a  jz      short loc_18002B0C5
0x18002b09c  mov     eax, [r12+8]
0x18002b0a1  mov     edx, eax
0x18002b0a3  and     edx, 2
0x18002b0a6  test    al, 1
0x18002b0a8  jnz     loc_18002B2A4
0x18002b0ae  test    edx, edx
0x18002b0b0  jnz     short loc_18002B0C1
0x18002b0b2  mov     rax, [r8]
0x18002b0b5  mov     rcx, r8
0x18002b0b8  mov     rax, [rax+10h]
0x18002b0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0c1  mov     [r12], rdi
0x18002b0c5  and     dword ptr [r12+8], 0FFFFFFFEh
0x18002b0cb  or      [r12+8], r15d
0x18002b0d0  test    r15d, r15d
0x18002b0d3  jnz     loc_18002BF0E
0x18002b0d9  mov     [r12], rsi
0x18002b0dd  mov     rax, [rsi]
0x18002b0e0  mov     rcx, rsi
0x18002b0e3  mov     rax, [rax+8]
0x18002b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0ec  and     dword ptr [r12+8], 0FFFFFFFDh
0x18002b0f2  mov     rax, [rsi]
0x18002b0f5  lea     r8, [rbp+var_48]
0x18002b0f9  lea     rdx, IID_IRowsetConnection
0x18002b100  mov     rcx, rsi
0x18002b103  mov     rax, [rax]
0x18002b106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b10b  test    eax, eax
0x18002b10d  js      short loc_18002B13A
0x18002b10f  mov     dword ptr [rbp+arg_0], edi
0x18002b112  mov     rcx, [rbp+var_48]
0x18002b116  mov     rax, [rcx]
0x18002b119  lea     rdx, [rbp+arg_0]
0x18002b11d  mov     rax, [rax+30h]
0x18002b121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b126  test    eax, eax
0x18002b128  js      short loc_18002B13A
0x18002b12a  mov     eax, edi
0x18002b12c  cmp     dword ptr [rbp+arg_0], 0
0x18002b130  setnz   al
0x18002b133  mov     [r13+2C8h], eax
0x18002b13a  mov     r8, [r13+2A8h]
0x18002b141  mov     edx, edi
0x18002b143  mov     r10d, [r8+10h]
0x18002b147  mov     ecx, edi
0x18002b149  test    r10d, r10d
0x18002b14c  jle     short loc_18002B180
0x18002b14e  mov     eax, r10d
0x18002b151  cmp     ecx, r10d
0x18002b154  jge     short loc_18002B171
0x18002b156  mov     r9, [r8+8]
0x18002b15a  cmp     eax, 2
0x18002b15d  jge     loc_18002BF91
0x18002b163  test    r9, r9
0x18002b166  jz      short loc_18002B171
0x18002b168  cmp     qword ptr [r9+8], 0
0x18002b16d  jz      short loc_18002B171
0x18002b16f  inc     edx
0x18002b171  inc     ecx
0x18002b173  cmp     ecx, r10d
0x18002b176  jl      short loc_18002B14E
0x18002b178  test    edx, edx
0x18002b17a  jnz     loc_18002BFA7
0x18002b180  mov     r8, [r13+2B0h]
0x18002b187  mov     edx, edi
0x18002b189  mov     r10d, [r8+10h]
0x18002b18d  mov     ecx, edi
0x18002b18f  test    r10d, r10d
0x18002b192  jle     short loc_18002B1C6
0x18002b194  mov     eax, r10d
0x18002b197  cmp     ecx, r10d
0x18002b19a  jge     short loc_18002B1B7
0x18002b19c  mov     r9, [r8+8]
0x18002b1a0  cmp     eax, 2
0x18002b1a3  jge     loc_18002BF9C
0x18002b1a9  test    r9, r9
0x18002b1ac  jz      short loc_18002B1B7
0x18002b1ae  cmp     qword ptr [r9+8], 0
0x18002b1b3  jz      short loc_18002B1B7
0x18002b1b5  inc     edx
0x18002b1b7  inc     ecx
0x18002b1b9  cmp     ecx, r10d
0x18002b1bc  jl      short loc_18002B194
0x18002b1be  test    edx, edx
0x18002b1c0  jnz     loc_18002BFA7
0x18002b1c6  mov     dword ptr [r13+448h], 0
0x18002b1d1  mov     byte ptr [r13+5E2h], 1
0x18002b1d9  mov     dword ptr [r13+2B8h], 0F0000000h
0x18002b1e4  lea     rdx, [rbp+arg_18]; unsigned int *
0x18002b1e8  mov     rcx, r13; this
0x18002b1eb  call    ?GetAttributes@CRecordset@@QEAAJPEAK@Z; CRecordset::GetAttributes(ulong *)
0x18002b1f0  mov     dword ptr [r13+2BCh], 0FFFFFFFFh
0x18002b1fb  lea     rcx, [r13+138h]
0x18002b202  test    byte ptr [rcx+10h], 4
0x18002b206  jnz     loc_18002B3E6
0x18002b20c  mov     [rbp+arg_0], rdi
0x18002b210  lea     rdx, [rbp+arg_0]
0x18002b214  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x18002b219  test    eax, eax
0x18002b21b  js      loc_18002B3F1
0x18002b221  mov     rcx, [rbp+arg_0]
0x18002b225  test    rcx, rcx
0x18002b228  jz      short loc_18002B236
0x18002b22a  mov     rax, [rcx]
0x18002b22d  mov     rax, [rax+10h]
0x18002b231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b236  mov     rcx, r13; this
0x18002b239  call    ?SetupBookmarkAccessor@CRecordset@@AEAAJXZ; CRecordset::SetupBookmarkAccessor(void)
0x18002b23e  mov     r14d, eax
0x18002b241  test    eax, eax
0x18002b243  jns     loc_18002B3F1
0x18002b249  test    byte ptr cs:_bidGblFlags, 2
0x18002b250  jz      loc_18002C32E
0x18002b256  lea     rcx, [r13+618h]; this
0x18002b25d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002b262  cmp     eax, 0FFFFFFFFh
0x18002b265  jz      loc_18002C030
0x18002b26b  lea     rcx, [r13+618h]; this
0x18002b272  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002b277  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002b27e  mov     [rsp+78h+var_50], 1C76h
0x18002b286  mov     dword ptr [rsp+78h+var_58], r14d
0x18002b28b  mov     r9d, eax
0x18002b28e  lea     r8, aCrecordsetSwap_5; "<CRecordset::SwapRowset|ADO|ERR> %u#,0x"...
0x18002b295  mov     edx, 71D809h
0x18002b29a  call    _bidTraceW
0x18002b29f  jmp     loc_18002C32E
0x18002b2a4  test    edx, edx
  ... truncated ...
```
