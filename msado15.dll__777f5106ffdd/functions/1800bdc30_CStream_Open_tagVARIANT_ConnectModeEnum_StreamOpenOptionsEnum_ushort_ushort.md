# CStream::Open(tagVARIANT,ConnectModeEnum,StreamOpenOptionsEnum,ushort *,ushort *)

- ea: `0x1800bdc30`
- end: `0x1800bf09c`
- name: `?Open@CStream@@UEAAJUtagVARIANT@@W4ConnectModeEnum@@W4StreamOpenOptionsEnum@@PEAG3@Z`
- size: `5228`
- prototype: `__int64 __usercall@<rax>(CStream *__hidden this@<rcx>, struct tagVARIANT *@<rdx>, enum ConnectModeEnum@<r8d>, enum StreamOpenOptionsEnum@<r9d>, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009f9d0`

## callees

- `0x18001a750`
- `0x18001a820`
- `0x180020da0`
- `0x180020e20`
- `0x180030ce0`
- `0x180031760`
- `0x180032710`
- `0x1800465a4`
- `0x18004c390`
- `0x18004f1b0`
- `0x180053d40`
- `0x180054098`
- `0x180057938`
- `0x180059ccc`
- `0x18005a16c`
- `0x18005a3a0`
- `0x18005b790`
- `0x18006a22c`
- `0x1800bdc30`
- `0x1800bf0a4`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800ca4c4`
- `0x1800ca824`
- `0x1800caa28`
- `0x1800cd638`
- `0x1800cd800`
- `0x1800cd890`
- `0x1800cd920`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800becca`
- `MSDART!MpHeapAlloc` at `0x1800becca`
- `ole32!CoCreateInstance` at `0x1800be905`
- `ole32!CoCreateInstance` at `0x1800be905`
- `OLEAUT32!__imp_SysAllocString` at `0x1800be741`
- `OLEAUT32!__imp_SysAllocString` at `0x1800be741`
- `OLEAUT32!__imp_VariantInit` at `0x1800bdf65`
- `OLEAUT32!__imp_VariantInit` at `0x1800bdf65`
- `OLEAUT32!__imp_VariantClear` at `0x1800be2e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800be2e2`

## string_xrefs

