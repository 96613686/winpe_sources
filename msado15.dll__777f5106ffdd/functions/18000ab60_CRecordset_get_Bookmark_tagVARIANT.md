# CRecordset::get_Bookmark(tagVARIANT *)

- ea: `0x18000ab60`
- end: `0x18000b74c`
- name: `?get_Bookmark@CRecordset@@UEAAJPEAUtagVARIANT@@@Z`
- size: `3052`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update`

## callers

- `0x180075af0`

## callees

- `0x180006610`
- `0x180009940`
- `0x18000ab60`
- `0x180018788`
- `0x18001a750`
- `0x180020da0`
- `0x180020e20`
- `0x180020fc0`
- `0x18004f2b0`
- `0x18005cac8`
- `0x18006a22c`
- `0x180078c80`
- `0x1800795c0`
- `0x1800a56a8`
- `0x1800c8f34`
- `0x1800cd2e4`
- `0x1800cd3d0`
- `0x1800cd4c4`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18000ac0b`
- `MSDART!UMSEnterCSWraper` at `0x18000ac0b`
- `KERNEL32!LeaveCriticalSection` at `0x18000af6e`
- `KERNEL32!LeaveCriticalSection` at `0x18000af6e`
- `KERNEL32!TlsSetValue` at `0x18000abf0`
- `KERNEL32!TlsSetValue` at `0x18000aca7`
- `KERNEL32!TlsSetValue` at `0x18000aed6`
- `KERNEL32!TlsSetValue` at `0x18000af0d`
- `KERNEL32!TlsSetValue` at `0x18000afac`
- `KERNEL32!TlsSetValue` at `0x18000b189`
- `KERNEL32!TlsSetValue` at `0x18000abf0`
- `KERNEL32!TlsSetValue` at `0x18000aca7`
- `KERNEL32!TlsSetValue` at `0x18000aed6`
- `KERNEL32!TlsSetValue` at `0x18000af0d`
- `KERNEL32!TlsSetValue` at `0x18000afac`
- `KERNEL32!TlsSetValue` at `0x18000b189`
- `KERNEL32!TlsGetValue` at `0x18000abad`
- `KERNEL32!TlsGetValue` at `0x18000ac5f`
- `KERNEL32!TlsGetValue` at `0x18000abad`
- `KERNEL32!TlsGetValue` at `0x18000ac5f`
- `ole32!CoTaskMemFree` at `0x18000b38f`
- `ole32!CoTaskMemFree` at `0x18000b38f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b0a4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b0cf`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b0fc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b19d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b0a4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b0cf`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b0fc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000b19d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::get_Bookmark(CRecordset *this, struct tagVARIANT *a2)
{
  __int64 v4; // rbx
  char *v5; // rsi
  _DWORD *Value; // rax
  LONGLONG *v7; // r12
  __int64 v8; // r14
  _DWORD *v9; // rax
  int DeferredHRow; // eax
  int v11; // esi
  __int64 v12; // rdx
  int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  int v17; // r8d
  int v18; // ebx
  bool v19; // zf
  _DWORD *v20; // rax
  IErrorInfo *v21; // rdx
  _DWORD *v22; // rax
  IErrorInfo *v23; // rdx
  char v24; // al
  unsigned int v25; // ebx
  __int64 v26; // rcx
  _DWORD *v27; // rax
  IErrorInfo *v28; // rdx
  unsigned int BidObjectID; // eax
  _DWORD *v31; // rax
  IErrorInfo *v32; // rdx
  __int64 v33; // rbx
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  void *v37; // rcx
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v40; // edx
  unsigned int v41; // eax
  __int64 v42; // r9
  __int64 v43; // rdx
  int v44; // r8d
  unsigned int v45; // eax
  unsigned __int8 v46; // r8
  unsigned int v47; // eax
  __int64 v48; // [rsp+20h] [rbp-A9h]
  _DWORD *v49; // [rsp+30h] [rbp-99h] BYREF
  int v50; // [rsp+38h] [rbp-91h]
  __int64 v51; // [rsp+40h] [rbp-89h]
  int v52; // [rsp+48h] [rbp-81h]
  __int16 v53; // [rsp+4Ch] [rbp-7Dh]
  char v54; // [rsp+4Eh] [rbp-7Bh]
  char *v55; // [rsp+50h] [rbp-79h]
  int v56; // [rsp+58h] [rbp-71h]
  int v57; // [rsp+5Ch] [rbp-6Dh]
  _DWORD *TlsValue; // [rsp+60h] [rbp-69h] BYREF
  int v59; // [rsp+68h] [rbp-61h]
  __int64 v60; // [rsp+70h] [rbp-59h]
  int v61; // [rsp+78h] [rbp-51h]
  __int16 v62; // [rsp+7Ch] [rbp-4Dh]
  char v63; // [rsp+7Eh] [rbp-4Bh]
  char *v64; // [rsp+80h] [rbp-49h]
  int v65; // [rsp+88h] [rbp-41h]
  int v66; // [rsp+8Ch] [rbp-3Dh]
  __int64 *v67; // [rsp+90h] [rbp-39h]
  char v68[8]; // [rsp+98h] [rbp-31h] BYREF
  int v69; // [rsp+A0h] [rbp-29h]
  _QWORD v70[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v71; // [rsp+C8h] [rbp-1h]
  IRecordInfo *v72; // [rsp+D8h] [rbp+Fh]
  unsigned __int64 v73; // [rsp+130h] [rbp+67h] BYREF
  __int64 v74; // [rsp+140h] [rbp+77h] BYREF

  v4 = *((_QWORD *)this + 38) + 8LL;
  v5 = (char *)this + 32;
  if ( !this )
    v5 = 0;
  v64 = v5;
  v66 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v65 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v59 = 1;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v67 = 0;
  UMSEnterCSWraper(v4);
  v67 = (__int64 *)v4;
  if ( !*((_DWORD *)this + 315) )
  {
    v65 = -2146824584;
    if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
    {
      if ( v65 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 3120137, L"<CRecordset::get_Bookmark|ADO|ERR>  line %d\n", 3047);
          }
          else
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(
              off_18012A208[0],
              3120137,
              L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n",
              BidObjectID,
              3047);
          }
        }
        goto LABEL_52;
      }
    }
  }
  if ( (*((_BYTE *)this + 328) & 4) != 0 )
  {
    if ( *((_QWORD *)this + 40) )
    {
LABEL_8:
      v65 = 0;
      goto LABEL_9;
    }
  }
  else
  {
    v73 = 0;
    if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
                (char *)this + 312,
                &v73) >= 0 )
    {
      if ( v73 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v73 + 16LL))(v73);
      goto LABEL_8;
    }
  }
  v65 = -2146825037;
  TlsValue[11] = 10020;
  if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 3123209, L"<CRecordset::get_Bookmark|ADO|ERR>  line %d\n", 3050);
      }
      else
      {
        v14 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 3123209, L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n", v14, 3050);
      }
    }
    goto LABEL_52;
  }
LABEL_9:
  v7 = 0;
  v8 = 0;
  v55 = v5;
  v57 = 0;
  v9 = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  v49 = v9;
  v56 = 0;
  if ( v9 )
  {
    ++v9[2];
  }
  else
  {
    v50 = 1;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &v49);
    v49 = &v49;
  }
  v73 = 0;
  v74 = 0;
  DeferredHRow = CRecordGroup::GetDeferredHRow((CRecordset *)((char *)this + 736), *((_QWORD *)this + 91), &v73);
  v11 = DeferredHRow;
  if ( DeferredHRow < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0] )
    {
      v33 = *((_QWORD *)this + 91);
      v34 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(
        `CRecordset::GetDeferredHRow'::`10'::_bidSrcFileA[0],
        375808,
        `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0],
        v34,
        v11,
        v33);
    }
    v56 = v11;
    CContext::PushError((CContext *)&v49);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 9306121, L"<CRecordset::GetBookmarkInfo|ADO|ERR>  line %d\n", 9088);
      }
      else
      {
        v35 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v48) = 9088;
        bidTraceW(off_18012A208[0], 9306121, L"<CRecordset::GetBookmarkInfo|ADO|ERR> %u#, line %d\n", v35, v48);
      }
    }
    v18 = v56;
    if ( v74 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    v19 = v49[2]-- == 1;
    if ( v19 )
    {
      v31 = v49;
      v32 = (IErrorInfo *)*((_QWORD *)v49 + 2);
      if ( v32 )
      {
        SetErrorInfo(0, v32);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v49 + 2) + 16LL))(*((_QWORD *)v49 + 2));
        v31 = v49;
      }
      if ( *((_BYTE *)v31 + 30) )
      {
        *((_QWORD *)v31 + 2) = 0;
        v49[6] = 0;
      }
      else
      {
        TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
      }
    }
    goto LABEL_47;
  }
  v56 = DeferredHRow;
  v74 = 0;
  v12 = *((_QWORD *)this + 141);
  if ( v12 )
  {
    v13 = 0;
    if ( (*((_BYTE *)this + 1136) & 1) != 0 )
    {
      if ( (_DWORD)v12 )
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 *))(**((_QWORD **)g_pStaticGlobals + 10) + 40LL))(
                *((_QWORD *)g_pStaticGlobals + 10),
                v12,
                &IID_IRowset,
                &v74);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*((_QWORD *)this + 141));
      v74 = *((_QWORD *)this + 141);
    }
    v56 = v13;
    if ( v13 < 0 )
    {
      CContext::PushError((CContext *)&v49);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 9307145, L"<CRecordset::GetBookmarkInfo|ADO|ERR>  line %d\n", 9089);
        }
        else
        {
          v36 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 9307145, L"<CRecordset::GetBookmarkInfo|ADO|ERR> %u#, line %d\n", v36, 9089);
        }
      }
      v18 = v56;
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v19 = v49[2]-- == 1;
      if ( v19 )
      {
        v22 = v49;
        v23 = (IErrorInfo *)*((_QWORD *)v49 + 2);
        if ( v23 )
        {
          SetErrorInfo(0, v23);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v49 + 2) + 16LL))(*((_QWORD *)v49 + 2));
          v22 = v49;
        }
        if ( *((_BYTE *)v22 + 30) )
        {
          *((_QWORD *)v22 + 2) = 0;
          v49[6] = 0;
        }
        else
        {
          TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
        }
      }
      goto LABEL_47;
    }
  }
  else
  {
    v56 = 0;
  }
  if ( *((_BYTE *)this + 1256) == 1 )
  {
    v37 = (void *)*((_QWORD *)this + 146);
    if ( v37 )
    {
      CoTaskMemFree(v37);
      *((_QWORD *)this + 146) = 0;
      *((_QWORD *)this + 147) = 0;
    }
  }
  v7 = (LONGLONG *)((char *)this + 1168);
  *((_DWORD *)this + 296) = 0;
  v15 = *((_QWORD *)this + 150);
  if ( v15 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, char *))(*(_QWORD *)v74 + 32LL))(
            v74,
            v73,
            v15,
            (char *)this + 1168);
    if ( v16 == -2147217887 && *((_DWORD *)this + 296) == 8 )
    {
      *v7 = 0;
      *((_QWORD *)this + 147) = 0;
      v16 = 0;
    }
    v56 = v16;
    if ( v16 < 0 )
      CContext::PushError((CContext *)&v49);
  }
  else
  {
    *v7 = 0;
    *((_QWORD *)this + 147) = 0;
    v56 = 0;
  }
  v17 = *((_DWORD *)this + 296);
  if ( v17 )
  {
    LODWORD(v73) = -2147217887;
    CContext::FailedDescription((CContext *)&v49, (const int *)&v73, v17 + 2000);
  }
  v8 = *((_QWORD *)this + 147);
  if ( (unsigned __int8)(*((_BYTE *)this + 1256) - 2) > 1u )
    v7 = (LONGLONG *)*v7;
  v18 = v56;
  if ( v74 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  v19 = v49[2]-- == 1;
  if ( v19 )
  {
    v20 = v49;
    v21 = (IErrorInfo *)*((_QWORD *)v49 + 2);
    if ( v21 )
    {
      SetErrorInfo(0, v21);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v49 + 2) + 16LL))(*((_QWORD *)v49 + 2));
      v20 = v49;
    }
    if ( *((_BYTE *)v20 + 30) )
    {
      *((_QWORD *)v20 + 2) = 0;
      v49[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
LABEL_47:
  v65 = v18;
  if ( v18 >= 0 )
  {
    if ( !v8 )
    {
      LODWORD(v73) = -2147217887;
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v73) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 3134473, L"<CRecordset::get_Bookmark|ADO|ERR>  line %d\n", 3061);
          }
          else
          {
            v39 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            LODWORD(v48) = 3061;
            bidTraceW(off_18012A208[0], 3134473, L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n", v39, v48);
          }
        }
        goto LABEL_52;
      }
    }
    v24 = *((_BYTE *)this + 1256);
    if ( v24 == 2 )
    {
      if ( v8 == 4 )
      {
        a2->vt = 5;
        a2->dblVal = (double)*(int *)v7;
        goto LABEL_52;
      }
    }
    else if ( v24 == 3 && v8 == 8 )
    {
      a2->vt = 20;
      a2->llVal = *v7;
      goto LABEL_52;
    }
    CBlob::CBlob((CBlob *)v68, 4u, 7u);
    if ( (unsigned int)CContext::BlobFailed((CContext *)&TlsValue, (struct CBlob *)v68) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v41 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v48) = 3082;
          bidTraceW(off_18012A208[0], 3155977, L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n", v41, v48);
          goto LABEL_129;
        }
        v42 = 3082;
        v43 = 3155977;
LABEL_121:
        bidTraceW(off_18012A208[0], v43, L"<CRecordset::get_Bookmark|ADO|ERR>  line %d\n", v42);
      }
    }
    else
    {
      if ( v8 == (unsigned int)CSafeArray::cDim((CSafeArray *)v68, v40)
        || (LODWORD(v73) = CBlob::Resize((CBlob *)v68, v8),
            !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v73)) )
      {
        CBlob::PutData((CBlob *)v68, v7, v44);
        v69 = 1;
        CVar::CVar((CVar *)v70, (const struct CBlob *)v68, v46);
        if ( (unsigned int)CContext::VariantFailed((CContext *)&TlsValue, (const struct CVar *)v70) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
            {
              bidTraceW(off_18012A208[0], 3165193, L"<CRecordset::get_Bookmark|ADO|ERR>  line %d\n", 3091);
            }
            else
            {
              v47 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v48) = 3091;
              bidTraceW(off_18012A208[0], 3165193, L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n", v47, v48);
            }
          }
        }
        else
        {
          CVar::UpdateVariant((CVar *)v70);
          *(_OWORD *)&a2->vt = v71;
          a2->pRecInfo = v72;
        }
        v70[0] = &CVar::`vftable';
        CVar::Clear((CVar *)v70);
        goto LABEL_129;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v45 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v48) = 3085;
          bidTraceW(off_18012A208[0], 3159049, L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n", v45, v48);
          goto LABEL_129;
        }
        v42 = 3085;
        v43 = 3159049;
        goto LABEL_121;
      }
    }