- `0x1800bdd34`: `<CStream::Open|ADO|ERR> %u#, line %d\n`
- `0x1800be02e`: `<CStream::Open|ADO|ERR> %u#, line %d\n`
- `0x1800be2bf`: `<CStream::Open|ADO|ERR> %u#, line %d\n`
- `0x1800be7c3`: `<CStream::Open|ADO|ERR> %u#, line %d\n`
- `0x1800be961`: `<CStream::Open|ADO|ERR> %u#, line %d\n`
- `0x1800bed63`: `<CStream::Open|ADO|ERR> %u#, line %d\n`
- `0x1800be054`: `<CStream::Open|ADO|ERR>  line %d\n`
- `0x1800be3c0`: `<CStream::Open|ADO|ERR>  line %d\n`
- `0x1800be7e9`: `<CStream::Open|ADO|ERR>  line %d\n`
- `0x1800be9e6`: `<CStream::Open|ADO|ERR>  line %d\n`
- `0x1800bedfb`: `<CStream::Open|ADO|ERR>  line %d\n`
- `0x1800befcf`: `<CStream::Open|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CStream::Open(
        CStream *this,
        struct tagVARIANT *a2,
        unsigned __int32 a3,
        const char *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  int v6; // r15d
  unsigned int BidObjectID; // eax
  int v11; // r12d
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdx
  int HasValue; // eax
  int v17; // edx
  __int64 *v18; // r13
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rax
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned int v30; // ecx
  int v31; // ecx
  unsigned int v32; // eax
  __int64 v33; // rax
  int (__fastcall *v34)(__int64 *, __int128 *, struct IUnknown **); // rax
  wchar_t *v35; // rcx
  wchar_t *v36; // rbx
  unsigned __int16 *v37; // rbx
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r9
  __int64 v41; // rdx
  unsigned int v42; // eax
  unsigned __int16 **v43; // rbx
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rcx
  CAuthenticateInfo *v46; // rax
  CAuthenticateInfo *v47; // rsi
  unsigned int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // r9
  __int64 v51; // rdx
  int v52; // r9d
  __int64 v53; // r9
  wchar_t *v54; // r8
  int v55; // eax
  __int64 v56; // rcx
  int v57; // ebx
  unsigned int v58; // eax
  unsigned int v59; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+28h] [rbp-D8h]
  int v63; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v67; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v68; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v69[40]; // [rsp+90h] [rbp-70h] BYREF
  int v70; // [rsp+B8h] [rbp-48h]
  _QWORD v71[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v72; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v74[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v75; // [rsp+108h] [rbp+8h]
  CSysString *v76; // [rsp+120h] [rbp+20h]
  __int128 v77; // [rsp+130h] [rbp+30h] BYREF
  IRecordInfo *pRecInfo; // [rsp+140h] [rbp+40h]
  unsigned int v79; // [rsp+1A0h] [rbp+A0h] BYREF

  v72 = -1;
  v6 = (int)a4;
  if ( (bidGblFlags & 4) != 0 && off_18012ADA8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    v62 = v6;
    bidScopeEnterW(&v72, off_18012ADA8[0], BidObjectID, a2, a3);
  }
  CXLockContext::CXLockContext(
    (CXLockContext *)v69,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    a4);
  v11 = 1;
  CVar::CVar((CVar *)v74, a2, 4u, 1);
  v67 = 0;
  if ( (unsigned int)CContext::VariantFailed((CContext *)v69, (const struct CVar *)v74) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_244;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v13 = 1247241;
      LODWORD(ppv) = 1218;
LABEL_8:
      bidTraceW(off_18012A210[0], v13, L"<CStream::Open|ADO|ERR> %u#, line %d\n", v12, ppv);
      goto LABEL_244;
    }
    v14 = 1218;
    v15 = 1247241;
    goto LABEL_243;
  }
  if ( (((v75 & 0xBFFF) - 8) & 0xFFFA) == 0 && (v75 & 0xBFFF) != 0xC
    || (HasValue = CVar::HasValue((CVar *)v74), v17 = 0, !HasValue) )
  {
    v17 = 1;
  }
  if ( (unsigned int)CContext::ArgFailed((CContext *)v69, v17) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_244;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v13 = 1252361;
      LODWORD(ppv) = 1223;
      goto LABEL_8;
    }
    v14 = 1223;
    v15 = 1252361;
    goto LABEL_243;
  }
  v18 = (__int64 *)((char *)this + 168);
  if ( *((_QWORD *)this + 21) && (unsigned int)CContext::FailIfOpen((CContext *)v69, 0) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_244;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v13 = 1256457;
      LODWORD(ppv) = 1227;
      goto LABEL_8;
    }
    v14 = 1227;
    v15 = 1256457;
    goto LABEL_243;
  }
  if ( !(unsigned int)CVar::HasValue((CVar *)v74) )
  {
    if ( a3 || v6 != -1 || a5 && *a5 || a6 && *a6 || (v75 & 0xBFFF) != 0xA )
      v11 = 0;
    if ( !(unsigned int)CContext::ArgFailed((CContext *)v69, v11) )
    {
      v79 = CStream::OpenMemoryStream(this);
      CContext::Failed((CContext *)v69, (const int *)&v79);
      goto LABEL_244;
    }
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_244;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v13 = 1276937;
      LODWORD(ppv) = 1247;
      goto LABEL_8;
    }
    v14 = 1247;
    v15 = 1276937;
    goto LABEL_243;
  }
  if ( v6 != -1 && (v6 & 4) != 0 )
  {
    v64 = 0;
    v68 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    v65 = 0;
    v71[0] = 0;
    v66 = 0;
    v79 = 0;
    VariantInit(&pvarg);
    if ( (((v75 & 0xBFFF) - 9) & 0xFFFB) != 0 || !CVar::operator IUnknown *(v74, v19, v20, v21) )
    {
      v63 = -2146825287;
      if ( (unsigned int)CContext::Failed((CContext *)v69, &v63) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v26 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v27 = 1305609;
            LODWORD(ppv) = 1275;
            goto LABEL_49;
          }
          v28 = 1275;
          v29 = 1305609;
          goto LABEL_51;
        }
        goto LABEL_82;
      }
    }
    else
    {
      v25 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))CVar::operator IUnknown *(v74, v22, v23, v24);
      if ( (**v25)(v25, &IID_IADORecord, &v64) < 0 )
      {
        v63 = -2146825287;
        if ( (unsigned int)CContext::Failed((CContext *)v69, &v63) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_82;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v26 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v27 = 1300489;
            LODWORD(ppv) = 1270;
LABEL_49:
            bidTraceW(off_18012A210[0], v27, L"<CStream::Open|ADO|ERR> %u#, line %d\n", v26, ppv, v62);
            goto LABEL_82;
          }
          v28 = 1270;
          v29 = 1300489;
          goto LABEL_51;
        }
      }
    }
    v63 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 120LL))(v64, &v79);
    if ( (unsigned int)CContext::Failed((CContext *)v69, &v63) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_244;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v13 = 1309705;
        LODWORD(ppv) = 1279;
        goto LABEL_8;
      }
      v14 = 1279;
      v15 = 1309705;
      goto LABEL_243;
    }
    v30 = v79;
    if ( !v79 )
    {
      v30 = 1;
      v79 = 1;
    }
    if ( a3 )
    {
      if ( (a3 & 3) == 3 )
      {
        v31 = v30 & 3;
        if ( v31 != 3 )
          a3 = v31 | a3 & 0xFFFFFFFC;
      }
      v63 = (*(__int64 (__fastcall **)(CStream *, _QWORD))(*(_QWORD *)this + 136LL))(this, a3);
      if ( (unsigned int)CContext::Failed((CContext *)v69, &v63) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_244;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 1327113;
          LODWORD(ppv) = 1296;
          goto LABEL_8;
        }
        v14 = 1296;
        v15 = 1327113;
        goto LABEL_243;
      }
    }
    else
    {
      v63 = (*(__int64 (__fastcall **)(CStream *, _QWORD))(*(_QWORD *)this + 136LL))(this, v30);
      if ( (unsigned int)CContext::Failed((CContext *)v69, &v63) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_244;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 1316873;
          LODWORD(ppv) = 1286;
          goto LABEL_8;
        }
        v14 = 1286;
        v15 = 1316873;
        goto LABEL_243;
      }
    }
    v63 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v64 + 184LL))(v64, &v68);
    if ( !(unsigned int)CContext::Failed((CContext *)v69, &v63) )
    {
      pvarg.vt = 3;
      pvarg.lVal = -1;
      v33 = *v68;
      pRecInfo = pvarg.pRecInfo;
      v34 = *(int (__fastcall **)(__int64 *, __int128 *, struct IUnknown **))(v33 + 80);
      v77 = *(_OWORD *)&pvarg.vt;
      if ( v34(v68, &v77, &v65) < 0
        || ((int (__fastcall *)(struct IUnknown *, VARIANTARG *))v65->lpVtbl[4].AddRef)(v65, &pvarg) < 0
        || ((pvarg.vt - 9) & 0xFFFB) != 0
        || (**(int (__fastcall ***)(LONGLONG, GUID *, _QWORD *))pvarg.llVal)(
             pvarg.llVal,
             &IID_IADOStreamConstruction,
             v71) < 0 )
      {
        v11 = 0;
      }
      if ( (unsigned int)CContext::FeatureFailed((CContext *)v69, v11) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_82;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v26 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v27 = 1342473;
          LODWORD(ppv) = 1311;
          goto LABEL_49;
        }
        v28 = 1311;
        v29 = 1342473;
      }
      else
      {
        v63 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v71[0] + 56LL))(v71[0], &v66);
        if ( (unsigned int)CContext::Failed((CContext *)v69, &v63) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_82;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v26 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v27 = 1344521;
            LODWORD(ppv) = 1313;
            goto LABEL_49;
          }
          v28 = 1313;
          v29 = 1344521;
        }
        else
        {
          v63 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v66)(v66, &IID_IStream, (char *)this + 168);
          if ( !(unsigned int)CContext::Failed((CContext *)v69, &v63) || (bidGblFlags & 2) == 0 )
            goto LABEL_82;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v26 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v27 = 1345545;
            LODWORD(ppv) = 1314;
            goto LABEL_49;
          }
          v28 = 1314;
          v29 = 1345545;
        }
      }
LABEL_51:
      bidTraceW(off_18012A210[0], v29, L"<CStream::Open|ADO|ERR>  line %d\n", v28);
      goto LABEL_82;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
      {
        bidTraceW(off_18012A210[0], 1331209, L"<CStream::Open|ADO|ERR>  line %d\n", 1300);
      }
      else
      {
        v32 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        LODWORD(ppv) = 1300;
        bidTraceW(off_18012A210[0], 1331209, L"<CStream::Open|ADO|ERR> %u#, line %d\n", v32, ppv);
      }
    }
LABEL_82:
    VariantClear(&pvarg);
    if ( v65 )
    {
      ((void (__fastcall *)(struct IUnknown *))v65->lpVtbl->Release)(v65);
      v65 = 0;
    }
    if ( v68 )
    {
      (*(void (__fastcall **)(__int64 *))(*v68 + 16))(v68);
      v68 = 0;
    }
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( v71[0] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v71[0] + 16LL))(v71[0]);
      v71[0] = 0;
    }
    if ( v66 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      v66 = 0;
    }
    if ( v70 < 0 && (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v13 = 1357833;
        LODWORD(ppv) = 1326;
        goto LABEL_8;
      }
      v14 = 1326;
      v15 = 1357833;
      goto LABEL_243;
    }
    goto LABEL_244;
  }
  if ( (v75 & 0xBFFF) == 8 )
  {
    v35 = (*((_BYTE *)v76 + 8) & 4) != 0 ? *(wchar_t **)v76 : 0LL;
    if ( (unsigned int)ContainsURL(v35, 0) )
    {
      v65 = 0;
      v66 = 0;
      v64 = 0;
      if ( a3 )
      {
        v79 = (*(__int64 (__fastcall **)(CStream *, _QWORD))(*(_QWORD *)this + 136LL))(this, a3);
        if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_244;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v13 = 1453065;
            LODWORD(ppv) = 1419;
            goto LABEL_8;
          }
          v14 = 1419;
          v15 = 1453065;
          goto LABEL_243;
        }
      }
      if ( !*((_DWORD *)this + 48) )
      {
        v79 = (*(__int64 (__fastcall **)(CStream *, __int64))(*(_QWORD *)this + 136LL))(this, 1);
        if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_244;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v13 = 1457161;
            LODWORD(ppv) = 1423;
            goto LABEL_8;
          }
          v14 = 1423;
          v15 = 1457161;
          goto LABEL_243;
        }
      }
      if ( (*((_BYTE *)v76 + 8) & 4) != 0
        && (v36 = *(wchar_t **)v76, v79 = 0, v36)
        && (unsigned int)ContainsURL(v36, &v79) )
      {
        v37 = SysAllocString(&v36[v79]);
      }
      else
      {
        v37 = 0;
      }
      CSysString::CSysString((CSysString *)v71, v37, 2u);
      CVar::operator=((CVar *)v74);
      if ( (unsigned int)CContext::MemFailed((CContext *)v69, v37) )
      {
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_163:
          if ( v65 )
          {
            ((void (__fastcall *)(struct IUnknown *))v65->lpVtbl->Release)(v65);
            v65 = 0;
          }
          if ( v66 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            v66 = 0;
          }
          if ( v64 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            v64 = 0;
          }
          CSysString::~CSysString((CSysString *)v71);
          goto LABEL_244;
        }
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v39 = 1466377;
          LODWORD(ppv) = 1432;
LABEL_144:
          bidTraceW(off_18012A210[0], v39, L"<CStream::Open|ADO|ERR> %u#, line %d\n", v38, ppv, v62);
          goto LABEL_163;
        }
        v40 = 1432;
        v41 = 1466377;
        goto LABEL_146;
      }
      if ( (unsigned int)CContext::VariantFailed((CContext *)v69, (const struct CVar *)v74) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_163;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v39 = 1468425;
          LODWORD(ppv) = 1434;
          goto LABEL_144;
        }
        v40 = 1434;
        v41 = 1468425;
LABEL_146:
        bidTraceW(off_18012A210[0], v41, L"<CStream::Open|ADO|ERR>  line %d\n", v40);
        goto LABEL_163;
      }
      if ( (v75 & 0xBFFF) != 8 || (unsigned int)CSysString::IsEmpty(v76) )
      {
        v79 = -2146825287;
        if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_163;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v39 = 1472521;
            LODWORD(ppv) = 1438;
            goto LABEL_144;
          }
          v40 = 1438;
          v41 = 1472521;
          goto LABEL_146;
        }
      }
      v79 = CoCreateInstance(&CLSID_CRootBinder, 0, 3u, &IID_IBindResource, &v67);
      if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
          {
            bidTraceW(off_18012A210[0], 1482761, L"<CStream::Open|ADO|ERR>  line %d\n", 1448);
          }
          else
          {
            v42 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            LODWORD(ppv) = 1448;
            bidTraceW(off_18012A210[0], 1482761, L"<CStream::Open|ADO|ERR> %u#, line %d\n", v42, ppv);
          }
        }
        goto LABEL_163;
      }
      (*(void (__fastcall **)(char *, GUID *, struct IUnknown **))(*((_QWORD *)this + 12) + 32LL))(
        (char *)this + 96,
        &IID_IUnknown,
        &v65);
      v43 = (unsigned __int16 **)((char *)this + 120);
      if ( (*((_BYTE *)this + 128) & 3) != 0 )
      {
        if ( !*v43 )
        {
LABEL_179:
          v79 = -2146824572;
          if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_163;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v39 = 1491977;
              LODWORD(ppv) = 1457;
              goto LABEL_144;
            }
            v40 = 1457;
            v41 = 1491977;
            goto LABEL_146;
          }
          v43 = (unsigned __int16 **)((char *)this + 120);
LABEL_185:
          if ( v66 )
          {
            v45 = v64;
            if ( v64 )
            {
              if ( *((_DWORD *)this + 29) )
              {
                v79 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v66 + 24LL))(v66, v65);
                if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_163;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                  {
                    v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    v39 = 1499145;
                    LODWORD(ppv) = 1464;
                    goto LABEL_144;
                  }
                  v40 = 1464;
                  v41 = 1499145;
                  goto LABEL_146;
                }
                v45 = v64;
              }
              v79 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v45 + 32LL))(
                      v45,
                      *((unsigned int *)this + 32));
              if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_163;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  v39 = 1501193;
                  LODWORD(ppv) = 1466;
                  goto LABEL_144;
                }
                v40 = 1466;
                v41 = 1501193;
                goto LABEL_146;
              }
              if ( *v43 )
              {
                v79 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 24LL))(v64);
                if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_163;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                  {
                    v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    v39 = 1504265;
                    LODWORD(ppv) = 1469;
                    goto LABEL_144;
                  }
                  v40 = 1469;
                  v41 = 1504265;
                  goto LABEL_146;
                }
              }
            }
          }
          v46 = (CAuthenticateInfo *)MpHeapAlloc(g_hHeapHandle, 10485760, 32);
          if ( v46 )
          {
            v47 = CAuthenticateInfo::CAuthenticateInfo(v46);
            if ( v47 )
              goto LABEL_207;
          }
          else
          {
            v47 = 0;
          }
          v79 = -2147024882;
          if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_163;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v38 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v39 = 1511433;
              LODWORD(ppv) = 1476;
              goto LABEL_144;
            }
            v40 = 1476;
            v41 = 1511433;
            goto LABEL_146;
          }
LABEL_207:
          v79 = CAuthenticateInfo::PutUserID(v47, a5);
          if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_236;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v48 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v49 = 1513481;
              LODWORD(ppv) = 1478;
LABEL_211:
              bidTraceW(off_18012A210[0], v49, L"<CStream::Open|ADO|ERR> %u#, line %d\n", v48, ppv, v62);
              goto LABEL_236;
            }
            v50 = 1478;
            v51 = 1513481;
          }
          else
          {
            v79 = CAuthenticateInfo::PutPassword(v47, a6);
            if ( !(unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) )
            {
              v52 = 0;
              if ( (v6 & 1) != 0 && v6 != -1 )
                v52 = 4096;
              v53 = *((_DWORD *)this + 48) | (unsigned int)v52;
              v79 = 0;
              if ( (*((_BYTE *)v76 + 8) & 4) != 0 )
                v54 = *(wchar_t **)v76;
              else
                v54 = 0;
              v63 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, wchar_t *, __int64, const GUID *, GUID *, CAuthenticateInfo *, _QWORD, unsigned int *, char *))(*(_QWORD *)v67 + 24LL))(
                      v67,
                      0,
                      v54,
                      v53,
                      &DBGUID_STREAM,
                      &IID_IStream,
                      v47,
                      0,
                      &v79,
                      (char *)this + 168);
              if ( v63 == 265946 )
              {
                v55 = MapOLEDBStatusToADOErrorDirect(v79, (const struct OLEDBStatusMap *)&g_BindResourceStatusMap);
                if ( v55 != -2147217887 )
                {
                  v56 = *v18;
                  v63 = v55;
                  if ( v56 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                    *v18 = 0;
                  }
                }
              }
              CContext::Failed((CContext *)v69, &v63);
              goto LABEL_236;
            }
            if ( (bidGblFlags & 2) == 0 )
            {
LABEL_236:
              if ( v47 )
                CAuthenticateInfo::Release(v47);
              goto LABEL_163;
            }
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v48 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v49 = 1514505;
              LODWORD(ppv) = 1479;
              goto LABEL_211;
            }
            v50 = 1479;
            v51 = 1514505;
          }
          bidTraceW(off_18012A210[0], v51, L"<CStream::Open|ADO|ERR>  line %d\n", v50);
          goto LABEL_236;
        }
        v44 = *v43;
      }
      else
      {
        v44 = *v43;
        if ( !*v43 )
          goto LABEL_185;
      }
      if ( !(unsigned int)IsTrustedMachine(v44)
        || (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v67)(v67, &IID_IObjectWithSite, &v66) >= 0
        && (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v67)(v67, &IID_IADOSecurity, &v64) >= 0
        || !(unsigned int)SecurityDialog(v65, *v43, 0) )
      {
        goto LABEL_185;
      }
      goto LABEL_179;
    }
  }
  v79 = -2146825287;
  if ( (unsigned int)CContext::Failed((CContext *)v69, (const int *)&v79) && (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v13 = 1547273;
      LODWORD(ppv) = 1511;
      goto LABEL_8;
    }
    v14 = 1511;
    v15 = 1547273;
LABEL_243:
    bidTraceW(off_18012A210[0], v15, L"<CStream::Open|ADO|ERR>  line %d\n", v14);
  }
LABEL_244:
  if ( v67 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v67 + 16LL))(v67);
  if ( (bidGblFlags & 2) != 0 && off_18012A918[0] )
  {
    v57 = v70;
    v58 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    LODWORD(ppv) = v57;
    bidTraceW(off_18012A210[0], 1554432, off_18012A918[0], v58, ppv);
  }
  if ( (bidGblFlags & 4) != 0 && v72 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v72);
  v59 = v70;
  v74[0] = &CVar::`vftable';
  CVar::Clear((CVar *)v74);
  CXLockContext::~CXLockContext((CXLockContext *)v69);
  return v59;
}