LABEL_129:
    CSafeArray::~CSafeArray((CSafeArray *)v68);
    goto LABEL_52;
  }
  CContext::PushError((CContext *)&TlsValue);
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
    {
      bidTraceW(off_18012A208[0], 3126281, L"<CRecordset::get_Bookmark|ADO|ERR>  line %d\n", 3053);
    }
    else
    {
      v38 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v48) = 3053;
      bidTraceW(off_18012A208[0], 3126281, L"<CRecordset::get_Bookmark|ADO|ERR> %u#, line %d\n", v38, v48);
    }
  }
LABEL_52:
  v25 = v65;
  v26 = *v67;
  --*(_DWORD *)(v26 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
  v19 = TlsValue[2]-- == 1;
  if ( v19 )
  {
    v27 = TlsValue;
    v28 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v28 )
    {
      SetErrorInfo(0, v28);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v27 = TlsValue;
    }
    if ( *((_BYTE *)v27 + 30) )
    {
      *((_QWORD *)v27 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v25;
}

```

## disassembly

```asm
0x18000ab60  mov     [rsp-8+arg_8], rbx
0x18000ab65  push    rbp
0x18000ab66  push    rsi
0x18000ab67  push    rdi
0x18000ab68  push    r12
0x18000ab6a  push    r13
0x18000ab6c  push    r14
0x18000ab6e  push    r15
0x18000ab70  lea     rbp, [rsp-27h]
0x18000ab75  sub     rsp, 0F0h
0x18000ab7c  mov     r15, rdx
0x18000ab7f  mov     rdi, rcx
0x18000ab82  mov     rbx, [rcx+130h]
0x18000ab89  add     rbx, 8
0x18000ab8d  lea     rsi, [rcx+20h]
0x18000ab91  xor     r13d, r13d
0x18000ab94  test    rcx, rcx
0x18000ab97  cmovz   rsi, r13
0x18000ab9b  mov     [rbp+57h+var_A0], rsi
0x18000ab9f  mov     [rbp+57h+var_94], r13d
0x18000aba3  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000abaa  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000abad  call    cs:__imp_TlsGetValue
0x18000abb4  nop     dword ptr [rax+rax+00h]
0x18000abb9  mov     [rbp+57h+TlsValue], rax
0x18000abbd  mov     [rbp+57h+var_98], r13d
0x18000abc1  test    rax, rax
0x18000abc4  jnz     loc_18000ADCC
0x18000abca  mov     [rbp+57h+var_B8], 1
0x18000abd1  mov     [rbp+57h+var_B0], r13
0x18000abd5  mov     [rbp+57h+var_A8], r13d
0x18000abd9  mov     [rbp+57h+var_A4], r13w
0x18000abde  mov     [rbp+57h+var_A2], r13b
0x18000abe2  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x18000abe6  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000abed  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000abf0  call    cs:__imp_TlsSetValue
0x18000abf7  nop     dword ptr [rax+rax+00h]
0x18000abfc  lea     rax, [rbp+57h+TlsValue]
0x18000ac00  mov     [rbp+57h+TlsValue], rax
0x18000ac04  mov     [rbp+57h+var_90], r13
0x18000ac08  mov     rcx, rbx
0x18000ac0b  call    cs:__imp_UMSEnterCSWraper
0x18000ac12  nop     dword ptr [rax+rax+00h]
0x18000ac17  mov     [rbp+57h+var_90], rbx
0x18000ac1b  cmp     [rdi+4ECh], r13d
0x18000ac22  jz      loc_18000B01B
0x18000ac28  lea     rcx, [rdi+138h]
0x18000ac2f  test    byte ptr [rcx+10h], 4
0x18000ac33  jz      loc_18000AD3E
0x18000ac39  cmp     [rcx+8], r13
0x18000ac3d  jz      loc_18000AD53
0x18000ac43  mov     [rbp+57h+var_98], r13d
0x18000ac47  mov     r12, r13
0x18000ac4a  mov     r14, r13
0x18000ac4d  mov     [rbp+57h+var_D0], rsi
0x18000ac51  mov     [rbp+57h+var_C4], r13d
0x18000ac55  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000ac5c  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000ac5f  call    cs:__imp_TlsGetValue
0x18000ac66  nop     dword ptr [rax+rax+00h]
0x18000ac6b  mov     [rsp+120h+var_F0], rax
0x18000ac70  mov     [rbp+57h+var_C8], r13d
0x18000ac74  test    rax, rax
0x18000ac77  jnz     loc_18000ADD4
0x18000ac7d  mov     [rsp+120h+var_E8], 1
0x18000ac85  mov     [rsp+120h+var_E0], r13
0x18000ac8a  mov     [rsp+120h+var_D8], r13d
0x18000ac8f  mov     [rbp+57h+var_D4], r12w
0x18000ac94  mov     [rbp+57h+var_D2], r12b
0x18000ac98  lea     rdx, [rsp+120h+var_F0]; lpTlsValue
0x18000ac9d  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000aca4  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000aca7  call    cs:__imp_TlsSetValue
0x18000acae  nop     dword ptr [rax+rax+00h]
0x18000acb3  lea     rax, [rsp+120h+var_F0]
0x18000acb8  mov     [rsp+120h+var_F0], rax
0x18000acbd  mov     [rbp+57h+arg_0], r13
0x18000acc1  mov     [rbp+57h+arg_10], r13
0x18000acc5  lea     rcx, [rdi+2E0h]; this
0x18000accc  lea     r8, [rbp+57h+arg_0]; unsigned __int64 *
0x18000acd0  mov     rdx, [rdi+2D8h]; __int64
0x18000acd7  call    ?GetDeferredHRow@CRecordGroup@@QEAAJ_JPEA_K@Z; CRecordGroup::GetDeferredHRow(__int64,unsigned __int64 *)
0x18000acdc  mov     esi, eax
0x18000acde  test    eax, eax
0x18000ace0  js      loc_18000B229
0x18000ace6  mov     [rbp+57h+var_C8], eax
0x18000ace9  mov     [rbp+57h+arg_10], r13
0x18000aced  mov     rdx, [rdi+468h]
0x18000acf4  test    rdx, rdx
0x18000acf7  jz      loc_18000B376
0x18000acfd  mov     ebx, r13d
0x18000ad00  test    byte ptr [rdi+470h], 1
0x18000ad07  jz      loc_18000ADDC
0x18000ad0d  test    edx, edx
0x18000ad0f  jz      loc_18000ADF6
0x18000ad15  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000ad1c  mov     rcx, [rax+50h]
0x18000ad20  mov     rax, [rcx]
0x18000ad23  lea     r9, [rbp+57h+arg_10]
0x18000ad27  lea     r8, IID_IRowset
0x18000ad2e  mov     rax, [rax+28h]
0x18000ad32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad37  mov     ebx, eax
0x18000ad39  jmp     loc_18000ADF6
0x18000ad3e  mov     [rbp+57h+arg_0], r13
0x18000ad42  lea     rdx, [rbp+57h+arg_0]
0x18000ad46  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x18000ad4b  test    eax, eax
0x18000ad4d  jns     loc_18000B1E8
0x18000ad53  mov     [rbp+57h+var_98], 800A0CB3h
0x18000ad5a  mov     rax, [rbp+57h+TlsValue]
0x18000ad5e  mov     dword ptr [rax+2Ch], 2724h
0x18000ad65  lea     rcx, [rbp+57h+TlsValue]; this
0x18000ad69  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000ad6e  test    eax, eax
0x18000ad70  jz      loc_18000AC47
0x18000ad76  test    byte ptr cs:_bidGblFlags, 2
0x18000ad7d  jz      loc_18000AF5D
0x18000ad83  lea     rcx, [rdi+618h]; this
0x18000ad8a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000ad8f  cmp     eax, 0FFFFFFFFh
0x18000ad92  jz      loc_18000B206
0x18000ad98  lea     rcx, [rdi+618h]; this
0x18000ad9f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000ada4  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000adab  mov     dword ptr [rsp+120h+var_100], 0BEAh
0x18000adb3  mov     r9d, eax
0x18000adb6  lea     r8, aCrecordsetGetB_2; "<CRecordset::get_Bookmark|ADO|ERR> %u#,"...
0x18000adbd  mov     edx, 2FA809h
0x18000adc2  call    _bidTraceW
0x18000adc7  jmp     loc_18000AF5D
0x18000adcc  inc     dword ptr [rax+8]
0x18000adcf  jmp     loc_18000AC04
0x18000add4  inc     dword ptr [rax+8]
0x18000add7  jmp     loc_18000ACBD
0x18000addc  mov     rax, [rdx]
0x18000addf  mov     rcx, rdx
0x18000ade2  mov     rax, [rax+8]
0x18000ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adeb  mov     rax, [rdi+468h]
0x18000adf2  mov     [rbp+57h+arg_10], rax
0x18000adf6  mov     [rbp+57h+var_C8], ebx
0x18000adf9  test    ebx, ebx
0x18000adfb  js      loc_18000AFD7
0x18000ae01  cmp     byte ptr [rdi+4E8h], 1
0x18000ae08  jz      loc_18000B37F
0x18000ae0e  lea     r12, [rdi+490h]
0x18000ae15  mov     [r12+10h], r13d
0x18000ae1a  mov     r8, [rdi+4B0h]
0x18000ae21  test    r8, r8
0x18000ae24  jnz     short loc_18000AE35
0x18000ae26  mov     [r12], r13
0x18000ae2a  mov     [r12+8], r13
0x18000ae2f  mov     [rbp+57h+var_C8], r13d
0x18000ae33  jmp     short loc_18000AE62
0x18000ae35  mov     rcx, [rbp+57h+arg_10]
0x18000ae39  mov     rax, [rcx]
0x18000ae3c  mov     r9, r12
0x18000ae3f  mov     rdx, [rbp+57h+arg_0]
0x18000ae43  mov     rax, [rax+20h]
0x18000ae47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4c  cmp     eax, 80040E21h
0x18000ae51  jz      loc_18000B3AE
0x18000ae57  mov     [rbp+57h+var_C8], eax
0x18000ae5a  test    eax, eax
0x18000ae5c  js      loc_18000B093
0x18000ae62  mov     r8d, [rdi+4A0h]
0x18000ae69  test    r8d, r8d
0x18000ae6c  jnz     loc_18000B3CB
0x18000ae72  mov     r14, [rdi+498h]
0x18000ae79  movzx   eax, byte ptr [rdi+4E8h]
0x18000ae80  sub     al, 2
0x18000ae82  cmp     al, 1
0x18000ae84  ja      loc_18000B3EC
0x18000ae8a  mov     ebx, [rbp+57h+var_C8]
0x18000ae8d  mov     rcx, [rbp+57h+arg_10]
0x18000ae91  test    rcx, rcx
0x18000ae94  jz      short loc_18000AEA3
0x18000ae96  mov     rax, [rcx]
0x18000ae99  mov     rax, [rax+10h]
0x18000ae9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aea2  nop
0x18000aea3  mov     rax, [rsp+120h+var_F0]
0x18000aea8  add     dword ptr [rax+8], 0FFFFFFFFh
0x18000aeac  jnz     short loc_18000AEE3
0x18000aeae  mov     rax, [rsp+120h+var_F0]
0x18000aeb3  mov     rdx, [rax+10h]; perrinfo
0x18000aeb7  test    rdx, rdx
0x18000aeba  jnz     loc_18000B0FA
0x18000aec0  cmp     byte ptr [rax+1Eh], 0
0x18000aec4  jnz     loc_18000B3F5
0x18000aeca  xor     edx, edx; lpTlsValue
0x18000aecc  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000aed3  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000aed6  call    cs:__imp_TlsSetValue
0x18000aedd  nop     dword ptr [rax+rax+00h]
0x18000aee2  nop
0x18000aee3  jmp     short loc_18000AF1A
0x18000aee5  mov     rax, [rsp+120h+var_F0]
0x18000aeea  mov     rdx, [rax+10h]; perrinfo
0x18000aeee  test    rdx, rdx
0x18000aef1  jnz     loc_18000B0CD
0x18000aef7  cmp     byte ptr [rax+1Eh], 0
0x18000aefb  jnz     loc_18000B364
0x18000af01  xor     edx, edx; lpTlsValue
0x18000af03  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000af0a  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000af0d  call    cs:__imp_TlsSetValue
0x18000af14  nop     dword ptr [rax+rax+00h]
0x18000af19  nop
0x18000af1a  mov     [rbp+57h+var_98], ebx
0x18000af1d  test    ebx, ebx
0x18000af1f  js      loc_18000B407
0x18000af25  test    r14, r14
0x18000af28  jz      loc_18000B485
0x18000af2e  movzx   eax, byte ptr [rdi+4E8h]
0x18000af35  cmp     al, 2
0x18000af37  jnz     loc_18000B516
0x18000af3d  cmp     r14, 4
0x18000af41  jnz     loc_18000B533
0x18000af47  mov     word ptr [r15], 5
0x18000af4d  movd    xmm0, dword ptr [r12]
0x18000af53  cvtdq2pd xmm0, xmm0
0x18000af57  movsd   qword ptr [r15+8], xmm0
0x18000af5d  mov     ebx, [rbp+57h+var_98]
0x18000af60  mov     rax, [rbp+57h+var_90]
0x18000af64  mov     rcx, [rax]
0x18000af67  dec     dword ptr [rcx+30h]
0x18000af6a  add     rcx, 8; lpCriticalSection
0x18000af6e  call    cs:__imp_LeaveCriticalSection
0x18000af75  nop     dword ptr [rax+rax+00h]
0x18000af7a  nop
0x18000af7b  mov     rax, [rbp+57h+TlsValue]
0x18000af7f  add     dword ptr [rax+8], 0FFFFFFFFh
0x18000af83  jnz     short loc_18000AFB9
0x18000af85  mov     rax, [rbp+57h+TlsValue]
0x18000af89  mov     rdx, [rax+10h]; perrinfo
0x18000af8d  test    rdx, rdx
0x18000af90  jnz     loc_18000B0A2
0x18000af96  cmp     byte ptr [rax+1Eh], 0
0x18000af9a  jnz     loc_18000B73A
0x18000afa0  xor     edx, edx; lpTlsValue
0x18000afa2  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000afa9  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000afac  call    cs:__imp_TlsSetValue
0x18000afb3  nop     dword ptr [rax+rax+00h]
0x18000afb8  nop
0x18000afb9  mov     eax, ebx
0x18000afbb  mov     rbx, [rsp+120h+arg_8]
0x18000afc3  add     rsp, 0F0h
0x18000afca  pop     r15
0x18000afcc  pop     r14
0x18000afce  pop     r13
0x18000afd0  pop     r12
0x18000afd2  pop     rdi
0x18000afd3  pop     rsi
0x18000afd4  pop     rbp
0x18000afd5  retn
0x18000afd7  lea     rcx, [rsp+120h+var_F0]; this
0x18000afdc  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000afe1  test    byte ptr cs:_bidGblFlags, 2
0x18000afe8  jnz     loc_18000B2FC
0x18000afee  mov     ebx, [rbp+57h+var_C8]
0x18000aff1  mov     rcx, [rbp+57h+arg_10]
0x18000aff5  test    rcx, rcx
0x18000aff8  jz      short loc_18000B007
0x18000affa  mov     rax, [rcx]
0x18000affd  mov     rax, [rax+10h]
0x18000b001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b006  nop
0x18000b007  mov     rax, [rsp+120h+var_F0]
0x18000b00c  add     dword ptr [rax+8], 0FFFFFFFFh
0x18000b010  jz      loc_18000AEE5
0x18000b016  jmp     loc_18000AF1A
0x18000b01b  mov     [rbp+57h+var_98], 800A0E78h
0x18000b022  lea     rcx, [rbp+57h+TlsValue]; this
0x18000b026  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000b02b  test    eax, eax
0x18000b02d  jz      loc_18000AC28
0x18000b033  cmp     [rbp+57h+var_98], r13d
0x18000b037  jz      loc_18000AC28
0x18000b03d  test    byte ptr cs:_bidGblFlags, 2
0x18000b044  jz      loc_18000AF5D
0x18000b04a  lea     rcx, [rdi+618h]; this
0x18000b051  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000b056  cmp     eax, 0FFFFFFFFh
0x18000b059  jz      loc_18000B1C5
0x18000b05f  lea     rcx, [rdi+618h]; this
0x18000b066  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000b06b  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000b072  mov     dword ptr [rsp+120h+var_100], 0BE7h
0x18000b07a  mov     r9d, eax
0x18000b07d  lea     r8, aCrecordsetGetB_2; "<CRecordset::get_Bookmark|ADO|ERR> %u#,"...
0x18000b084  mov     edx, 2F9C09h
0x18000b089  call    _bidTraceW
0x18000b08e  jmp     loc_18000AF5D
0x18000b093  lea     rcx, [rsp+120h+var_F0]; this
0x18000b098  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000b09d  jmp     loc_18000AE62
  ... truncated ...
```