```

## disassembly

```asm
0x1800bdc30  push    rbp
0x1800bdc32  push    rbx
0x1800bdc33  push    rsi
0x1800bdc34  push    rdi
0x1800bdc35  push    r12
0x1800bdc37  push    r13
0x1800bdc39  push    r14
0x1800bdc3b  push    r15
0x1800bdc3d  lea     rbp, [rsp-58h]
0x1800bdc42  sub     rsp, 158h
0x1800bdc49  xor     r14d, r14d
0x1800bdc4c  mov     [rbp+90h+var_B8], 0FFFFFFFFFFFFFFFFh
0x1800bdc54  test    byte ptr cs:_bidGblFlags, 4
0x1800bdc5b  mov     r15d, r9d
0x1800bdc5e  mov     esi, r8d
0x1800bdc61  mov     rbx, rdx
0x1800bdc64  mov     rdi, rcx
0x1800bdc67  jz      short loc_1800BDCA0
0x1800bdc69  mov     rax, cs:off_18012ADA8; "<CStream::Open|API|ADO> %u#, varSource:"...
0x1800bdc70  test    rax, rax
0x1800bdc73  jz      short loc_1800BDCA0
0x1800bdc75  add     rcx, 98h; this
0x1800bdc7c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bdc81  mov     rdx, cs:off_18012ADA8; "<CStream::Open|API|ADO> %u#, varSource:"...
0x1800bdc88  lea     rcx, [rbp+90h+var_B8]
0x1800bdc8c  mov     r9, rbx
0x1800bdc8f  mov     dword ptr [rsp+190h+var_168], r15d
0x1800bdc94  mov     r8d, eax
0x1800bdc97  mov     dword ptr [rsp+190h+ppv], esi
0x1800bdc9b  call    _bidScopeEnterW
0x1800bdca0  mov     r8, [rdi+90h]
0x1800bdca7  lea     rcx, [rdi+20h]
0x1800bdcab  mov     r13d, 8
0x1800bdcb1  mov     rax, rdi
0x1800bdcb4  add     r8, r13; struct CCriticalSection **
0x1800bdcb7  neg     rax
0x1800bdcba  sbb     rdx, rdx
0x1800bdcbd  and     rdx, rcx; struct CStdComObjectRoot *
0x1800bdcc0  lea     rcx, [rbp+90h+var_100]; this
0x1800bdcc4  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800bdcc9  lea     r12d, [r13-7]
0x1800bdccd  mov     r8b, 4; unsigned __int8
0x1800bdcd0  mov     r9d, r12d; int
0x1800bdcd3  lea     rcx, [rbp+90h+var_98]; this
0x1800bdcd7  mov     rdx, rbx; struct tagVARIANT *
0x1800bdcda  call    ??0CVar@@QEAA@AEBUtagVARIANT@@EH@Z; CVar::CVar(tagVARIANT const &,uchar,int)
0x1800bdcdf  lea     rdx, [rbp+90h+var_98]; struct CVar *
0x1800bdce3  mov     [rbp+90h+var_110], r14
0x1800bdce7  lea     rcx, [rbp+90h+var_100]; this
0x1800bdceb  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x1800bdcf0  mov     bl, 2
0x1800bdcf2  test    eax, eax
0x1800bdcf4  jz      short loc_1800BDD58
0x1800bdcf6  test    byte ptr cs:_bidGblFlags, bl
0x1800bdcfc  jz      loc_1800BEFDB
0x1800bdd02  lea     rsi, [rdi+98h]
0x1800bdd09  mov     rcx, rsi; this
0x1800bdd0c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bdd11  or      ebx, 0FFFFFFFFh
0x1800bdd14  cmp     eax, ebx
0x1800bdd16  jz      short loc_1800BDD48
0x1800bdd18  mov     rcx, rsi; this
0x1800bdd1b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bdd20  mov     edx, 130809h
0x1800bdd25  mov     dword ptr [rsp+190h+ppv], 4C2h
0x1800bdd2d  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bdd34  lea     r8, aCstreamOpenAdo; "<CStream::Open|ADO|ERR> %u#, line %d\n"
0x1800bdd3b  mov     r9d, eax
0x1800bdd3e  call    _bidTraceW
0x1800bdd43  jmp     loc_1800BEFDB
0x1800bdd48  mov     r9d, 4C2h
0x1800bdd4e  mov     edx, 130809h
0x1800bdd53  jmp     loc_1800BEFC8
0x1800bdd58  movzx   ecx, [rbp+90h+var_88]
0x1800bdd5c  mov     eax, 0BFFFh
0x1800bdd61  and     cx, ax
0x1800bdd64  mov     edx, 0FFFAh
0x1800bdd69  movzx   eax, cx
0x1800bdd6c  sub     ax, r13w
0x1800bdd70  test    dx, ax
0x1800bdd73  jnz     short loc_1800BDD7B
0x1800bdd75  cmp     cx, 0Ch
0x1800bdd79  jnz     short loc_1800BDD8B
0x1800bdd7b  lea     rcx, [rbp+90h+var_98]; this
0x1800bdd7f  call    ?HasValue@CVar@@QEBAHXZ; CVar::HasValue(void)
0x1800bdd84  mov     edx, r14d
0x1800bdd87  test    eax, eax
0x1800bdd89  jnz     short loc_1800BDD8E
0x1800bdd8b  mov     edx, r12d; int
0x1800bdd8e  lea     rcx, [rbp+90h+var_100]; this
0x1800bdd92  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800bdd97  test    eax, eax
0x1800bdd99  jz      short loc_1800BDDE7
0x1800bdd9b  test    byte ptr cs:_bidGblFlags, bl
0x1800bdda1  jz      loc_1800BEFDB
0x1800bdda7  lea     rsi, [rdi+98h]
0x1800bddae  mov     rcx, rsi; this
0x1800bddb1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bddb6  or      ebx, 0FFFFFFFFh
0x1800bddb9  cmp     eax, ebx
0x1800bddbb  jz      short loc_1800BDDD7
0x1800bddbd  mov     rcx, rsi; this
0x1800bddc0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bddc5  mov     edx, 131C09h
0x1800bddca  mov     dword ptr [rsp+190h+ppv], 4C7h
0x1800bddd2  jmp     loc_1800BDD2D
0x1800bddd7  mov     r9d, 4C7h
0x1800bdddd  mov     edx, 131C09h
0x1800bdde2  jmp     loc_1800BEFC8
0x1800bdde7  lea     r13, [rdi+0A8h]
0x1800bddee  cmp     [r13+0], r14
0x1800bddf2  jz      short loc_1800BDE4F
0x1800bddf4  xor     edx, edx; int
0x1800bddf6  lea     rcx, [rbp+90h+var_100]; this
0x1800bddfa  call    ?FailIfOpen@CContext@@QEAAHH@Z; CContext::FailIfOpen(int)
0x1800bddff  test    eax, eax
0x1800bde01  jz      short loc_1800BDE4F
0x1800bde03  test    byte ptr cs:_bidGblFlags, bl
0x1800bde09  jz      loc_1800BEFDB
0x1800bde0f  lea     rsi, [rdi+98h]
0x1800bde16  mov     rcx, rsi; this
0x1800bde19  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bde1e  or      ebx, 0FFFFFFFFh
0x1800bde21  cmp     eax, ebx
0x1800bde23  jz      short loc_1800BDE3F
0x1800bde25  mov     rcx, rsi; this
0x1800bde28  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bde2d  mov     edx, 132C09h
0x1800bde32  mov     dword ptr [rsp+190h+ppv], 4CBh
0x1800bde3a  jmp     loc_1800BDD2D
0x1800bde3f  mov     r9d, 4CBh
0x1800bde45  mov     edx, 132C09h
0x1800bde4a  jmp     loc_1800BEFC8
0x1800bde4f  lea     rcx, [rbp+90h+var_98]; this
0x1800bde53  call    ?HasValue@CVar@@QEBAHXZ; CVar::HasValue(void)
0x1800bde58  test    eax, eax
0x1800bde5a  jnz     loc_1800BDF22
0x1800bde60  test    esi, esi
0x1800bde62  jnz     short loc_1800BDEA0
0x1800bde64  cmp     r15d, 0FFFFFFFFh
0x1800bde68  jnz     short loc_1800BDEA0
0x1800bde6a  mov     rax, [rbp+90h+arg_20]
0x1800bde71  test    rax, rax
0x1800bde74  jz      short loc_1800BDE7C
0x1800bde76  cmp     [rax], r14w
0x1800bde7a  jnz     short loc_1800BDEA0
0x1800bde7c  mov     rax, [rbp+90h+arg_28]
0x1800bde83  test    rax, rax
0x1800bde86  jz      short loc_1800BDE8E
0x1800bde88  cmp     [rax], r14w
0x1800bde8c  jnz     short loc_1800BDEA0
0x1800bde8e  movzx   eax, [rbp+90h+var_88]
0x1800bde92  mov     ecx, 0BFFFh
0x1800bde97  and     ax, cx
0x1800bde9a  cmp     ax, 0Ah
0x1800bde9e  jz      short loc_1800BDEA3
0x1800bdea0  mov     r12d, r14d
0x1800bdea3  mov     edx, r12d; int
0x1800bdea6  lea     rcx, [rbp+90h+var_100]; this
0x1800bdeaa  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800bdeaf  test    eax, eax
0x1800bdeb1  jz      short loc_1800BDEFF
0x1800bdeb3  test    byte ptr cs:_bidGblFlags, bl
0x1800bdeb9  jz      loc_1800BEFDB
0x1800bdebf  lea     rsi, [rdi+98h]
0x1800bdec6  mov     rcx, rsi; this
0x1800bdec9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bdece  or      ebx, 0FFFFFFFFh
0x1800bded1  cmp     eax, ebx
0x1800bded3  jz      short loc_1800BDEEF
0x1800bded5  mov     rcx, rsi; this
0x1800bded8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bdedd  mov     edx, 137C09h
0x1800bdee2  mov     dword ptr [rsp+190h+ppv], 4DFh
0x1800bdeea  jmp     loc_1800BDD2D
0x1800bdeef  mov     r9d, 4DFh
0x1800bdef5  mov     edx, 137C09h
0x1800bdefa  jmp     loc_1800BEFC8
0x1800bdeff  mov     rcx, rdi; this
0x1800bdf02  call    ?OpenMemoryStream@CStream@@AEAAJXZ; CStream::OpenMemoryStream(void)
0x1800bdf07  lea     rdx, [rbp+90h+arg_0]; int *
0x1800bdf0e  mov     [rbp+90h+arg_0], eax
0x1800bdf14  lea     rcx, [rbp+90h+var_100]; this
0x1800bdf18  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bdf1d  jmp     loc_1800BEFDB
0x1800bdf22  cmp     r15d, 0FFFFFFFFh
0x1800bdf26  jz      loc_1800BE5BF
0x1800bdf2c  test    r15b, 4
0x1800bdf30  jz      loc_1800BE5BF
0x1800bdf36  xorps   xmm0, xmm0
0x1800bdf39  mov     [rsp+190h+var_128], r14
0x1800bdf3e  xor     eax, eax
0x1800bdf40  mov     [rbp+90h+var_108], r14
0x1800bdf44  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1800bdf48  mov     qword ptr [rbp+90h+pvarg+10h], rax
0x1800bdf4c  movups  xmmword ptr [rbp+90h+pvarg], xmm0
0x1800bdf50  mov     [rsp+190h+var_120], r14
0x1800bdf55  mov     [rbp+90h+var_C8], r14
0x1800bdf59  mov     [rsp+190h+var_118], r14
0x1800bdf5e  mov     [rbp+90h+arg_0], r14d
0x1800bdf65  call    cs:__imp_VariantInit
0x1800bdf6c  nop     dword ptr [rax+rax+00h]
0x1800bdf71  movzx   eax, [rbp+90h+var_88]
0x1800bdf75  mov     ecx, 0BFFFh
0x1800bdf7a  and     ax, cx
0x1800bdf7d  mov     r15d, 0FFFBh
0x1800bdf83  sub     ax, 9
0x1800bdf87  or      ebx, 0FFFFFFFFh
0x1800bdf8a  test    r15w, ax
0x1800bdf8e  jnz     loc_1800BE065
0x1800bdf94  lea     rcx, [rbp+90h+var_98]
0x1800bdf98  call    ??BCVar@@QEAAPEAUIUnknown@@XZ; CVar::operator IUnknown *(void)
0x1800bdf9d  test    rax, rax
0x1800bdfa0  jz      loc_1800BE065
0x1800bdfa6  lea     rcx, [rbp+90h+var_98]
0x1800bdfaa  call    ??BCVar@@QEAAPEAUIUnknown@@XZ; CVar::operator IUnknown *(void)
0x1800bdfaf  mov     r9, rax
0x1800bdfb2  lea     r8, [rsp+190h+var_128]
0x1800bdfb7  lea     rdx, IID_IADORecord
0x1800bdfbe  mov     rcx, [rax]
0x1800bdfc1  mov     rax, [rcx]
0x1800bdfc4  mov     rcx, r9
0x1800bdfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfcc  test    eax, eax
0x1800bdfce  jns     loc_1800BE0C6
0x1800bdfd4  lea     rdx, [rsp+190h+var_130]; int *
0x1800bdfd9  mov     [rsp+190h+var_130], 800A0BB9h
0x1800bdfe1  lea     rcx, [rbp+90h+var_100]; this
0x1800bdfe5  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bdfea  test    eax, eax
0x1800bdfec  jz      loc_1800BE0C6
0x1800bdff2  test    byte ptr cs:_bidGblFlags, 2
0x1800bdff9  jz      loc_1800BE2DE
0x1800bdfff  lea     rsi, [rdi+98h]
0x1800be006  mov     rcx, rsi; this
0x1800be009  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800be00e  cmp     eax, ebx
0x1800be010  jz      short loc_1800BE042
0x1800be012  mov     rcx, rsi; this
0x1800be015  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800be01a  mov     edx, 13D809h
0x1800be01f  mov     dword ptr [rsp+190h+ppv], 4F6h
0x1800be027  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800be02e  lea     r8, aCstreamOpenAdo; "<CStream::Open|ADO|ERR> %u#, line %d\n"
0x1800be035  mov     r9d, eax
0x1800be038  call    _bidTraceW
0x1800be03d  jmp     loc_1800BE2DE
0x1800be042  mov     r9d, 4F6h
0x1800be048  mov     edx, 13D809h
0x1800be04d  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800be054  lea     r8, aCstreamOpenAdo_0; "<CStream::Open|ADO|ERR>  line %d\n"
0x1800be05b  call    _bidTraceW
0x1800be060  jmp     loc_1800BE2DE
0x1800be065  lea     rdx, [rsp+190h+var_130]; int *
0x1800be06a  mov     [rsp+190h+var_130], 800A0BB9h
0x1800be072  lea     rcx, [rbp+90h+var_100]; this
0x1800be076  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800be07b  test    eax, eax
0x1800be07d  jz      short loc_1800BE0C6
0x1800be07f  test    byte ptr cs:_bidGblFlags, 2
0x1800be086  jz      loc_1800BE2DE
0x1800be08c  lea     rsi, [rdi+98h]
0x1800be093  mov     rcx, rsi; this
0x1800be096  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800be09b  cmp     eax, ebx
0x1800be09d  jz      short loc_1800BE0B9
0x1800be09f  mov     rcx, rsi; this
0x1800be0a2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800be0a7  mov     edx, 13EC09h
0x1800be0ac  mov     dword ptr [rsp+190h+ppv], 4FBh
0x1800be0b4  jmp     loc_1800BE027
0x1800be0b9  mov     r9d, 4FBh
0x1800be0bf  mov     edx, 13EC09h
0x1800be0c4  jmp     short loc_1800BE04D
0x1800be0c6  mov     rcx, [rsp+190h+var_128]
0x1800be0cb  lea     rdx, [rbp+90h+arg_0]
0x1800be0d2  mov     rax, [rcx]
0x1800be0d5  mov     rax, [rax+78h]
0x1800be0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be0de  lea     rdx, [rsp+190h+var_130]; int *
0x1800be0e3  mov     [rsp+190h+var_130], eax
0x1800be0e7  lea     rcx, [rbp+90h+var_100]; this
0x1800be0eb  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800be0f0  test    eax, eax
0x1800be0f2  jz      short loc_1800BE13E
0x1800be0f4  test    byte ptr cs:_bidGblFlags, 2
0x1800be0fb  jz      loc_1800BEFDB
0x1800be101  lea     rsi, [rdi+98h]
0x1800be108  mov     rcx, rsi; this
0x1800be10b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800be110  cmp     eax, ebx
0x1800be112  jz      short loc_1800BE12E
0x1800be114  mov     rcx, rsi; this
0x1800be117  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800be11c  mov     edx, 13FC09h
0x1800be121  mov     dword ptr [rsp+190h+ppv], 4FFh
0x1800be129  jmp     loc_1800BDD2D
0x1800be12e  mov     r9d, 4FFh
0x1800be134  mov     edx, 13FC09h
0x1800be139  jmp     loc_1800BEFC8
  ... truncated ...
```
